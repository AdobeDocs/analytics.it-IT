---
title: getPercentPageViewed
description: Recupera la percentuale della pagina visualizzata dal visitatore.
feature: Variables
exl-id: 7a842cf0-f8cb-45a9-910e-5793849bcfb8
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 5%

---

# Plug-in di Adobe: getPercentPageViewed

{{plug-in}}

La `getPercentPageViewed` Il plug-in misura l’attività di scorrimento di un visitatore per vedere la quantità di una pagina visualizzata prima di passare a un’altra pagina. Questo plug-in non è necessario se le pagine sono di piccole dimensioni o se non desideri misurare l’attività di scorrimento.

## Installare il plug-in utilizzando l’SDK per web o l’estensione SDK per web

Questo plug-in non è ancora supportato per l&#39;utilizzo all&#39;interno dell&#39;SDK per web.

## Installare il plug-in utilizzando l’estensione Adobe Analytics

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati con Adobe Analytics.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul [!UICONTROL Catalog] pulsante
1. Installa e pubblica il [!UICONTROL Common Analytics Plugins] estensione
1. Se non lo hai già fatto, crea una regola denominata &quot;Inizializza plug-in&quot; con la seguente configurazione:
   * Condizione: nessuna
   * Evento: Core - Libreria caricata (pagina in alto)
1. Aggiungi un&#39;azione alla regola precedente con la seguente configurazione:
   * Estensione: Plug-in comuni di Analytics
   * Tipo azione: Inizializza getPercentPageViewed
1. Salva e pubblica le modifiche alla regola.

## Installare il plug-in utilizzando l’editor di codice personalizzato

