---
title: Panoramica sull'implementazione JavaScript del codice H
description: Scopri il flusso di lavoro per implementare il codice H sul tuo sito.
feature: Implementation Basics
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 11%

---

# Panoramica sull&#39;implementazione JavaScript del codice H

>[!IMPORTANT]
>
>Questa versione della raccolta dati non è più supportata. Effettua l’aggiornamento a [tag in Adobe Experience Platform](../../launch/overview.md) o [AppMeasurement per JavaScript](../overview.md).

Per implementare correttamente una pagina con codice per raccogliere i dati, devi disporre dell’accesso ai server di hosting. I passaggi seguenti illustrano un’implementazione di base del codice H di Analytics.

>[!NOTE]
>
>È già necessaria una copia esistente di `s_code.js` seguire queste istruzioni. Adobe non offre più un&#39;opzione per scaricare il codice H in Code Manager.

1. **Aggiorna le variabili del file JS di base**: Modifica le `s_code.js` e assicurati che le seguenti variabili siano aggiornate:
   * `s_account` contiene l&#39;ID suite di rapporti a cui desideri inviare i dati. Consulta
   * `s.trackingServer` contiene i cookie di posizione memorizzati. Vedi [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Ospita `s_code.js` file sul sito**: Questo file si trova in genere con altri script sul server Web.
1. **Riferimento `s_code.js` su tutte le pagine**: Assicurati che tutte le singole pagine chiamino il file JavaScript di base e fallo all’interno di HTML `<body>` (non il `<head>` tag).

   >[!TIP]
   >
   >Il codice H richiede che `s_code.js` lo script viene chiamato all&#39;interno del `<body>` tag . Ciò è diverso da altri metodi di implementazione, la maggior parte dei quali richiede che i riferimenti di script siano presenti nel `<head>` tag .
1. **Definire variabili specifiche per la pagina in ogni pagina**: Per ogni pagina devono essere definite singole variabili, ad esempio il nome della pagina o le eVar. Le singole variabili sono in genere definite con una `<script>` su ogni pagina.
1. **Utilizza il debugger per verificare la raccolta dati**: Scarica e installa la [Debugger Experience Cloud](../../validate/debugger.md) per assicurarsi che i dati siano inviati ad Adobe e che le variabili di pagina siano definite correttamente.

## Memorizzazione in cache

Il file JavaScript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti web, gli utenti visualizzano in media più di alcune visualizzazioni di pagina per sessione, quindi il trasferimento di JavaScript utilizzato più volte in questo file può causare un minor numero di dati scaricati.

## Compressione del codice H

Se sei preoccupato della dimensione del download del `s_code.js` file, Adobe consiglia di comprimere il `s_code.js` file utilizzando GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione JavaScript. Vedi [Apache Module mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html) nella documentazione di Apache.
