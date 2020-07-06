---
title: rfl
description: Rimuovere un valore specifico da una stringa delimitata da caratteri.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '1033'
ht-degree: 2%

---


# Plug-in Adobe: rfl (Rimuovi da elenco)

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarvi a ottenere più valore da Adobe  Analytics. L&#39;Assistenza clienti Adobe non fornisce supporto per questo plug-in, inclusa l&#39;installazione o la risoluzione dei problemi. Se avete bisogno di aiuto con questo plug-in, contattate l&#39;Account Manager della vostra azienda. Possono organizzare una riunione con un consulente per assistenza.

Il `rfl` plug-in consente di rimuovere in modo &quot;sicuro&quot; i valori dalle stringhe delimitate, ad esempio [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md)ecc. Questo plug-in è utile per rimuovere valori specifici da una stringa delimitata senza preoccuparsi dei delimitatori. Molti altri plug-in dipendono da questo codice per essere eseguiti correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più variabili Analytics  alla volta, oppure se non si utilizzano plug-in dipendenti.

Il plug-in utilizza la logica seguente:

* Se il valore che si desidera rimuovere esiste, il plug-in mantiene tutti gli elementi della variabile tranne il valore da rimuovere.
* Se il valore da rimuovere non esiste, il plug-in mantiene la stringa originale così com&#39;è.

## Installare il plug-in utilizzando l&#39;estensione Lancio del Adobe Experience Platform 

