---
title: Migrazione ad AppMeasurement per JavaScript
description: Determina cosa è necessario per migrare l'implementazione di H Code.
feature: Implementation Basics
exl-id: ed606ab4-bd7d-4871-baa1-77e30fdd419e
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 3%

---

# Migrazione ad AppMeasurement per JavaScript

Se l’implementazione utilizza ancora il codice H, Adobe consiglia vivamente di eseguire la migrazione all’ultima versione di AppMeasurement. Implementazione di Analytics tramite [tag in Adobe Experience Platform](../launch/overview.md) è consigliato, tuttavia è possibile utilizzare un’implementazione JavaScript aggiornata.

In AppMeasurement sono presenti le seguenti modifiche importanti rispetto al codice H:

* 3-7 volte più veloce del codice H.
* Più leggero del codice H - 21 kb non compresso rispetto al codice H, che è 33 kb non compresso.
* La libreria e il codice della pagina possono essere distribuiti all&#39;interno della `<head>` tag .
* Il codice H esistente a livello di pagina è compatibile con AppMeasurement.
* La libreria fornisce utility native per ottenere parametri di query, cookie di lettura e scrittura ed eseguire il tracciamento avanzato dei collegamenti.
* La libreria non supporta le variabili di configurazione dell’account dinamico (tra cui `dynamicAccountSelection`, `dynamicAccountMatch`e `dynamicAccountList`).

I passaggi seguenti delineano un flusso di lavoro di migrazione tipico.

1. **Scarica il nuovo file AppMeasurement**: Accedi al nuovo file accedendo ad Adobe Analytics, quindi vai a Amministratore > Tutti gli amministratori > Gestione codici. Il file compresso scaricato contiene un `AppMeasurement.js` , insieme ai moduli Media e Integrate .
1. **Copia il `s_code.js` personalizzazioni a`AppMeasurement.js`**: Sposta tutto il codice prima della `DO NOT ALTER ANYTHING BELOW THIS LINE` sezione `s_code.js` all&#39;inizio di `AppMeasurement.js`.
1. **Aggiorna tutti i plug-in**: Assicurati di utilizzare la versione più recente di ogni plug-in elencato nella `s_code.js` file. Questo passaggio include i moduli Media e Integrazione .
1. **Distribuire il file AppMeasurement.js**: Carica il `AppMeasurement.js` al server web.
1. **Aggiorna i riferimenti di script per puntare a`AppMeasurement.js`**: Assicurati che tutti i riferimenti alle pagine `AppMeasurement.js` anziché `s_code.js`.

## Esempio di codice Appmeasurement

Tipico `AppMeasurement.js` file. Assicurati che le variabili di configurazione siano impostate sopra la variabile `doPlugins` funzione .

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

Assicurati di aver incluso anche un riferimento a `AppMeasurement.js` e `VisitorAPI.js` su ogni pagina. Vedi [Implementazione JavaScript](/help/implement/js/overview.md) per ulteriori informazioni.
