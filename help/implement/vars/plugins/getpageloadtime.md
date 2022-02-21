---
title: getPageLoadTime
description: Tieni traccia del tempo necessario al caricamento di una pagina.
feature: Variables
exl-id: 9bf0e26b-f1af-48a6-900a-712f7e588d37
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 1%

---

# Plug-in di Adobe: getPageLoadTime

>[!IMPORTANT]
>
>Questo plug-in è fornito da Adobe Consulting come cortesia per aiutarti a ottenere più valore da Adobe Analytics. L’Assistenza clienti di Adobe non fornisce supporto per questo plug-in, inclusa l’installazione o la risoluzione dei problemi. Se hai bisogno di aiuto con questo plug-in, contatta l’Account Manager della tua organizzazione. Possono organizzare una riunione con un consulente per l&#39;assistenza.

La `getPageLoadTime` Il plug-in utilizza l&#39;oggetto prestazioni JavaScript per consentire di misurare il tempo necessario al caricamento completo di una pagina. Adobe consiglia di utilizzare questo plug-in per misurare il tempo di caricamento delle pagine.

## Installare il plug-in utilizzando i tag in Adobe Experience Platform

Adobe offre un’estensione che consente di utilizzare i plug-in più comunemente utilizzati.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
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

Se non desideri utilizzare l&#39;estensione plug-in, puoi utilizzare l&#39;editor di codice personalizzato.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto l&#39;estensione Adobe Analytics.
1. Espandi la [!UICONTROL Configure tracking using custom code] fisarmonica, che rivela [!UICONTROL Open Editor] pulsante .
1. Apri l’editor di codice personalizzato e incolla il codice plug-in fornito di seguito nella finestra di modifica.
1. Salva e pubblica le modifiche all’estensione Analytics.

## Installare il plug-in utilizzando AppMeasurement

Copia e incolla il seguente codice in qualsiasi punto del file AppMeasurement dopo la creazione dell&#39;istanza dell&#39;oggetto di tracciamento Analytics (utilizzando [`s_gi`](../functions/s-gi.md)). La conservazione dei commenti e dei numeri di versione del codice nell’implementazione consente ad Adobe di risolvere eventuali problemi.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getPageLoadTime v2.0.1 with performanceWriteFull, performanceWritePart, performanceCheck, and performanceRead helper functions (Requires AppMeasurement and the p_fo plugin) */
function getPageLoadTime(){function l(){var a=performance.timing;if(0<a.loadEventEnd&&(clearInterval(window.pi),""===window.cookieRead("s_plt"))){var b=window,d=b.cookieWrite;var c=a.loadEventEnd;var f=a.navigationStart;c=0<=c&&0<=f?6E4>c-f&&0<=c-f?parseFloat((c-f)/1E3).toFixed(2):60:void 0;d.call(b,"s_plt",c);window.cookieWrite("s_pltp",window.pageName)}window.ptc=a.loadEventEnd}if(arguments&&"-v"===arguments[0])return{plugin:"getPageLoadTime",version:"2.0.1"};var e=function(){if("undefined"!==typeof window.s_c_il)for(var a=0,b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c)return b}();"undefined"!==typeof e&&(e.contextData.getPageLoadTime="2.0.1");window.pageName="undefined"!==typeof e&&e.pageName||"";window.cookieWrite=window.cookieWrite||function(a,b,d){if("string"===typeof a){var c=window.location.hostname,f=window.location.hostname.split(".").length-1;if(c&&!/^[0-9.]+$/.test(c)){f=2<f?f:2;var h=c.lastIndexOf(".");if(0<=h){for(;0<=h&&1<f;)h=c.lastIndexOf(".",h-1),f--;h=0<h?c.substring(h):c}}g=h;b="undefined"!==typeof b?""+b:"";if(d||""===b)if(""===b&&(d=-60),"number"===typeof d){var k=new Date;k.setTime(k.getTime()+6E4*d)}else k=d;return a&&(document.cookie=encodeURIComponent(a)+"="+encodeURIComponent(b)+"; path=/;"+(d?" expires="+k.toUTCString()+";":"")+(g?" domain="+g+";":""),"undefined"!==typeof cookieRead)?cookieRead(a)===b:!1}};window.cookieRead=window.cookieRead||function(a){if("string"===typeof a)a=encodeURIComponent(a);else return"";var b=" "+document.cookie,d=b.indexOf(" "+a+"="),c=0>d?d:b.indexOf(";",d);return(a=0>d?"":decodeURIComponent(b.substring(d+2+a.length,0>c?b.length:c)))?a:""};window.p_fo=window.p_fo||function(a){window.__fo||(window.__fo={});if(window.__fo[a])return!1;window.__fo[a]={};return!0};"undefined"!==typeof performance&&p_fo("performance")&&((e=performance,e.clearResourceTimings(),""!==window.cookieRead("s_plt")&&(0<e.timing.loadEventEnd&&clearInterval(window.pi),this._pltLoadTime=window.cookieRead("s_plt"),this._pltPreviousPage=window.cookieRead("s_pltp"),window.cookieWrite("s_plt",""),window.cookieWrite("s_pltp","")),0===e.timing.loadEventEnd)?window.pi=setInterval(function(){l()},250):0<e.timing.loadEventEnd&&(window.ptc?window.ptc===e.timing.loadEventEnd&&1===e.getEntries().length&&(window.pwp=setInterval(function(){var a=performance;0<a.getEntries().length&&(window.ppfe===a.getEntries().length?clearInterval(window.pwp):window.ppfe=a.getEntries().length);""===window.cookieRead("s_plt")&&(window.cookieWrite("s_plt",((a.getEntries()[a.getEntries().length-1].responseEnd-a.getEntries()[0].startTime)/1E3).toFixed(2)),window.cookieWrite("s_pltp",window.pageName))},500)):l()))};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Usa il plug-in

La `getPageLoadTime` La funzione non utilizza argomenti. Quando si chiama questa funzione, non restituisce alcun risultato. Imposta invece le seguenti variabili:

* `s._pltPreviousPage`: La pagina precedente per correlare il tempo di caricamento alla pagina precedente
* `s._pltLoadTime`: Tempo in secondi necessario al caricamento della pagina precedente

Il plug-in getPageLoadTime crea due cookie di prime parti:

* `s_plt`: Tempo, in secondi, necessario per caricare la pagina precedente. Scade alla fine della sessione del browser.
* `s_pltp` Il valore del `s.pageName` come registrato nella precedente richiesta immagine di Adobe Analytics. Scade alla fine della sessione del browser.

## Esempio

```js
// 1. Run the getPageLoadTime function if the pageName variable is set
// 2. Set prop10 to the load time of the previous page
// 3. Set eVar10 to the name of the previous page
// 4. Set event100 to the load time (in seconds) of the previous page. A numeric event is required to capture this value.
// You can then use event100 in calculated metrics to obtain the average page load time per page.
if(s.pageName) s.getPageLoadTime();
if(s._pltPreviousPage)
{
  s.prop10 = s._pltLoadTime;
  s.eVar10 = s._pltPreviousPage
  s.events = "event100=" + s._pltLoadTime;
}
```

## Cronologia versioni

### 2.0.1 (26 marzo 2021)

* È stato corretto un problema a causa del quale il plug-in non impostava correttamente i valori sull’oggetto s.

### 2.0 (19 marzo 2021)

* È stato aggiunto il numero di versione come dati contestuali.

### 1.0 (22 maggio 2018)

* Versione iniziale.