Se non desideri utilizzare l’estensione del plug-in Common Analytics Plugins, puoi utilizzare l’editor di codice personalizzato.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPercentPageViewed v5.1 */
function getPercentPageViewed(pid,ch){var e=pid,i=ch;if("-v"===e)return{plugin:"getPercentPageViewed",version:"5.1"};var t=function(){if(void 0!==window.s_c_il){for(var e,i=0;i<window.s_c_il.length;i++)if((e=window.s_c_il[i])._c&&"s_c"===e._c)return e}}();function o(){if(window.ppvID){var e=Math.max(Math.max(document.body.scrollHeight,document.documentElement.scrollHeight),Math.max(document.body.offsetHeight,document.documentElement.offsetHeight),Math.max(document.body.clientHeight,document.documentElement.clientHeight)),i=window.innerHeight||document.documentElement.clientHeight||document.body.clientHeight,t=(window.pageYOffset||window.document.documentElement.scrollTop||window.document.body.scrollTop)+i,o=Math.min(Math.round(t/e*100),100),n=Math.floor(e/i),p=Math.floor(t/i),s="";if(!window.cookieRead("s_tp")||decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID)||!0==window.ppvChange&&window.cookieRead("s_tp")&&e!=window.cookieRead("s_tp")){if((decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])!==window.ppvID||window.p_fo(window.ppvID+"1"))&&window.cookieWrite("s_ips",t),window.cookieRead("s_tp")&&decodeURIComponent(window.cookieRead("s_ppv").split(",")[0])===window.ppvID){window.cookieRead("s_tp");var a=window.cookieRead("s_ppv"),c=a.indexOf(",")>-1?a.split(","):[],d=c[0]?c[0]:"",r=window.cookieRead("s_ips"),l=c[3]?c[3]:"";s=d+","+Math.round(r/e*100)+","+Math.round(l/e*100)+","+o+","+l+","+n+","+p}window.cookieWrite("s_tp",e)}else s=window.cookieRead("s_ppv");var v=s&&s.indexOf(",")>-1?s.split(",",7):[],f=v.length>0?v[0]:encodeURIComponent(window.ppvID),$=v.length>1?parseInt(v[1]):o,h=v.length>2?parseInt(v[2]):o,u=v.length>4?parseInt(v[4]):t,k=v.length>5?parseInt(v[5]):n,m=v.length>6?parseInt(v[6]):p;o>0&&(s=f+","+$+","+(o>h?o:h)+","+o+","+(t>u?t:u)+","+(n>k?n:k)+","+(p>m?p:m)),window.cookieWrite("s_ppv",s)}}void 0!==t&&(t.contextData.getPercentPageViewed="5.1"),window.pageName=void 0!==t&&t.pageName||"",window.cookieWrite=window.cookieWrite||function(e,i,t){if("string"==typeof e){if(g=function(){var e=window.location.hostname,i=window.location.hostname.split(".").length-1;if(e&&!/^[0-9.]+$/.test(e)){i=2<i?i:2;var t=e.lastIndexOf(".");if(0<=t){for(;0<=t&&1<i;)t=e.lastIndexOf(".",t-1),i--;t=0<t?e.substring(t):e}}return t}(),i=void 0!==i?""+i:"",t||""===i){if(""===i&&(t=-60),"number"==typeof t){var o=new Date;o.setTime(o.getTime()+6e4*t)}else o=t}return!!e&&(document.cookie=encodeURIComponent(e)+"="+encodeURIComponent(i)+"; path=/;"+(t?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),void 0!==window.cookieRead)&&window.cookieRead(e)===i}},window.cookieRead=window.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var i=" "+document.cookie,t=i.indexOf(" "+e+"="),o=0>t?t:i.indexOf(";",t);return(e=0>t?"":decodeURIComponent(i.substring(t+2+e.length,0>o?i.length:o)))?e:""},window.p_fo=window.p_fo||function(e){return window.__fo||(window.__fo={}),!window.__fo[e]&&(window.__fo[e]={},!0)};var n=window.cookieRead("s_ppv"),p=n.indexOf(",")>-1?n.split(","):[];p[0]=p.length>0?decodeURIComponent(p[0]):"",e=e||(window.pageName?window.pageName:document.location.href),void 0===i||!0==i?window.ppvChange=!0:window.ppvChange=!1,void 0!==t&&t.linkType&&"o"===t.linkType||(window.ppvID&&window.ppvID===e||(window.ppvID=e,window.cookieWrite("s_ppv",""),o()),window.p_fo("s_gppvLoad2")&&window.addEventListener&&(window.addEventListener("load",o,!1),window.addEventListener("click",o,!1),window.addEventListener("scroll",o,!1)),this._ppvPreviousPage=p[0]?p[0]:"",this._ppvInitialPercentViewed=p[1]?p[1]:"",this._ppvHighestPercentViewed=p[2]?p[2]:"",this._ppvFinalPercentViewed=p[3]?p[3]:"",this._ppvHighestPixelsSeen=p[4]?p[4]:"",this._ppvFoldsAvailable=p[5]?p[5]:"",this._ppvFoldsSeen=p[6]?p[6]:"")}
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getPercentPageViewed` La funzione utilizza i seguenti argomenti:

* **`pid`** (facoltativo, stringa): Variabile o valore uguale alla pagina corrente. Impostazioni predefinite per AppMeasurement di Analytics `pageName` OPPURE l&#39;URL corrente se la variabile pageName AppMeasurement non è impostata.
* **`ch`** (facoltativo, booleano): Imposta questo su `false` o `0`) se non desideri che il plug-in tenga conto di eventuali modifiche apportate alle dimensioni di una pagina dopo il caricamento iniziale. Se omesso, questo argomento viene impostato automaticamente su `true`. L&#39;Adobe consiglia di omettere questo argomento nella maggior parte dei casi.

La chiamata di questa funzione non restituisce nulla; imposta invece le seguenti variabili:

* `window._ppvPreviousPage`: Nome della pagina precedente visualizzata. Le misure di scorrimento finali per la pagina corrente non sono disponibili fino al caricamento di una nuova pagina.
* `window._ppvInitialPercentViewed`: La percentuale della pagina precedente visibile al primo caricamento della pagina precedente. Se l’intera pagina è visibile al primo caricamento, questo valore è `100`.
* `window._ppvHighestPercentViewed`: La percentuale più alta della pagina precedente visualizzata dal visitatore (in base all’altezza). Il punto più avanzato su cui il visitatore ha effettuato lo scorrimento nella pagina precedente. Se l’intera pagina è visibile al primo caricamento, questo valore è `100`.
* `window._ppvFinalPercentViewed`: La percentuale della pagina precedente visibile nel punto in cui il visitatore si è spostato sulla pagina corrente. Questo valore sarà uguale o maggiore della percentuale iniziale visualizzata e sarà anche uguale o inferiore alla percentuale più alta visualizzata.
* `window._ppvHighestPixelsSeen`: Il numero più alto di pixel totali visualizzati (in altezza) mentre il visitatore scorreva verso il basso la pagina precedente.
* `window._ppvFoldsAvailable`: Il numero di &quot;pieghe di pagina&quot; totali disponibili per scorrere verso il basso nella pagina precedente. Se l’intera pagina è visibile al primo caricamento, questo valore è `1`.
* `window._ppvFoldsSeen`: Il numero più alto di &quot;pieghe di pagina&quot; raggiunto quando il visitatore ha fatto scorrere la pagina precedente. Questa variabile include la piega &quot;inizio pagina&quot;. Se l’intera pagina è visibile al primo caricamento, questo valore è `1`.

Assegna una o più di queste variabili a eVar per visualizzare i dati delle dimensioni nei rapporti.

Questo plug-in crea un cookie di prime parti denominato `s_ppv` che contiene i valori sopra indicati. scade alla fine della sessione del browser.

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

* È stato aggiunto il `_finalPercentViewed` soluzione

### 5.0.1 (22 giugno 2021)

* È stato risolto un problema a causa del quale alcuni caratteri speciali causavano l’interruzione del plug-in.

### 5.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### v4.0 (7 ottobre 2019)

* Aggiunto `s._ppvFoldsSeen` e `s._ppvFoldsAvailable` soluzioni

### v3.01 (13 agosto 2018)

* È stato risolto un problema per le pagine che hanno più oggetti AppMeasurement in una pagina

### v3.0 (13 aprile 2018)

* Rilascio a punti (ricompilato, dimensioni del codice più piccole)
* Il plug-in ora crea variabili da assegnare alle variabili di Adobe Analytics anziché valori restituiti
