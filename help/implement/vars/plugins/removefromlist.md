---
title: rfl
description: Rimuovere un valore specifico da una stringa delimitata da caratteri.
feature: Variables
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 1%

---

# Plug-in di Adobe: rfl (Rimuovi dall’elenco)

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

La `rfl` il plug-in consente di rimuovere in modo &quot;sicuro&quot; i valori dalle stringhe delimitate, ad esempio [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md)e altri. Questo plug-in è utile se desideri rimuovere valori specifici da una stringa delimitata senza preoccuparti dei delimitatori. Diversi altri plug-in dipendono da questo codice per essere eseguiti correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più di una variabile Analytics alla volta o se non si utilizzano plug-in dipendenti.

Il plug-in utilizza la logica seguente:

* Se il valore da rimuovere esiste, il plug-in mantiene tutti gli elementi della variabile eccetto il valore da rimuovere.
* Se il valore da rimuovere non esiste, il plug-in mantiene la stringa originale così com&#39;è.

## Installare il plug-in utilizzando l’SDK per web o l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza RFP (Rimuovi dall’elenco)
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
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

La `rfl` La funzione utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa): Variabile (o stringa) contenente un elenco di valori delimitati
* **`vr`** (obbligatorio, stringa): Il valore da rimuovere dal `lv` argomento. Adobe sconsiglia di rimuovere più valori durante un singolo `rfl` chiama.
* **`d1`** (facoltativo, stringa): Il delimitatore che la `lv` viene utilizzato l&#39;argomento . Impostazione predefinita di una virgola (`,`).
* **`d2`** (facoltativo, stringa): Il delimitatore che si desidera utilizzare per la stringa restituita. Predefinito allo stesso valore della variabile `d1` argomento.
* **`df`** (facoltativo, booleano): Se `true`, forza solo le istanze duplicate del `vr` argomento del `lv` anziché tutte le istanze. Predefinito su `false` quando non è impostato.

Una chiamata a questa funzione restituisce una stringa modificata contenente `lv` ma senza istanze (o istanze duplicate) del valore specificato nel `vr` argomento.

## Chiamate di esempio

### Esempio n. 1

Se viene mostrato...

```js
s.events = "event22,event24,event25";
```

...e viene eseguito il seguente codice...

```js
s.events = rfl(s.events,"event24");
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
s.events = rfl(s.events,"event26");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event24,event25";
```

In questo esempio, la chiamata rfl non ha apportato modifiche a s.events poiché s.events non conteneva &quot;event26&quot;

### Esempio n. 3

Se viene mostrato...

```js
s.events = "event22,event24,event25";
```

...e viene eseguito il seguente codice...

```js
s.events = rfl(s.events);
```

...il valore finale di s.events sarà:

```js
s.events = "";
```

Se `lv` argomento o `vr` argomento vuoto in un `rfl` Chiama, quindi il plug-in non restituisce nulla.

### Esempio n. 4

Se viene mostrato...

```js
s.prop4 = "hello|people|today";
```

...e viene eseguito il seguente codice...

```js
s.eVar5 = rfl(s.prop4,"people","|");
```

...il valore finale di s.prop4 sarà ancora...

```js
s.prop4 = "hello|people|today";
```

...ma il valore finale di s.eVar5 sarà:

```js
s.eVar5 = "hello|today";
```

Tieni presente che il plug-in restituisce solo un valore; in realtà non &quot;reimposta&quot; la variabile passata attraverso il `lv` argomento.

### Esempio n. 5

Se viene mostrato...

```js
s.prop4 = "hello|people|today";
```

...e viene eseguito il seguente codice...

```js
s.prop4 = rfl(s.prop4,"people");
```

...il valore finale di s.prop4 sarà ancora...

```js
s.prop4 = "hello|people|today";
```

Assicurati di impostare il `d1` in casi in cui `lv` il valore dell&#39;argomento contiene un delimitatore diverso rispetto al valore predefinito (ovvero virgola).

### Esempio n. 6

Se viene mostrato...

```js
s.events = "event22,event23,event25";
```

...e viene eseguito il seguente codice...

```js
s.events = rfl(s.events,"EVenT23");
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
s.events = rfl(s.events,"event23");
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
s.events = rfl(s.events,"event23:12345");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23:12345,event25";
```

Quando devi rimuovere un evento che utilizza la serializzazione e/o la sintassi numerica/valutaria, devi specificare solo l’evento stesso (ovvero senza i valori serialization/numeric/currency) nel `rfl` chiama.

### Esempio n. 9

Se viene mostrato...

```js
s.events = "event22,event23,event23,event23,event24,event25";
```

...e viene eseguito il seguente codice...

```js
s.events = rfl(s.events,"event23");
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
s.events = rfl(s.events,"event23", "", "",true);
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
s.events = rfl(s.events,"event23", "", "|",true);
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
s.events = rfl(s.events,"event23,event24");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event23,event24,event25";
```

Impostazione di più valori nel `vr` argomento non supportato. La `rfl` Nell&#39;esempio precedente, i valori vengono prima suddivisi nel `lv` argomento (ad esempio s.events) quindi cercare di far corrispondere ogni valore delimitato al valore completo `vr` valore dell&#39;argomento (ovvero `"event23,event24"`).

### Esempio n. 13

Se viene mostrato...

```js
s.events = "event22,event23,event24,event25";
```

...e viene eseguito il seguente codice...

```js
s.events = rfl(s.events,"event23");
s.events = rfl(s.events,"event24");
```

...il valore finale di s.events sarà:

```js
s.events = "event22,event25");
```

Ogni valore da rimuovere dall’elenco deve essere contenuto all’interno del proprio `rfl` chiama.

### Esempio n. 14

Se viene mostrato...

```js
s.linkTrackVars = "events,eVar1,eVar2,eVar3";
```

...e viene eseguito il seguente codice...

```js
s.linkTrackVars = rfl(s.linkTrackVars,"eVar2", ",", ",", false);
```

...il valore finale di s.linkTrackVars sarà:

```js
s.linkTrackVars = "events,eVar1,eVar3";
```

Gli ultimi tre argomenti (cioè &quot;,&quot;,&quot;,&quot;, false) alla fine di questo `rfl` Le chiamate non sono necessarie, ma non &quot;danneggiano nulla&quot; poiché corrispondono alle impostazioni predefinite.

### Esempio n. 15

Se viene mostrato...

```js
s.events = "event22,event23,event24";
```

...e viene eseguito il seguente codice...

```js
rfl(s.events,"event23");
```

...il valore finale di s.events sarà ancora:

```js
s.events = "event22,event23,event24";
```

Tieni presente che il plug-in restituisce solo un valore; in realtà non &quot;reimposta&quot; la variabile passata attraverso il `lv` argomento.

## Cronologia versioni

### 2.1 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.01 (17 settembre 2019)

* Correzione di bug minori per il valore delimitatore predefinito

### 2.0 (16 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* È stata rimossa la necessità di `join` plug-in.

### 1.0 (18 luglio 2016)

* Versione iniziale.
