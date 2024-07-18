---
title: getQueryParam
description: Estrai il valore del parametro della stringa di query di un URL.
feature: Variables
exl-id: d2d542d1-3a18-43d9-a50d-c06d8bd473b8
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 7%

---

# Plug-in di Adobe: getQueryParam

{{plug-in}}

Il plug-in `getQueryParam` consente di estrarre il valore di qualsiasi parametro di stringa di query contenuto in un URL. È utile per estrarre i codici campagna, sia interni che esterni, dagli URL della pagina di destinazione. È utile anche quando si estraggono termini di ricerca o altri parametri di stringa di query.

Questo plug-in fornisce funzioni affidabili per l’analisi di URL complessi, inclusi hash e URL contenenti più parametri di stringhe di query. Se hai solo bisogno di parametri di stringa di query semplici, Adobe consiglia di utilizzare le funzioni per parametri URL tramite Web SDK o l&#39;estensione Adobe Analytics o il metodo [`Util.getQueryParam()`](../functions/util-getqueryparam.md) incluso in AppMeasurement.

## Installare il plug-in utilizzando l’estensione Web SDK

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fare clic su **[!UICONTROL Tags]** a sinistra, quindi fare clic sulla proprietà tag desiderata.
1. Fai clic su **[!UICONTROL Extensions]** a sinistra, quindi sulla scheda **[!UICONTROL Catalog]**
1. Individuare e installare l&#39;estensione **[!UICONTROL Common Web SDK Plugins]**.
1. Fai clic su **[!UICONTROL Data Elements]** a sinistra, quindi sull&#39;elemento dati desiderato.
1. Imposta il nome dell’elemento dati desiderato con la seguente configurazione:
   * Estensione: Common Web SDK Plugins
   * Elemento dati: `getQueryParam`
1. Imposta i parametri desiderati a destra.
1. Salva e pubblica le modifiche apportate all’elemento dati.

## Installare manualmente il plug-in implementando Web SDK

Questo plug-in non è ancora supportato per l’utilizzo in un’implementazione manuale dell’SDK per web.

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
   * Tipo azione: inizializzare getQueryParam
1. Salva e pubblica le modifiche apportate alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandere il pannello a soffietto [!UICONTROL Configure tracking using custom code], che mostra il pulsante [!UICONTROL Open Editor].
1. Apri l’editor di codice personalizzato e incolla il codice del plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche nell’estensione Analytics.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getQueryParam v4.0.1  */
function getQueryParam(a,d,f){function n(g,c){c=c.split("?").join("&");c=c.split("#").join("&");var e=c.indexOf("&");if(g&&(-1<e||c.indexOf("=")>e)){e=c.substring(e+1);e=e.split("&");for(var h=0,p=e.length;h<p;h++){var l=e[h].split("="),q=l[1];if(l[0].toLowerCase()===g.toLowerCase())return decodeURIComponent(q||!0)}}return""}if("-v"===a)return{plugin:"getQueryParam",version:"4.0.1"};var b=function(){if("undefined"!==typeof window.s_c_il)for(var g=0,c;g<window.s_c_il.length;g++)if(c=window.s_c_il[g],c._c&&"s_c"===c._c)return c}();"undefined"!==typeof b&&(b.contextData.getQueryParam="4.0");if(a){d=d||"";f=(f||"undefined"!==typeof b&&b.pageURL||location.href)+"";(4<d.length||-1<d.indexOf("="))&&f&&4>f.length&&(b=d,d=f,f=b);b="";for(var m=a.split(","),r=m.length,k=0;k<r;k++)a=n(m[k],f),"string"===typeof a?(a=-1<a.indexOf("#")?a.substring(0,a.indexOf("#")):a,b+=b?d+a:a):b=""===b?a:b+(d+a);return b}};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `getQueryParam` utilizza i seguenti argomenti:

* **`qsp`** (obbligatorio): elenco delimitato da virgole di parametri della stringa di query da cercare all&#39;interno dell&#39;URL. Non fa distinzione tra maiuscole e minuscole.
* **`de`** (facoltativo): delimitatore da utilizzare se più parametri della stringa di query corrispondono. Impostazione predefinita: stringa vuota.
* **`url`** (facoltativo): URL personalizzato, stringa o variabile da cui estrarre i valori dei parametri della stringa di query. Predefinito su `window.location`.

La chiamata di questa funzione restituisce un valore che dipende dagli argomenti di cui sopra e dall’URL:

* Se non viene trovato un parametro di stringa di query corrispondente, la funzione restituisce una stringa vuota.
* Se viene trovato un parametro di stringa di query corrispondente, la funzione restituisce il valore del parametro della stringa di query.
* Se viene trovato un parametro di stringa di query corrispondente ma il valore è vuoto, la funzione restituisce `true`.
* Se vengono trovati più parametri di stringa di query corrispondenti, la funzione restituisce una stringa con ogni valore di parametro delimitato dalla stringa nell&#39;argomento `de`.

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

* È stato aggiornato un problema a causa del quale veniva restituito un valore non definito invece di &quot;&quot; se il parametro di query non era presente nella stringa di query.

### 4.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.
* Dipendenze rimosse dal plug-in `pt`.

### 3.3 (24 settembre 2019)

* Ignorata la logica non necessaria per ridurre la dimensione del codice

### 3.2 (15 maggio 2018)

* Ha spostato `findParameterValue` e `getParameterValue` funzioni nella funzione `getQueryParam`

### 3.1 (10 maggio 2018)

* È stato risolto un problema relativo all’acquisizione di parametri della stringa di query senza valore

### 3.0 (16 aprile 2018)

* Versione a punti (ricompilata, con codice di dimensioni inferiori).
* Le funzioni helper sono state rinominate `findParameterValue` e `getParameterValue` a scopo di leggibilità.
* È stata rimossa la necessità di aggiungere un argomento per trovare i parametri contenuti nell’hash URL

### 2.5 (8 gennaio 2016)

* Compatibile sia con codice H che con AppMeasurement (richiede `s.pt` con AppMeasurement).

### 2,4

* È stato aggiunto il parametro `h`, che consente al codice di trovare i parametri della stringa di query trovati dopo il carattere hash (`#`)

### 2,3

* È stato risolto un problema di regressione a causa del quale il plug-in funzionava solo quando l’hash era presente dopo il codice di tracciamento

### 2,2

* Ora rimuove i caratteri hash (e tutto ciò che segue) dal valore restituito

### 2,1

* Compatibile con il codice H.10
