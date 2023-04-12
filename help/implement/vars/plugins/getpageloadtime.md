---
title: getPageLoadTime
description: Tieni traccia del tempo necessario al caricamento di una pagina.
feature: Variables
exl-id: 9bf0e26b-f1af-48a6-900a-712f7e588d37
source-git-commit: bbb138d979968ec2536e53ff07001b43156df095
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 7%

---

# Plug-in di Adobe: getPageLoadTime

{{plug-in}}

La `getPageLoadTime` Il plug-in utilizza l&#39;oggetto prestazioni JavaScript per consentire di misurare il tempo necessario al caricamento completo di una pagina. Adobe consiglia di utilizzare questo plug-in per misurare il tempo di caricamento delle pagine.

>NOTA/AVVISO: Se stai aggiornando questo plug-in da una versione precedente, molto probabilmente dovrai modificare anche il codice che chiama questa funzione.  Controlla l&#39;implementazione e verifica accuratamente prima dell&#39;implementazione in produzione

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
   * Tipo azione: Inizializza getPageLoadTime
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
/* Adobe Consulting Plugin: getPageLoadTime v3.0 */
!function(){let e=globalThis.window||this;e.getPageLoadTime=function(t){let i=function(){if(e.s_c_il){for(let t in e.s_c_il)if("s_c"===e.s_c_il[t]._c)return e.s_c_il[t]}}();function n(){var i=performance.timing;i.loadEventEnd>0&&(clearInterval(e.pi),""===e.cookieRead("s_plt")&&e.cookieWrite("s_plt",function e(t,i){if(t>=0&&i>=0)return t-i<6e4&&t-i>=0?parseFloat((t-i)/1e3).toFixed(2):60}(i.loadEventEnd,i.navigationStart)+","+t)),e.ptc=i.loadEventEnd}if(i&&(i.contextData.getPageLoadTime="3.1"),t=t||i&&i.pageName||document.location.href,e.cookieWrite=e.cookieWrite||function(t,i,n){if("string"==typeof t){if(g=function(){var t=e.location.hostname,i=e.location.hostname.split(".").length-1;if(t&&!/^[0-9.]+$/.test(t)){i=2<i?i:2;var n=t.lastIndexOf(".");if(0<=n){for(;0<=n&&1<i;)n=t.lastIndexOf(".",n-1),i--;n=0<n?t.substring(n):t}}return n}(),i=void 0!==i?""+i:"",n||""===i){if(""===i&&(n=-60),"number"==typeof n){var o=new Date;o.setTime(o.getTime()+6e4*n)}else o=n}return!!t&&(document.cookie=encodeURIComponent(t)+"="+encodeURIComponent(i)+"; path=/;"+(n?" expires="+o.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!=typeof cookieRead)&&cookieRead(t)===i}},e.cookieRead=e.cookieRead||function(e){if("string"!=typeof e)return"";e=encodeURIComponent(e);var t=" "+document.cookie,i=t.indexOf(" "+e+"="),n=0>i?i:t.indexOf(";",i);return(e=0>i?"":decodeURIComponent(t.substring(i+2+e.length,0>n?t.length:n)))?e:""},e.p_fo=e.p_fo||function(t){return e.__fo||(e.__fo={}),!e.__fo[t]&&(e.__fo[t]={},!0)},performance&&e.p_fo("performance")){var o=performance;o.clearResourceTimings(),""!==e.cookieRead("s_plt")&&(o.timing.loadEventEnd>0&&clearInterval(e.pi),this._pltLoadTime=e.cookieRead("s_plt").split(",")[0],this._pltPreviousPage=e.cookieRead("s_plt").split(",")[1],e.cookieWrite("s_plt","")),0===o.timing.loadEventEnd?e.pi=setInterval(function(){n()},250):o.timing.loadEventEnd>0&&(e.ptc?e.ptc===o.timing.loadEventEnd&&1===o.getEntries().length&&(e.pwp=setInterval(function(){var i;(i=performance).getEntries().length>0&&(e.ppfe===i.getEntries().length?clearInterval(e.pwp):e.ppfe=i.getEntries().length),""===e.cookieRead("s_plt")&&e.cookieWrite("s_plt",((i.getEntries()[i.getEntries().length-1].responseEnd-i.getEntries()[0].startTime)/1e3).toFixed(2)+","+t)},500)):n())}},e.getPageLoadTime.getVersion=function(){return{plugin:"getPageLoadTime",version:"3.0"}}}();
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getPercentPageViewed` La funzione utilizza i seguenti argomenti:

* **`pv`** (facoltativo, stringa): Dimensione con cui correlare il tempo di caricamento della pagina.  Questo valore deve essere uguale a un valore che identifica la pagina stessa. Se non è impostato, questo argomento viene impostato automaticamente sulla variabile pageName di Adobe AppMeasurement (cioè s.pageName) o sull&#39;URL quando s.pageName non è impostato

La chiamata di questa funzione non restituisce nulla; imposta invece le seguenti variabili:

* `window._pltPreviousPage`: Il valore della pagina precedente (ovvero ciò che è stato passato nell’argomento pv)
* `window._pltLoadTime`: Tempo in secondi necessario al caricamento della pagina precedente

Il plug-in getPageLoadTime crea un cookie di prima parte:

* `s_plt`: Tempo, in secondi, necessario per caricare la pagina precedente.  Contiene anche il valore di ciò che è stato passato nell&#39;argomento pv.  Scade alla fine della sessione del browser.

## Esempio

```js
// 1. Run the getPageLoadTime function if the pageName variable is set
// 2. Set prop10 to the load time of the previous page
// 3. Set eVar10 to the name of the previous page
// 4. Set event100 to the load time (in seconds) of the previous page. A numeric event is required to capture this value.
// You can then use event100 in calculated metrics to obtain the average page load time per page.
if(s.pageName) getPageLoadTime();
if(window._pltPreviousPage)
{
  s.prop10 = window._pltLoadTime;
  s.eVar10 = window._pltPreviousPage
  s.events = "event100=" + window._pltLoadTime;
}
```

## Cronologia versioni

### 3.0 (6 dicembre 2022)

* Riscrittura completa del plug-in per renderlo indipendente dalla soluzione.  Ad esempio, questo è ora compatibile con AEP Web SDK
* Crea la `_pltPreviousPage` e `_pltLoadTime` variabili nell&#39;oggetto finestra (anziché nell&#39;oggetto AppMeasurement s)
* Rimuove la necessità del cookie s_pltp: tutto è ora memorizzato solo nel cookie s_plt
* Include la funzione getVersion per facilitare la risoluzione dei problemi

### 2.0.1 (26 marzo 2021)

* È stato corretto un problema a causa del quale il plug-in non impostava correttamente i valori sull’oggetto s.

### 2.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.0 (22 maggio 2018)

* Versione iniziale.
