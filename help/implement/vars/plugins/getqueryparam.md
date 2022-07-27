---
title: getQueryParam
description: Estrai il valore del parametro della stringa di query di un URL.
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
source-git-commit: 7c7a7d8add9edb1538df12b440bc0a15f09efe5e
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 1%

---

# Plug-in di Adobe: getQueryParam

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

La `getQueryParam` il plug-in consente di estrarre il valore di qualsiasi parametro della stringa di query contenuto in un URL. È utile per estrarre i codici della campagna, sia interni che esterni, dagli URL della pagina di destinazione. È utile anche per l’estrazione dei termini di ricerca o di altri parametri della stringa di query.

Questo plug-in fornisce solide funzioni per l’analisi di URL complessi, tra cui hash e URL contenenti più parametri di stringa di query. Se hai solo esigenze di parametri di stringa di query semplici, Adobe consiglia di utilizzare le funzionalità dei parametri URL utilizzando l’SDK per web o l’estensione Adobe Analytics o [`Util.getQueryParam()`](../functions/util-getqueryparam.md) incluso in AppMeasurement.

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
    * Action Type: Initialize getQueryParam
1. Save and publish the changes to the rule.-->

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getQueryParam` La funzione utilizza i seguenti argomenti:

* **`qsp`** (obbligatorio): Elenco delimitato da virgole dei parametri della stringa di query da cercare all’interno dell’URL. Non fa distinzione tra maiuscole e minuscole.
* **`de`** (facoltativo): Il delimitatore da utilizzare se più parametri della stringa di query corrispondono. Impostazione predefinita di una stringa vuota.
* **`url`** (facoltativo): Un URL personalizzato, una stringa o una variabile da cui estrarre i valori dei parametri della stringa di query. Predefinito su `window.location`.

Una chiamata a questa funzione restituisce un valore a seconda degli argomenti di cui sopra e dell&#39;URL:

* Se non viene trovato un parametro della stringa di query corrispondente, la funzione restituisce una stringa vuota.
* Se viene trovato un parametro della stringa di query corrispondente, la funzione restituisce il valore del parametro della stringa di query.
* Se viene trovato un parametro della stringa di query corrispondente ma il valore è vuoto, la funzione restituisce `true`.
* Se vengono trovati più parametri di stringa di query corrispondenti, la funzione restituisce una stringa con ogni valore di parametro delimitato dalla stringa nel `de` argomento.

## Esempi

```js
// Given the URL https://example.com/?cid=trackingcode
// Sets the campaign variable to "trackingcode"
s.campaign = getQueryParam('cid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode:123"
s.campaign = getQueryParam('cid,ecid',':');

// Given the URL https://example.com/?cid=trackingcode&ecid=123
// Sets the campaign variable to "trackingcode123"
s.campaign = getQueryParam('cid,ecid');

// Given the URL https://example.com/?cid=trackingcode&ecid=123#location
// Sets the campaign variable to "123"
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com/#location&cid=trackingcode&ecid=123
// Sets the campaign variable to "123"
// The plug-in replaces the URL's hash character with a question mark if a question mark doesn't exist.
s.campaign = getQueryParam('ecid');

// Given the URL https://example.com
// Does not set the campaign variable to a value.
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid');

// Given the URL https://example.com
// Sets the campaign variable to "trackingcode"
s.pageURL = "https://example.com/?cid=trackingcode";
s.campaign = getQueryParam('cid','',s.pageURL);

// Given the URL https://example.com
// Sets eVar2 to "123|trackingcode|true|300"
s.eVar1 = "https://example.com/?cid=trackingcode&ecid=123#location&pos=300";
s.eVar2 = getQueryParam('ecid,cid,location,pos','|',s.eVar1);
```

## Cronologia versioni

### 4.0.1 (26 marzo 2021)

* È stato aggiornato il problema per cui veniva restituito undefined invece di &quot;&quot; se il parametro di query non era presente nella stringa query.

### 4.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.
* Sono state rimosse le dipendenze dal plug-in pt.

### 3.3 (24 settembre 2019)

* È stata ignorata una logica non necessaria per ridurre la dimensione del codice

### 3.2 (15 maggio 2018)

* Spostato `findParameterValue` e `getParameterValue` nelle funzioni `getQueryParam` Funzione

### 3.1 (10 maggio 2018)

* È stato risolto un problema relativo all’acquisizione di parametri di stringa di query senza valore

### 3.0 (16 aprile 2018)

* Rilascio del punto (ricompilato, dimensioni del codice più piccole).
* Funzioni helper rinominate in `findParameterValue` e `getParameterValue` a fini di leggibilità.
* È stata rimossa la necessità di aggiungere un argomento per trovare i parametri contenuti nell’hash dell’URL

### 2.5 (8 gennaio 2016)

* Compatibile sia con codice H che con AppMeasurement (richiesto) `s.pt` con AppMeasurement).

### 2,4

* È stato aggiunto il `h` , che consente al codice di trovare i parametri della stringa di query trovati dopo l’hash (`#`) carattere

### 2.3.

* È stato risolto un problema di regressione a causa del quale il plug-in funzionava solo quando l’hash era presente dopo il codice di tracciamento

### 2.2.

* Rimuove ora i caratteri hash (e tutti gli elementi successivi) dal valore restituito

### 2.1

* Compatibile con il codice H.10
