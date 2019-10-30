---
description: Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nel reporting.
keywords: Analytics Implementation;javascript;javascript implementation;appmeasurement;download appmeasurement;Identity Service;visitorapi.js;caching;appmeasurement compressione
seo-description: Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nel reporting.
seo-title: Panoramica sull'implementazione JavaScript
solution: Analytics
title: Panoramica sull'implementazione JavaScript
topic: Sviluppatore e implementazione
uuid: bb661d8c-faf9-4454-ac3c-0c1a4c0a9336
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Panoramica sull'implementazione JavaScript

Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nel reporting.

Il modo più semplice e consigliato per inviare i dati [!DNL Analytics] è utilizzare [Launch](/help/implement/implement-with-launch/create-analytics-property.md). Tuttavia, in alcuni casi, potrebbe essere utile implementare Analytics utilizzando il precedente metodo JavaScript.

> [!NOTE] Questa sezione descrive il metodo legacy di implementazione di Analytics. Tutti i clienti Analytics hanno accesso a [Launch](/help/implement/implement-with-launch/create-analytics-property.md), che è il metodo standard per distribuire i tag Experience Cloud.

## Passaggi di implementazione {#section_73961BAD5BB4430A95E073DE5C026277}

Per implementare correttamente una pagina con codice per la raccolta dei dati, è necessario avere accesso ai server di hosting per caricare nuovi contenuti nel sito Web. È inoltre utile disporre di un sito esistente per implementare il codice.

La procedura seguente illustra un'implementazione di base di Analytics.

| Attività | Descrizione |
|--- |--- |
| 1. Scarica AppMeasurement per JavaScript e il servizio ID. | Accedi ad Analytics tramite Experience Cloud. Il file di download è disponibile in Analytics &gt; Amministratore &gt; Code Manager (Gestione codici).  Questo zip di download contiene diversi file.  AppMeasurement.js e VisitorAPI.js sono i file rilevanti per l’implementazione di Analytics. |
| 2. Configurare il servizio identità. (precedentemente servizio ID visitatore) | Consultate [Configurare il servizio identità per Analytics](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| 3. Update `AppMeasurement.js`. | Copia il codice [AppMeasurement.js di](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) esempio e incollalo all’inizio del `AppMeasurement.js` file. Come minimo, aggiorna le seguenti variabili:<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>Vedi [Compilazione corretta delle variabili](https://helpx.adobe.com/analytics/kb/determining-data-center.html) trackingServer e trackingServerSecure oppure contatta Client Care se non sei sicuro di questi valori. Se non sono impostati correttamente, i dati non saranno raccolti dall’implementazione.</br> |
| 4. Host `AppMeasurement.js` e `VisitorAPI.js`. | Questi file JavaScript di base devono essere ospitati su un server Web accessibile a tutte le pagine del sito. È necessario definire il percorso di questi file nella fase successiva. |
| 5. Reference `AppMeasurement.js` and `VisitorAPI.js`  on all site pages. | <ul><li>Includi il servizio ID visitatore aggiungendo la seguente riga di codice nel `head` tag o `body` tag di ogni pagina. (`VisitorAPI.js` deve essere incluso prima `AppMeasurement.js`).<br>`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</br></li><li>Include AppMeasurement for JavaScript by adding the following line of code in the `head` or `body` tag on each page:<br>`script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</br></li></ul> |
| 6. Aggiorna e distribuisci il codice della pagina. | Copiate il codice [di pagina di](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) esempio e incollatelo subito dopo il `body` tag di apertura su ogni pagina da monitorare. Come minimo, aggiorna le seguenti variabili:<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s.pageName="INSERT-NAME-HERE" (ad esempio, s.pageName=document.title)</li></ul> |
| 7. Usa Experience Cloud Debugger per verificare che i dati vengano inviati. | Installa [Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2). Una volta installato, carica una pagina in cui hai distribuito il codice della pagina e apri il debugger. Il debugger visualizza i dettagli relativi ai dati di raccolta inviati. |

## Cache {#section_4E2D1D962DF046418134C43CFC49AD4A}

Il file JavaScript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti Web, gli utenti visualizzano in media più di poche visualizzazioni di pagina per sessione, pertanto il trasferimento di JavaScript utilizzato più volte in questo file può comportare una riduzione dei dati scaricati complessivi.

## JavaScript per la compressione AppMeasurement {#section_C10BBC84C81C414088F97363D29E021B}

Se siete preoccupati per lo spessore (dimensione) della pagina del codice H (AppMeasurement per JavaScript 1.0 è precompresso), Adobe consiglia di valutare la possibilità di comprimere il file utilizzando GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione JavaScript per comprimere e decomprimere il file [!DNL s_code.js] JavaScript di base.

I seguenti collegamenti spiegano come utilizzare la funzionalità GZIP sul sito per gestire la compressione del codice [!DNL s_code.js] JavaScript:

[Apache Module mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Abilitazione della compressione gzip con Tomcat e Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
