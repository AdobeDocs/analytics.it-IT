---
title: rfl
description: Rimuovi un valore specifico da una stringa delimitata da caratteri.
feature: Variables
exl-id: d66b757e-b39f-4b6e-9999-6fbde87505af
source-git-commit: b8640d1387a475e2a9dd082759f0514bd18c1b6e
workflow-type: tm+mt
source-wordcount: '925'
ht-degree: 3%

---

# Plug-in di Adobe: rfl (Rimuovi dall&#39;elenco)

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting per aiutarti a ottenere più valore da Adobe Analytics. Adobe L’Assistenza clienti non fornisce supporto con questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di assistenza su questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare un incontro con un consulente per ricevere assistenza.

Il `rfl` Il plug-in consente di rimuovere &quot;in modo sicuro&quot; i valori dalle stringhe delimitate, ad esempio [`events`](../page-vars/events/events-overview.md), [`products`](../page-vars/products.md), [`list`](../page-vars/list.md), e altri. Questo plug-in è utile se si desidera rimuovere valori specifici da una stringa delimitata senza preoccuparsi dei delimitatori. Diversi altri plug-in dipendono da questo codice per funzionare correttamente. Questo plug-in non è necessario se non è necessario eseguire una funzione specifica su più variabili Analytics alla volta o se non si utilizzano plug-in dipendenti.

Il plug-in utilizza la logica seguente:

* Se il valore da rimuovere esiste, il plug-in mantiene tutto nella variabile, tranne il valore da rimuovere.
* Se il valore da rimuovere non esiste, il plug-in mantiene invariata la stringa originale.

<!--## Install the plug-in using the Web SDK or the Adobe Analytics extension

Adobe offers an extension that allows you to use most commonly-used plug-ins.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the desired tag property.
1. Go to the [!UICONTROL Extensions] tab, then click on the [!UICONTROL Catalog] button
1. Install and publish the [!UICONTROL Common Analytics Plugins] extension
1. If you haven't already, create a rule labeled "Initialize Plug-ins" with the following configuration:
    * Condition: None
    * Event: Core – Library Loaded (Page Top)
1. Add an action to the above rule with the following configuration:
    * Extension: Common Analytics Plugins
    * Action Type: Initialize RFP (Remove From List)
1. Save and publish the changes to the rule.-->

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione del plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi [!UICONTROL Configure tracking using custom code] Pannello a soffietto, che mostra [!UICONTROL Open Editor] pulsante.
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell’istanza dell’oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). Mantenere i commenti e i numeri di versione del codice nella tua implementazione aiuta ad Adobe nella risoluzione di eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: rfl (removeFromList) v2.1  */
function rfl(lv,vr,d1,d2,df){var b=lv,f=vr,e=d1,h=d2,g=df;if("-v"===b)return{plugin:"rfl",version:"2.1"};a:{if("undefined"!==typeof window.s_c_il){var c=0;for(var a;c<window.s_c_il.length;c++)if(a=window.s_c_il[c],a._c&&"s_c"===a._c){c=a;break a}}c=void 0}"undefined"!==typeof c&&(c.contextData.rfl="2.1");if(!b||!f)return"";c=[];a="";e=e||",";h=h||e;g=g||!1;b=b.split(e);e=b.length;for(var d=0;d<e;d++)-1<b[d].indexOf(":")&&(a=b[d].split(":"),a[1]=a[0]+":"+a[1],b[d]=a[0]),-1<b[d].indexOf("=")&&(a=b[d].split("="),a[1]=a[0]+"="+a[1],b[d]=a[0]),b[d]!==f&&a?c.push(a[1]):b[d]!==f?c.push(b[d]):b[d]===f&&g&&(a?c.push(a[1]):c.push(b[d]),g=!1),a="";return c.join(h)};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

Il `rfl` La funzione utilizza i seguenti argomenti:

* **`lv`** (obbligatorio, stringa): variabile (o stringa) contenente un elenco di valori delimitati
* **`vr`** (obbligatorio, stringa): valore che si desidera rimuovere dal `lv` argomento. L&#39;Adobe consiglia di non rimuovere più valori durante una singola `rfl` chiamare.
* **`d1`** (facoltativo, stringa): delimitatore utilizzato dalla proprietà `lv` utilizza. Impostazione predefinita: virgola (`,`).
* **`d2`** (facoltativo, stringa): delimitatore che si desidera utilizzare per la stringa restituita. Valore predefinito dello `d1` argomento.
* **`df`** (facoltativo, booleano): If `true`, forza solo le istanze duplicate del `vr` argomento da `lv` invece di tutte le istanze. Impostazione predefinita `false` quando non è impostato.

La chiamata di questa funzione restituisce una stringa modificata contenente `lv` ma senza alcuna istanza (o istanze duplicate) del valore specificato in `vr` argomento.

## Esempio di chiamate

### Esempio di #1

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

### Esempio di #2

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

### Esempio di #3

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

Se `lv` argomento o `vr` sono vuoti in un `rfl` effettua una chiamata, quindi il plug-in non restituisce nulla.

### Esempio di #4

Se viene mostrato...

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

...ma il valore finale di s.eVar 5 sarà:

```js
s.eVar5 = "hello|today";
```

Tieni presente che il plug-in restituisce solo un valore; in realtà non &quot;reimposta&quot; la variabile trasmessa attraverso il `lv` argomento.

### Esempio di #5

Se viene mostrato...

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

Assicurarsi di impostare `d1` nei casi in cui `lv` il valore dell&#39;argomento contiene un delimitatore diverso dal valore predefinito (ovvero virgola).

### Esempio di #6

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

Anche se questo esempio non è pratico, dimostra la necessità di trasmettere valori con distinzione tra maiuscole e minuscole.

### Esempio di #7

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

### Esempio di #8

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

Quando devi rimuovere un evento che utilizza la serializzazione e/o la sintassi numerica/valuta, devi specificare solo l’evento stesso (ovvero senza i valori di serializzazione/numerica/valuta) nel `rfl` chiamare.

### Esempio di #9

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

### Esempio di #10

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

### Esempio di #11

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

### Esempio di #12

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

Impostazione di più valori in `vr` non è supportato. Il `rfl` nell’esempio precedente suddividerebbe prima i valori nella sezione `lv` (es. s.events), quindi prova a far corrispondere ogni valore delimitato con il valore completo `vr` valore argomento (ad es. `"event23,event24"`).

### Esempio di #13

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

Ogni valore da rimuovere dall’elenco deve essere contenuto nel proprio `rfl` chiamare.

### Esempio di #14

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

Gli ultimi tre argomenti (ad esempio &quot;,&quot;,&quot;,&quot;,false) alla fine di questo `rfl` Le chiamate di non sono necessarie, ma non causano alcun &quot;danno&quot; in quanto sono presenti in quanto corrispondono alle impostazioni predefinite.

### Esempio di #15

Se viene mostrato...

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

Anche in questo caso, ricorda che il plug-in restituisce solo un valore; in realtà non &quot;reimposta&quot; la variabile trasmessa attraverso il `lv` argomento.

## Cronologia versioni

### 2.1 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 2.01 (17 settembre 2019)

* Correzione di bug minori per il valore delimitatore predefinito

### 2.0 (16 aprile 2018)

* Versione a punti (ricompilata, con codice di dimensioni inferiori).
* È stata eliminata la necessità di `join` plug-in.

### 1.0 (18 luglio 2016)

* Versione iniziale.
