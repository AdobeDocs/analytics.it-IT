---
title: Migrazione ad AppMeasurement per JavaScript
description: Determina cosa è necessario per migrare l’implementazione dal codice H.
feature: Implementation Basics
exl-id: ed606ab4-bd7d-4871-baa1-77e30fdd419e
role: Developer
TQID: https://experienceleague.adobe.com/Ml3fp170Ggn8-lpJCvDOAMBMF1izsmrG0BAnWcS-BUo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 297
ht-degree: 0%

---

# Migrazione ad AppMeasurement per JavaScript

Se la tua implementazione utilizza ancora codice H, Adobe consiglia vivamente di migrare all’ultima versione di AppMeasurement. Si consiglia di implementare Analytics tramite [tag in Adobe Experience Platform](../launch/overview.md), tuttavia è possibile utilizzare un&#39;implementazione JavaScript aggiornata.

Rispetto al codice H, in AppMeasurement sono presenti le seguenti modifiche di rilievo:

* 3-7 volte più veloce del codice H.
* Più leggero del codice H: 21 kb non compresso rispetto al codice H, che è 33 kb non compresso.
* La libreria e il codice della pagina possono essere distribuiti all&#39;interno del tag `<head>`.
* Il codice H a livello di pagina esistente è compatibile con AppMeasurement.
* La libreria fornisce utility native per ottenere parametri di query, cookie di lettura e scrittura ed eseguire il tracciamento avanzato dei collegamenti.
* La libreria non supporta le variabili di configurazione dell&#39;account dinamico (inclusi `dynamicAccountSelection`, `dynamicAccountMatch` e `dynamicAccountList`).

I passaggi seguenti descrivono un flusso di lavoro di migrazione tipico.

1. **Scarica il nuovo file AppMeasurement**: accedi al nuovo file accedendo ad Adobe Analytics, quindi scegliendo Admin > All admin > Code manager (Amministrazione > Tutte le attività di amministrazione > Gestione codici). Il file compresso scaricato contiene un file `AppMeasurement.js` minimizzato, insieme ai moduli Media e Integrate.
1. **Copia le personalizzazioni di `s_code.js` in`AppMeasurement.js`**: sposta tutto il codice prima della sezione `DO NOT ALTER ANYTHING BELOW THIS LINE` in `s_code.js` all&#39;inizio di `AppMeasurement.js`.
1. **Aggiorna tutti i plug-in**: assicurarsi di utilizzare la versione più recente di ciascun plug-in elencato nel file `s_code.js`. Questo passaggio include i moduli Media e Integrate.
1. **Distribuisci il file AppMeasurement.js**: carica il file `AppMeasurement.js` nel server Web.
1. **Aggiorna i riferimenti dello script per puntare a`AppMeasurement.js`**: verificare che tutte le pagine facciano riferimento a `AppMeasurement.js` anziché a `s_code.js`.

## Esempio di codice Appmeasurement

Un file `AppMeasurement.js` tipico. Verificare che le variabili di configurazione siano impostate sopra la funzione `doPlugins`.

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
made when instructed to do so by your Adobe Account Team.*/
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

Assicurarsi inoltre di aver incluso un riferimento a `AppMeasurement.js` e `VisitorAPI.js` in ogni pagina. Per ulteriori informazioni, vedere [Implementazione di JavaScript](/help/implement/js/overview.md).
