---
title: rfl
description: Rimuovi un valore specifico da una stringa delimitata da caratteri.
feature: Appmeasurement Implementation
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 3%

---

# Plug-in Adobe: rfl (Rimuovi dall’elenco)

{{plug-in}}

Il plug-in `rfl` consente di rimuovere in modo sicuro i valori dalle stringhe delimitate, ad esempio [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md) e altri. Questo plug-in è utile se si desidera rimuovere valori specifici da una stringa delimitata senza preoccuparsi dei delimitatori. Diversi altri plug-in dipendono da questo codice per funzionare correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più variabili Analytics alla volta o se non si utilizzano plug-in dipendenti.

Il plug-in utilizza la logica seguente:

* Se il valore da rimuovere esiste, il plug-in mantiene tutto nella variabile, tranne il valore da rimuovere.
* Se il valore da rimuovere non esiste, il plug-in mantiene invariata la stringa originale.

## Installare il plug-in utilizzando l’estensione Web SDK o Web SDK

Questo plug-in non è ancora supportato per l&#39;utilizzo in Web SDK.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante [!UICONTROL Catalog]
1. Installa e pubblica l&#39;estensione [!UICONTROL Common Analytics Plugins]
1. Se non lo hai già fatto, crea una regola denominata &quot;Initialize Plug-ins&quot; (Inizializza plug-in) con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Library Loaded (Page Top)
1. Aggiungi un’azione alla regola precedente con la seguente configurazione:
   * Estensione: Common Analytics Plugins
   * Tipo azione: Inizializza RFP (Rimuovi dall&#39;elenco)
1. Salva e pubblica le modifiche apportate alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandere il pannello a soffietto [!UICONTROL Configure tracking using custom code], che mostra il pulsante [!UICONTROL Open Editor].
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copiare e incollare il codice seguente in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta Adobe a risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `rfl` utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa): variabile (o stringa) contenente un elenco di valori delimitati
* **`vr`** (obbligatorio, stringa): valore che si desidera rimuovere dall&#39;argomento `lv`. Adobe consiglia di non rimuovere più valori durante una singola chiamata `rfl`.
* **`d1`** (facoltativo, stringa): delimitatore utilizzato dall&#39;argomento `lv`. Impostazione predefinita: virgola (`,`).
* **`d2`** (facoltativo, stringa): delimitatore da utilizzare per la stringa restituita. Il valore predefinito dell&#39;argomento `d1` è lo stesso.
* **`df`** (facoltativo, booleano): se `true`, forza solo le istanze duplicate dell&#39;argomento `vr` dall&#39;argomento `lv` anziché da tutte le istanze. Impostazione predefinita: `false` se non impostata.

La chiamata di questa funzione restituisce una stringa modificata contenente l&#39;argomento `lv`, ma senza alcuna istanza (o istanze duplicate) del valore specificato nell&#39;argomento `vr`.

## Esempio di chiamate

### Esempio di #1

Se...

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

### Esempio di #2

Se...

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

### Esempio di #3

Se...

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

Se l&#39;argomento `lv` o l&#39;argomento `vr` sono vuoti in una chiamata `rfl`, il plug-in non restituisce nulla.

### Esempio di #4

Se...

```js
s.prop4 = "hello|people|today";
```

...e viene eseguito il seguente codice...

```js
s.eVar5 = rfl(s.prop4,"people","|");
```

...il valore finale di s.prop4 sarà comunque...

```js
s.prop4 = "hello|people|today";
```

...ma il valore finale di s.eVar5 sarà:

```js
s.eVar5 = "hello|today";
```

Tenere presente che il plug-in restituisce solo un valore; non reimposta effettivamente la variabile trasmessa tramite l&#39;argomento `lv`.

### Esempio di #5

Se...

```js
s.prop4 = "hello|people|today";
```

...e viene eseguito il seguente codice...

```js
s.prop4 = rfl(s.prop4,"people");
```

...il valore finale di s.prop4 sarà comunque...

```js
s.prop4 = "hello|people|today";
```

Assicurarsi di impostare l&#39;argomento `d1` nei casi in cui il valore dell&#39;argomento `lv` contiene un delimitatore diverso dal valore predefinito (ovvero virgola).

### Esempio di #6

Se...

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

Anche se questo esempio non è pratico, dimostra la necessità di trasmettere valori con distinzione tra maiuscole e minuscole.

### Esempio di #7

Se...

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

### Esempio di #8

Se...

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

Quando è necessario rimuovere un evento che utilizza la serializzazione e/o la sintassi numerica/valuta, è necessario specificare solo l&#39;evento stesso (ovvero senza i valori di serializzazione/numerica/valuta) nella chiamata `rfl`.

### Esempio di #9

Se...

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

### Esempio di #10

Se...

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

### Esempio di #11

Se...

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

### Esempio di #12

Se...

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

L&#39;impostazione di più valori nell&#39;argomento `vr` non è supportata. La logica `rfl` nell&#39;esempio precedente suddividerebbe prima i valori nell&#39;argomento `lv` (ad esempio s.events) quindi proverebbe a far corrispondere ogni valore delimitato al valore completo dell&#39;argomento `vr` (ad esempio `"event23,event24"`).

### Esempio di #13

Se...

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

Ogni valore da rimuovere dall&#39;elenco deve essere contenuto nella propria chiamata `rfl`.

### Esempio di #14

Se...

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

Gli ultimi tre argomenti (ad esempio &quot;,&quot;,&quot;,&quot;,false) alla fine di questa chiamata di `rfl` non sono necessari, ma non sono in grado di danneggiare nulla poiché corrispondono alle impostazioni predefinite.

### Esempio di #15

Se...

```js
s.events = "event22,event23,event24";
```

...e viene eseguito il seguente codice...

```js
rfl(s.events,"event23");
```

...il valore finale di s.events sarà comunque:

```js
s.events = "event22,event23,event24";
```

Anche in questo caso, il plug-in restituisce solo un valore; in realtà non reimposta la variabile trasmessa tramite l&#39;argomento `lv`.

## Cronologia versioni

### 2.1 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.01 (17 settembre 2019)

* Correzione di bug minori per il valore delimitatore predefinito

### 2.0 (16 aprile 2018)

* Versione a punti (ricompilata, con codice di dimensioni inferiori).
* Rimozione della necessità del plug-in `join`.

### 1.0 (18 luglio 2016)

* Versione iniziale.
