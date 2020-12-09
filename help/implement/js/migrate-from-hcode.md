---
title: Migrazione ad AppMeasurement per JavaScript
description: Determinare gli elementi necessari per migrare l'implementazione di H Code.
translation-type: tm+mt
source-git-commit: 09b453c1b4cd8555c5d1718759003945f5c230c5
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 3%

---


# Migrazione ad AppMeasurement per JavaScript

Se l&#39;implementazione utilizza ancora il codice H,  Adobe consiglia vivamente di migrare all&#39;ultima versione di AppMeasurement. È consigliabile implementare Analytics tramite [Adobe Experience Platform Launch](../launch/overview.md) , tuttavia è possibile utilizzare un&#39;implementazione JavaScript aggiornata.

In AppMeasurement sono presenti le seguenti modifiche importanti confrontate con il Codice H:

* 3-7x più veloce del codice H.
* Più leggero del codice H - 21 kb non compresso rispetto al codice H, che è 33 kb non compresso.
* La libreria e il codice della pagina possono essere distribuiti all&#39;interno del `<head>` tag .
* Il codice H a livello di pagina esistente è compatibile con AppMeasurement.
* La libreria fornisce utility native per ottenere parametri di query, cookie di lettura e scrittura ed eseguire il tracciamento avanzato dei collegamenti.
* La libreria non supporta le variabili di configurazione dell&#39;account dinamico (incluse `dynamicAccountSelection`, `dynamicAccountMatch`e `dynamicAccountList`).

Nei passaggi seguenti viene delineato un flusso di lavoro di migrazione tipico.

1. **Scarica il nuovo file** AppMeasurement: Per accedere al nuovo file, accedi a  Adobe Analytics, quindi passa ad Admin > Code Manager (Amministratore > Gestione codici). Il file compresso scaricato contiene un `AppMeasurement.js` file ridotto, insieme ai moduli Media e Integrate.
1. **Copiate `s_code.js` le personalizzazioni in`AppMeasurement.js`**: Sposta tutto il codice prima della `DO NOT ALTER ANYTHING BELOW THIS LINE` sezione `s_code.js` all&#39;inizio di `AppMeasurement.js`.
1. **Aggiorna tutti i plug-in**: Accertatevi di utilizzare la versione più recente di ciascun plug-in elencato nel `s_code.js` file. Sono inclusi i moduli Media e Integrate.
1. **Distribuisci il file** AppMeasurement.js: Caricate il `AppMeasurement.js` file sul server Web.
1. **Aggiorna i riferimenti di script per puntare a`AppMeasurement.js`**: Accertatevi che tutti i riferimenti alle pagine siano `AppMeasurement.js` invece di `s_code.js`.

## Esempio di codice Appmeasurement

Un `AppMeasurement.js` file tipico. Verificate che le variabili di configurazione siano impostate al di sopra della `doPlugins` funzione.

```js
// Initialize AppMeasurement
var s = s_gi("examplersid");

/******** VISITOR ID SERVICE CONFIG - REQUIRES VisitorAPI.js ********/;
s.visitor=Visitor.getInstance("INSERT-MCORG-ID-HERE");

/************************** CONFIG SECTION **************************/;
/* You may add or alter any code config here. */
s.trackDownloadLinks = true;
s.trackExternalLinks = true;
s.trackInlineStats = true;
s.linkDownloadFileTypes = "exe,zip,wav,mp3,mov,mpg,avi,wmv,pdf,doc,docx,xls,xlsx,ppt,pptx";
s.linkInternalFilters = "javascript:,example.com";

s.usePlugins = true;
function s_doPlugins(s) {

// Use implementation plug-ins that are defined below in this section

}
s.doPlugins = s_doPlugins;

/* WARNING: Changing any of the below variables will cause drastic
changes to how your visitor data is collected.  Changes should only be
made when instructed to do so by your account manager.*/
s.trackingServer="example.data.adobedc.net";

/************************** PLUGINS SECTION *************************/

// Copy and paste implementation plug-ins here. Plug-ins can then be used in the s_doPlugins(s) function above

/****************************** MODULES *****************************/

// Copy and paste implementation modules (Media, Integrate) here.

/* ============== DO NOT ALTER ANYTHING BELOW THIS LINE ! ===============  */
```

## Esempio di codice della pagina

Codice tipico che viene caricato su ogni pagina.

```html
<script src="AppMeasurement.js"></script>
<script language="JavaScript" type="text/javascript">
s.pageName = "Example page name";
s.eVar1 = "Example eVar value";
s.events = "event1";
s.t();
</script>
```

Accertatevi di aver incluso anche un riferimento a `AppMeasurement.js` e `VisitorAPI.js` su ciascuna pagina. Per ulteriori informazioni, consultate Implementazione [](/help/implement/js/overview.md) JavaScript.
