---
title: Panoramica sull’implementazione JavaScript del codice H
description: Scopri il flusso di lavoro per implementare il codice H sul tuo sito.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 11%

---


# Panoramica sull’implementazione JavaScript del codice H

>[!IMPORTANT]
>
>Questa versione della raccolta dati non è più supportata. Aggiornamento a [Launch](../../launch/overview.md) Adobe Experience Platform o [AppMeasurement per JavaScript](../overview.md).

Per implementare correttamente una pagina con codice per la raccolta dei dati, è necessario disporre dell&#39;accesso ai server di hosting. La procedura seguente illustra un’implementazione di base  codice H di Analytics.

>[!NOTE]
>
>Per `s_code.js` seguire queste istruzioni è già necessario disporre di una copia esistente di. Adobe non offre più l&#39;opzione per scaricare il codice H in Code Manager.

1. **Aggiorna le variabili** del file JS di base: Modificate il `s_code.js` file e accertatevi che le seguenti variabili siano aggiornate:
   * `s_account` contiene l&#39;ID suite di rapporti a cui si desidera inviare i dati. Consulta
   * `s.trackingServer` contiene i cookie di posizione memorizzati. Vedi [trackingServer](../../vars/config-vars/trackingserver.md).
2. **Ospita il`s_code.js`file sul tuo sito**: Questo file si trova in genere con altri script sul server Web.
3. **Riferimento`s_code.js`su tutte le pagine**: Accertatevi che tutte le singole pagine chiamino il file JavaScript di base e lo facciano all’interno del `<body>` tag HTML (non il `<head>` tag).
   > [!TIP] H Code richiede che lo `s_code.js` script venga chiamato all&#39;interno del `<body>` tag . Ciò è diverso da altri metodi di implementazione, la maggior parte dei quali richiede che i riferimenti di script siano presenti nel `<head>` tag .
4. **Consente di definire variabili specifiche per la pagina in ogni pagina**: Ogni pagina deve avere singole variabili definite, ad esempio il nome della pagina o le eVar. Le singole variabili sono in genere definite con un `<script>` tag in linea su ogni pagina.
5. **Utilizzare il debugger per verificare la raccolta** dei dati: Scaricate e installate il [Experience Cloud Debugger](../../validate/debugger.md) per essere certi che i dati vengano inviati ad Adobe e che le variabili di pagina siano definite correttamente.

## Caching

Il file JavaScript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti Web, gli utenti visualizzano in media più di poche visualizzazioni di pagina per sessione, pertanto il trasferimento di JavaScript utilizzato più volte in questo file può comportare una riduzione dei dati scaricati complessivi.

## Compressione H Code

Se siete preoccupati per la dimensione di download del `s_code.js` file, Adobe consiglia di comprimere il `s_code.js` file utilizzando GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione JavaScript. Consulta [Apache Module mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) nella documentazione Apache.