Adobe offre un’estensione che consente di utilizzare la maggior parte dei plug-in usati comunemente.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installare e pubblicare l’ [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo avete già fatto, create una regola con l&#39;etichetta &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (Page Top)
1. Aggiungete un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in Analytics  comuni
   * Tipo azione: Inizializza RFP (Rimuovi dall&#39;elenco)
1. Salvate e pubblicate le modifiche alla regola.

## Installare il plug-in utilizzando l&#39;editor di codice personalizzato Launch

Se non desiderate utilizzare l&#39;estensione del plug-in, potete utilizzare l&#39;editor di codice personalizzato.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
1. Fate clic sulla proprietà desiderata.
1. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto l&#39;estensione Adobe  Analytics.
1. Espandere la struttura [!UICONTROL Configure tracking using custom code] a soffietto, che mostra il [!UICONTROL Open Editor] pulsante.
1. Aprite l’editor di codice personalizzato e incollate il codice plug-in fornito di seguito nella finestra di modifica.
1. Salvate e pubblicate le modifiche nell’estensione Analytics .

## Installare il plug-in utilizzando AppMeasurement

Copiate e incollate il seguente codice in qualsiasi punto del file AppMeasurement dopo che è stata creata un&#39;istanza dell&#39;oggetto di tracciamento Analytics  (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione di commenti e numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.01 */
s.rfl=function(lv,vr,d1,d2,df){if(!lv||!vr)return"";var d=[],b="";d2=d2?d2:d1;df=df?!0:!1;lv=lv.split(d1?d1:",");d1=lv.length;for(var c=0;c<d1;c++)-1<lv[c].indexOf(":")&&(b=lv[c].split(":"),b[1]=b[0]+":"+b[1],lv[c]=b[0]),-1<lv[c].indexOf("=")&&(b=lv[c].split("="), b[1]=b[0]+"="+b[1],lv[c]=b[0]),lv[c]!==vr&&b?d.push(b[1]):lv[c]!==vr?d.push(lv[c]):lv[c]===vr&&df&&(b?d.push(b[1]):d.push(lv[c]),df=!1),b="";return d.join(d2)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `rfl` metodo utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa): Variabile (o stringa) contenente un elenco di valori delimitati
* **`vr`** (obbligatorio, stringa): Il valore da rimuovere dall&#39; `lv` argomento. Adobe consiglia di rimuovere più valori durante una singola `rfl` chiamata.
* **`d1`** (facoltativo, stringa): Il delimitatore utilizzato dall&#39; `lv` argomento. Il valore predefinito è una virgola (`,`).
* **`d2`** (facoltativo, stringa): Il delimitatore da utilizzare per la stringa di ritorno. Il valore predefinito è lo stesso dell&#39; `d1` argomento.
* **`df`** (facoltativo, booleano): Se `true`, forza solo le istanze duplicate dell&#39; `vr` argomento dall&#39; `lv` argomento invece di tutte le istanze. Il valore predefinito è `false` se non è impostato.

Se si chiama questo metodo, viene restituita una stringa modificata contenente l’ `lv` argomento ma senza le istanze (o istanze duplicate) del valore specificato nell’ `vr` argomento.

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

```js
s.events = "event22,event24,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event24");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event25";
```

### Esempio n. 2

Se viene mostrato...

```js
s.events = "event22,event24,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event26");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event24,event25";
```

In questo esempio, la chiamata rfl non ha apportato modifiche a s.events in quanto s.events non conteneva &quot;event26&quot;

### Esempio n. 3

Se viene mostrato...

```js
s.events = "event22,event24,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events);
```

...il valore finale di s.events sarà:

```js
s.events = "";
```

Se l&#39;argomento lv o vr è vuoto in una chiamata s.rfl, il plug-in non restituirà nulla

### Esempio n. 4

Se viene mostrato...

```js
s.prop4 = "hello|people|today";
```

...e viene eseguito il codice seguente...

```js
s.eVar5 = s.rfl(s.prop4,"people","|");
```

...il valore finale di s.prop4 sarà ancora...

```js
s.prop4 = "hello|people|today";
```

...ma il valore finale di s.eVar5 sarà:

```js
s.eVar5 = "hello|today";
```

Tenere presente che il plug-in restituisce solo un valore; in realtà non &quot;reimposta&quot; la variabile passata attraverso l&#39;argomento lv.

### Esempio n. 5

Se viene mostrato...

```js
s.prop4 = "hello|people|today";
```

...e viene eseguito il codice seguente...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...il valore finale di s.prop4 sarà ancora...

```js
s.prop4 = "hello|people|today";
```

Accertatevi di impostare l&#39;argomento d1 nei casi in cui il valore dell&#39;argomento lv contenga un delimitatore diverso dal valore predefinito (ad es. virgola).

### Esempio n. 6

Se viene mostrato...

```js
s.events = "event22,event23,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"EVenT23");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23,event25";
```

Anche se questo esempio non è pratico, dimostra la necessità di trasmettere valori con distinzione tra maiuscole e minuscole.

### Esempio n. 7

Se viene mostrato...

```js
s.events = "event22,event23:12345,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event23");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event25";
```

### Esempio n. 8

Se viene mostrato...

```js
s.events = "event22,event23:12345,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event23:12345");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23:12345,event25";
```

Per rimuovere un evento che utilizza la serializzazione e/o la sintassi numerica/valutaria, è necessario specificare solo l&#39;evento stesso (ovvero senza i valori serializzazione/numerici/valuta) nella chiamata s.rfl.

### Esempio n. 9

Se viene mostrato...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event23");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event24,event25");
```

### Esempio n. 10

Se viene mostrato...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event23", "", "",true);
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23,event24,event25");
```

### Esempio n. 11

Se viene mostrato...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event23", "", "|",true);
```

...il valore finale di s.events sarà:

```js
s.events = "event22|event23|event24|event25");
```

### Esempio n. 12

Se viene mostrato...

```js
s.events = "event22,event23,event24,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event23,event24");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23,event24,event25";
```

L&#39;impostazione di più valori nell&#39;argomento vr non è supportata. La logica rfl nell&#39;esempio precedente suddividerebbe prima i valori nell&#39;argomento lv (es.s.events), quindi provate a far corrispondere ogni valore delimitato al valore completo dell&#39;argomento vr (es. &quot;event23,event24&quot;).

### Esempio n. 13

Se viene mostrato...

```js
s.events = "event22,event23,event24,event25";
```

...e viene eseguito il codice seguente...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event25");
```

Ogni valore da rimuovere dall&#39;elenco deve essere contenuto all&#39;interno della propria chiamata s.rfl.

### Esempio n. 14

Se viene mostrato...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...e viene eseguito il codice seguente...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...il valore finale di s.linkTrackVars sarà:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Gli ultimi tre argomenti (vale a dire &quot;,&quot;,&quot;,&quot;, false) alla fine di questa chiamata s.rfl non sono necessari ma non &quot;fanno male a nulla&quot; se ci sono presenti perché corrispondono alle impostazioni predefinite.

### Esempio n. 15

Se viene mostrato...

```js
s.events = "event22,event23,event24";
```

...e viene eseguito il codice seguente...

```js
s.rfl(s.events,"event23");
```

...il valore finale di s.events sarà comunque:

```js
s.events = "event22,event23,event24";
```

Tenete presente che il plug-in restituisce solo un valore; in realtà non &quot;reimposta&quot; la variabile passata attraverso l&#39;argomento lv.

## Cronologia versioni

### 2.01 (17 settembre 2019)

* Correzione di bug secondari per il valore di delimitazione predefinito

### 2.0 (16 aprile 2018)

* Rilascio punto (ricompilato, dimensioni del codice più piccole).
* È stata rimossa la necessità del `join` plug-in.

### 1.0 (18 luglio 2016)

* Versione iniziale.
