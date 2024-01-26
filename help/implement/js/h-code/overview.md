---
title: Panoramica sull’implementazione di JavaScript per codice H
description: Scopri il flusso di lavoro per implementare il codice H sul tuo sito.
feature: Implementation Basics
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 11%

---

# Panoramica sull’implementazione di JavaScript per codice H

>[!IMPORTANT]
>
>Questa versione della raccolta dati non è più supportata. Esegui l’aggiornamento a [tag in Adobe Experience Platform](../../launch/overview.md) o [AppMeasurement per JavaScript](../overview.md).

Devi avere accesso ai server di hosting per implementare correttamente una pagina con codice per raccogliere i dati. I seguenti passaggi ti guidano attraverso un’implementazione di base del codice H di Analytics.

>[!NOTE]
>
>È necessario disporre già di una copia di `s_code.js` per seguire queste istruzioni. L’Adobe non offre più l’opzione di scaricare il codice H in Code Manager.

1. **Aggiornare le variabili dei file JS di base**: modifica il `s_code.js` e accertati che siano aggiornate le seguenti variabili:
   * `s_account` contiene l’ID suite di rapporti a cui desideri inviare i dati. Consulta
   * `s.trackingServer` contiene i cookie di posizione memorizzati. Consulta [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Ospita il `s_code.js` file sul sito**: questo file risiede in genere con altri script sul server web.
1. **Riferimento `s_code.js` su tutte le pagine**: accertati che tutte le singole pagine chiamino il file JavaScript di base e all’interno di HTML `<body>` (non il tag `<head>` ).

   >[!TIP]
   >
   >Il codice H richiede che `s_code.js` lo script viene chiamato all&#39;interno del `<body>` tag. Questo è diverso da altri metodi di implementazione, la maggior parte dei quali richiede che i riferimenti agli script siano nel `<head>` tag.
1. **Definire le variabili specifiche della pagina in ogni pagina**: ogni pagina deve avere singole variabili definite, ad esempio il nome della pagina o le eVar. Le singole variabili sono in genere definite con un valore in linea `<script>` su ogni pagina.
1. **Utilizzare il debugger per verificare la raccolta dati**: scarica e installa [Debugger Experience Cloud](../../validate/debugger.md) per assicurarti che i dati siano inviati ad Adobe e che le variabili di pagina siano definite correttamente.

## Memorizzazione in cache

Il file JavaScript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti web, gli utenti effettuano in media più di un paio di visualizzazioni di pagina per sessione, pertanto il trasferimento di JavaScript utilizzato più volte in questo file può comportare meno dati scaricati.

## Compressione codice H

Se sei preoccupato della dimensione di download del `s_code.js` file, l’Adobe consiglia di comprimere il `s_code.js` file tramite GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione JavaScript. Consulta [Modulo Apache mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html) nella documentazione di Apache.
