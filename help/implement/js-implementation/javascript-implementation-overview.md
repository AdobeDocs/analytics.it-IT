---
description: Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nei rapporti.
keywords: Implementazione di Analytics; javascript; implementazione javascript; appmeasurement; appmeasurement del download; Servizio identità; visitorapi. js; memorizzazione nella cache; compressione delle app
seo-description: Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nei rapporti.
seo-title: Panoramica sull'implementazione javascript
solution: Analytics
title: Panoramica sull'implementazione javascript
topic: Sviluppatore e implementazione
uuid: bb 661 d 8 c-faf 9-4454-ac 3 c -0 c 1 a 4 c 0 a 9336
translation-type: tm+mt
source-git-commit: 883eb12c6c0f9b566dd485227d19cee16d9cfadc

---


# Panoramica sull'implementazione javascript

Per iniziare a utilizzare Analytics, i dati devono essere inviati a una suite di rapporti per essere visualizzati nei rapporti.

Il modo più immediato e consigliato per inviare i dati è [!DNL Analytics] utilizzare [Launch](/help/implement/implement-with-launch/create-analytics-property.md). Tuttavia, in alcuni casi, potrebbe essere utile implementare Analytics utilizzando il metodo javascript precedente.

>[!NOTE]
>
>Questa sezione descrive il metodo legacy di implementazione di Analytics. Tutti i clienti Analytics hanno accesso a [Launch](/help/implement/implement-with-launch/create-analytics-property.md), che è il metodo standard per distribuire i tag Experience Cloud.

## Passaggi di implementazione {#section_73961BAD5BB4430A95E073DE5C026277}

Per implementare correttamente una pagina con codice per la raccolta di dati, è necessario disporre dell'accesso ai server host per caricare nuovi contenuti nel sito Web. È inoltre utile disporre di un sito esistente per implementare il codice.

La procedura seguente illustra l'implementazione di base di Analytics.

| Attività | Descrizione |
|--- |--- |
| 1. Scarica appmeasurement per javascript e il servizio ID. | Accedi ad Analytics tramite Experience Cloud. Il file di download è disponibile in Analytics &gt; Admin &gt; Code Manager. Questo file ZIP di download contiene diversi file. Appmeasurement. js e visitorapi. js sono i file pertinenti durante l'implementazione di Analytics. |
| 2. Configurare il servizio identità. (già servizio Visitor ID) | Consultate [Configurare il servizio identità per Analytics](https://docs.adobe.com/content/help/en/id-service/using/home.html) |
| Aggiornamento `AppMeasurement.js`. | Copia il [codice appmeasurement. js di esempio](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) e incolla all'inizio del `AppMeasurement.js` file. Come minimo, aggiorna le seguenti variabili:<ul><li>s. account = "INSERT-RSID-HERE"</li><li>s. trackingserver = "INSERT-TRACKING-SERVER-HERE"</li><li>s. visitornamespace = "INSERT-NAMESPACE-HERE"</li><li>s. visitor = Visitor. getinstance ("INSERT-MCORG-ID-HERE")</li></ul><br>Consulta [Compilazione corretta delle variabili trackingserver e trackingserversecure](https://helpx.adobe.com/analytics/kb/determining-data-center.html) oppure contatta Client Care se non sei sicuro di uno di questi valori. Se non vengono impostati correttamente, i dati non saranno raccolti dalla tua implementazione.</br> |
| 3. Host `AppMeasurement.js` e `VisitorAPI.js`. | Questi file javascript di base devono essere ospitati su un server Web accessibile a tutte le pagine del sito. È necessario definire il percorso di questi file nella fase successiva. |
| 4. Reference `AppMeasurement.js` and `VisitorAPI.js`  on all site pages. | <ul><li>Includere il servizio ID visitatore aggiungendo la seguente riga di codice nel `head` tag o `body` in ogni pagina. `VisitorAPI.js` deve essere incluso prima `AppMeasurement.js`:`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</li><li>Include AppMeasurement for JavaScript by adding the following line of code in the `head` or `body` tag on each page: `script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</li></ul> |
| 5. Aggiornate e distribuite il codice della pagina. | Copiate [il codice pagina di esempio](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) e incollatelo appena dopo il `body` tag di apertura su ogni pagina da monitorare. Come minimo, aggiorna le seguenti variabili:<ul><li>var s = s_ gi ("INSERT-RSID-HERE")</li><li>s. pagename = "INSERT-NAME-HERE" (ad esempio, s. pagename = document. title)</li></ul> |
| 6. Utilizzate Experience Cloud Debugger per verificare che i dati siano in corso di invio. | Installare [il debugger Experience Cloud](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2). Dopo essere stato installato, caricate una pagina in cui avete distribuito il codice della pagina e aprite il debugger. Il debugger visualizza i dettagli relativi ai dati della raccolta inviati. |

## Memorizzazione nella cache {#section_4E2D1D962DF046418134C43CFC49AD4A}

Il file javascript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti Web, gli utenti possono media più di un paio di visualizzazioni di pagina per sessione, quindi il trasferimento di javascript utilizzato più volte in questo file può comportare meno dati scaricati.

## Javascript per la compressione appmeasurement {#section_C10BBC84C81C414088F97363D29E021B}

Se siete preoccupati dello spessore della pagina (dimensione) di Codice H (appmeasurement per javascript 1.0), Adobe consiglia di considerare la compressione del file mediante GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione javascript per comprimere e decomprimere il file [!DNL s_code.js] javascript di base.

I collegamenti seguenti spiegano come utilizzare la funzionalità GZIP sul sito per gestire la compressione del codice [!DNL s_code.js] javascript:

[Apache Module mod_ deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Abilitazione della compressione gzip con Tomcat e Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/)
