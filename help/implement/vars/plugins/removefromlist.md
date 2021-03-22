---
title: rfl
description: Rimuovere un valore specifico da una stringa delimitata da caratteri.
translation-type: tm+mt
source-git-commit: 4c23f3cf764834636c1cdcefb2903efc9c90be7a
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 2%

---


# Plug-in di Adobe: rfl (Rimuovi dall’elenco)

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

Il plug-in `rfl` consente di rimuovere in modo &quot;sicuro&quot; i valori dalle stringhe delimitate, ad esempio [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md) e altri. Questo plug-in è utile se desideri rimuovere valori specifici da una stringa delimitata senza preoccuparti dei delimitatori. Diversi altri plug-in dipendono da questo codice per essere eseguiti correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più di una variabile Analytics alla volta o se non si utilizzano plug-in dipendenti.

Il plug-in utilizza la logica seguente:

* Se il valore da rimuovere esiste, il plug-in mantiene tutti gli elementi della variabile eccetto il valore da rimuovere.
* Se il valore da rimuovere non esiste, il plug-in mantiene la stringa originale così com&#39;è.

## Installare il plug-in utilizzando l’estensione Adobe Experience Platform Launch

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza RFP (Rimuovi dall’elenco)
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato di Launch

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi il [!UICONTROL Configure tracking using custom code] pannello a soffietto, che mostra il pulsante [!UICONTROL Open Editor] .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

Il metodo `rfl` utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa): Variabile (o stringa) contenente un elenco di valori delimitati
* **`vr`** (obbligatorio, stringa): Il valore da rimuovere dall&#39; `lv` argomento. Adobe consiglia di non rimuovere più valori durante una singola chiamata `rfl`.
* **`d1`** (facoltativo, stringa): Il delimitatore utilizzato dall&#39; `lv` argomento. Impostazione predefinita di una virgola (`,`).
* **`d2`** (facoltativo, stringa): Il delimitatore che si desidera utilizzare per la stringa restituita. Predefinito sullo stesso valore dell&#39;argomento `d1`.
* **`df`** (facoltativo, booleano): Se  `true`, forza solo le istanze duplicate dell&#39; `vr` argomento dall&#39; `lv` argomento invece di tutte le istanze. Se non è impostato, viene impostato il valore predefinito `false`.

Quando si richiama questo metodo, viene restituita una stringa modificata contenente l&#39;argomento `lv` ma senza istanze (o istanze duplicate) del valore specificato nell&#39;argomento `vr`.

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

```js
s.events = "event22,event24,event25";
```

...e viene eseguito il seguente codice...

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

...e viene eseguito il seguente codice...

```js
s.events = s.rfl(s.events,"event26");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event24,event25";
```

In questo esempio, la chiamata rfl non ha apportato modifiche a s.events poiché s.events non conteneva &quot;event26&quot;

### Esempio n. 2

Se viene mostrato...

```js
s.events = "event22,event24,event25";
```

...e viene eseguito il seguente codice...

```js
s.events = s.rfl(s.events);
```

...il valore finale di s.events sarà:

```js
s.events = "";
```

Se l&#39;argomento lv o l&#39;argomento vr sono vuoti in una chiamata s.rfl, il plug-in non restituirà nulla

### Esempio n. 4

Se viene mostrato...

```js
s.prop4 = "hello|people|today";
```

...e viene eseguito il seguente codice...

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

Tieni presente che il plug-in restituisce solo un valore; in realtà non &quot;reimposta&quot; la variabile passata attraverso l&#39;argomento lv.

### Esempio n. 5

Se viene mostrato...

```js
s.prop4 = "hello|people|today";
```

...e viene eseguito il seguente codice...

```js
s.prop4 = s.rfl(s.prop4,"people");
```

...il valore finale di s.prop4 sarà ancora...

```js
s.prop4 = "hello|people|today";
```

Assicurati di impostare l’argomento d1 nei casi in cui il valore dell’argomento lv contenga un delimitatore diverso dal valore predefinito (ad esempio, virgola).

### Esempio n. 6

Se viene mostrato...

```js
s.events = "event22,event23,event25";
```

...e viene eseguito il seguente codice...

```js
s.events = s.rfl(s.events,"EVenT23");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23,event25";
```

Anche se questo esempio non è pratico, dimostra la necessità di passare valori sensibili a maiuscole e minuscole.

### Esempio n. 7

Se viene mostrato...

```js
s.events = "event22,event23:12345,event25";
```

...e viene eseguito il seguente codice...

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

...e viene eseguito il seguente codice...

```js
s.events = s.rfl(s.events,"event23:12345");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23:12345,event25";
```

Quando devi rimuovere un evento che utilizza la serializzazione e/o la sintassi numerica/valuta, devi specificare solo l’evento stesso (ovvero senza i valori serialization/numeric/currency) nella chiamata s.rfl.

### Esempio n. 9

Se viene mostrato...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...e viene eseguito il seguente codice...

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

...e viene eseguito il seguente codice...

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

...e viene eseguito il seguente codice...

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

...e viene eseguito il seguente codice...

```js
s.events = s.rfl(s.events,"event23,event24");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23,event24,event25";
```

L&#39;impostazione di più valori nell&#39;argomento vr non è supportata. La logica rfl nell&#39;esempio precedente dividerebbe prima i valori nell&#39;argomento lv (cioè s.events), quindi prova a far corrispondere ogni valore delimitato al valore completo dell&#39;argomento vr (cioè &quot;event23,event24&quot;).

### Esempio n. 13

Se viene mostrato...

```js
s.events = "event22,event23,event24,event25";
```

...e viene eseguito il seguente codice...

```js
s.events = s.rfl(s.events,"event23");
s.events = s.rfl(s.events,"event24");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event25");
```

Ogni valore da rimuovere dall’elenco deve essere contenuto all’interno della propria chiamata s.rfl.

### Esempio n. 14

Se viene mostrato...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...e viene eseguito il seguente codice...

```js
s.linkTrackVars = s.rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...il valore finale di s.linkTrackVars sarà:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Gli ultimi tre argomenti (cioè &quot;,&quot;,&quot;,&quot;, false) alla fine di questa chiamata s.rfl non sono necessarie ma non &quot;danneggiano nulla&quot; in quanto corrispondono alle impostazioni predefinite.

### Esempio n. 15

Se viene mostrato...

```js
s.events = "event22,event23,event24";
```

...e viene eseguito il seguente codice...

```js
s.rfl(s.events,"event23");
```

...il valore finale di s.events sarà ancora:

```js
s.events = "event22,event23,event24";
```

Tieni presente che il plug-in restituisce solo un valore; in realtà non &quot;reimposta&quot; la variabile passata attraverso l&#39;argomento lv.

## Cronologia versioni

### 2.1 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.01 (17 settembre 2019)

* Correzione di bug minori per il valore delimitatore predefinito

### 2.0 (16 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* È stata rimossa la necessità del plug-in `join` .

### 1.0 (18 luglio 2016)

* Versione iniziale.
