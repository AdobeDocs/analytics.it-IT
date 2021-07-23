---
title: Panoramica sull'implementazione JavaScript del codice H
description: Scopri il flusso di lavoro per implementare il codice H sul tuo sito.
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 11%

---

# Panoramica sull&#39;implementazione JavaScript del codice H

>[!IMPORTANT]
>
>Questa versione della raccolta dati non è più supportata. Effettua l&#39;aggiornamento ai tag [in Adobe Experience Platform](../../launch/overview.md) o [AppMeasurement per JavaScript](../overview.md).

Per implementare correttamente una pagina con codice per raccogliere i dati, devi disporre dell’accesso ai server di hosting. I passaggi seguenti illustrano un’implementazione di base del codice H di Analytics.

>[!NOTE]
>
>Devi già disporre di una copia esistente di `s_code.js` per seguire queste istruzioni. Adobe non offre più un&#39;opzione per scaricare il codice H in Code Manager.

1. **Aggiorna le variabili** del file JS di base: Modifica il  `s_code.js` file e assicurati che le seguenti variabili siano aggiornate:
   * `s_account` contiene l&#39;ID suite di rapporti a cui desideri inviare i dati. Consulta
   * `s.trackingServer` contiene i cookie di posizione memorizzati. Consulta [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Ospita il  `s_code.js` file sul tuo sito**: Questo file si trova in genere con altri script sul server Web.
1. **Riferimento  `s_code.js` su tutte le pagine**: Assicurati che tutte le singole pagine chiamino il file JavaScript di base e fallo all&#39;interno del  `<body>` tag HTML (non il  `<head>` tag).

   >[!TIP]
   >
   >Il codice H richiede che lo script `s_code.js` venga chiamato all&#39;interno del tag `<body>` . Ciò è diverso da altri metodi di implementazione, la maggior parte dei quali richiede che i riferimenti di script siano nel tag `<head>` .
1. **Definisci variabili specifiche per la pagina in ogni pagina**: Per ogni pagina devono essere definite singole variabili, ad esempio il nome della pagina o le eVar. Le singole variabili sono in genere definite con un tag in linea `<script>` in ogni pagina.
1. **Utilizza il debugger per verificare la raccolta** dati: Scarica e installa il  [debug ](../../validate/debugger.md) Experience Cloud per assicurarti che i dati siano inviati ad Adobe e che le variabili di pagina siano definite correttamente.

## Memorizzazione in cache

Il file JavaScript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti web, gli utenti visualizzano in media più di alcune visualizzazioni di pagina per sessione, quindi il trasferimento di JavaScript utilizzato più volte in questo file può causare un minor numero di dati scaricati.

## Compressione del codice H

Se sei preoccupato delle dimensioni di download del file `s_code.js`, Adobe consiglia di comprimere il file `s_code.js` utilizzando GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione JavaScript. Consulta [Modulo Apache mod_deflate](http://httpd.apache.org/docs/current/mod/mod_deflate.html) nella documentazione di Apache.
