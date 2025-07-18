---
title: getPercentPageViewed
description: Recupera la percentuale della pagina visualizzata dal visitatore.
feature: Appmeasurement Implementation
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '750'
ht-degree: 4%

---

# Plug-in Adobe: getPercentPageViewed

{{plug-in}}

Il plug-in `getPercentPageViewed` misura l&#39;attività di scorrimento di un visitatore per vedere quanta pagina viene visualizzata prima di passare a un&#39;altra pagina. Questo plug-in non è necessario se le pagine sono di piccole dimensioni o se non si desidera misurare l&#39;attività di scorrimento.

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
   * Tipo azione: inizializzare getPercentPageViewed
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
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizzare il plug-in

La funzione `getPercentPageViewed` utilizza i seguenti argomenti:

* **`pid`** (facoltativo, stringa): variabile o valore uguale alla pagina corrente. Impostazione predefinita della variabile Analytics AppMeasurement `pageName` OPPURE dell&#39;URL corrente se la variabile pageName di AppMeasurement non è impostata.
* **`ch`** (facoltativo, booleano): impostalo su `false` (o `0`) se non vuoi che il plug-in tenga conto di eventuali modifiche apportate alle dimensioni di una pagina dopo il suo caricamento iniziale. Se omesso, l&#39;impostazione predefinita di questo argomento sarà `true`. Nella maggior parte dei casi, Adobe consiglia di omettere questo argomento.

La chiamata di questa funzione non restituisce alcun risultato, ma imposta le seguenti variabili:

* `window._ppvPreviousPage`: nome della pagina precedente visualizzata. Le misurazioni di scorrimento finali per la pagina corrente sono disponibili solo dopo il caricamento di una nuova pagina.
* `window._ppvInitialPercentViewed`: percentuale della pagina precedente visibile al primo caricamento della pagina precedente. Se l&#39;intera pagina è visibile al primo caricamento, il valore è `100`.
* `window._ppvHighestPercentViewed`: la percentuale più alta della pagina precedente visualizzata dal visitatore (in altezza). Il punto più lontano a cui il visitatore è sceso nella pagina precedente. Se l&#39;intera pagina è visibile al primo caricamento, il valore è `100`.
* `window._ppvFinalPercentViewed`: la percentuale della pagina precedente visibile nel punto in cui il visitatore si è spostato sulla pagina corrente. Questo valore sarà uguale o maggiore della percentuale iniziale visualizzata e sarà uguale o inferiore alla percentuale più elevata visualizzata nella pagina.
* `window._ppvHighestPixelsSeen`: numero massimo di pixel totali visualizzati (in altezza) mentre il visitatore scorreva la pagina precedente.
* `window._ppvFoldsAvailable`: numero totale di &quot;pieghe di pagina&quot; disponibili per lo scorrimento verso il basso nella pagina precedente. Se l&#39;intera pagina è visibile al primo caricamento, il valore è `1`.
* `window._ppvFoldsSeen`: è stato raggiunto il numero massimo di &quot;pieghe di pagina&quot; con lo scorrimento verso il basso della pagina precedente. Questa variabile include la piega &quot;superiore della pagina&quot;. Se l&#39;intera pagina è visibile al primo caricamento, il valore è `1`.

Assegna una o più di queste variabili alle eVar per visualizzare i dati delle dimensioni nei rapporti.

Questo plug-in crea tre cookie di prime parti che scadono al termine di una sessione del browser:

* `s_ppv`: memorizza ciascuno dei valori esposti chiamando la funzione
* `s_tp`: memorizza l&#39;altezza totale in pixel della pagina precedente
* `s_ips`: memorizza la percentuale iniziale di scorrimento della pagina precedente

## Esempi

```js
// 1. Runs the getPercentPageViewed function if the page variable is set
// 2. Sets prop1 to the previous value of the page variable
// 3. Sets prop2 to the intial percent, the highest percent, and the final percent viewed; the number of folds available on the page, and the number of folds viewed ( of the previous page)
if(s.pageName) getPercentPageViewed();
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed + " | finalPercent=" + _ppvFinalPercentViewed + " | foldsAvailable=" + _ppvFoldsAvailable + " | foldsSeen=" + _ppvFoldsSeen;
}

// Given prop5 operates as a page type variable:
// 1. Runs the getPercentPageViewed function if prop5 has a value
// 2. Sets prop1 to the previous value of the page type
// 3. Sets prop2 to the initial percent viewed and the highest percent viewed.
if(s.prop5) getPercentPageViewed(s.prop5);
if(_ppvPreviousPage)
{
  s.prop1 = _ppvPreviousPage;
  s.prop2 = "initialPercent=" + _ppvInitialPercentViewed + " | highestPercent=" + _ppvHighestPercentViewed;
}
```

## Cronologia versioni

### 5.1 (8 dicembre 2022)

* Aggiunta della soluzione `_finalPercentViewed` completata

### 5.0.1 (22 giugno 2021)

* È stato risolto un problema che causava l’interruzione del plug-in a causa di alcuni caratteri speciali.

### 5.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v4.0 (7 ottobre 2019)

* Aggiunte `s._ppvFoldsSeen` e `s._ppvFoldsAvailable` soluzioni

### v3.01 (13 agosto 2018)

* È stato risolto un problema relativo alle pagine che hanno più oggetti AppMeasurement in una pagina

### v3.0 (13 aprile 2018)

* Versione a punti (ricompilata, con codice di dimensioni inferiori)
* Il plug-in ora crea variabili da assegnare alle variabili di Adobe Analytics invece di valori restituiti.
