---
title: Panoramica sull’implementazione di H Code JavaScript
description: Scopri il flusso di lavoro per implementare il codice H sul tuo sito.
feature: Implementation Basics
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
role: Developer
TQID: https://experienceleague.adobe.com/tcREdTxSH3L5XcCcu3W1aEQySJSDyAzrlQgyrutcUds
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 388
ht-degree: 11%

---

# Panoramica sull’implementazione di H Code JavaScript

>[!IMPORTANT]
>
>Questa versione della raccolta dati non è più supportata. Esegui l&#39;aggiornamento a [tag in Adobe Experience Platform](../../launch/overview.md) o [AppMeasurement per JavaScript](../overview.md).

Devi avere accesso ai server di hosting per implementare correttamente una pagina con codice per raccogliere i dati. I seguenti passaggi ti guidano attraverso un’implementazione di base del codice H di Analytics.

>[!NOTE]
>
>Per seguire queste istruzioni, è necessario disporre di una copia esistente di `s_code.js`. Adobe non offre più l’opzione di scaricare il codice H in Code Manager.

1. **Aggiorna le variabili del file JS di base**: modifica il file `s_code.js` e assicurati che le seguenti variabili siano aggiornate:
   * `s_account` contiene l&#39;ID suite di rapporti a cui desideri inviare i dati. Consulta
   * `s.trackingServer` contiene i cookie di posizione archiviati. Vedi [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Ospita il file `s_code.js` nel sito**: questo file risiede in genere con altri script nel server Web.
1. **Riferimento `s_code.js` su tutte le pagine**: assicurarsi che tutte le singole pagine chiamino il file JavaScript di base e che ciò avvenga all&#39;interno del tag HTML `<body>` (non il tag `<head>`).

   >[!TIP]
   >
   >Il codice H richiede che lo script `s_code.js` sia chiamato all&#39;interno del tag `<body>`. Questo metodo è diverso da altri metodi di implementazione, la maggior parte dei quali richiede che i riferimenti agli script siano nel tag `<head>`.
1. **Definisci le variabili specifiche della pagina in ogni pagina**: ogni pagina deve avere singole variabili definite, ad esempio il nome della pagina o le eVar. Le singole variabili vengono in genere definite con un tag `<script>` inline su ogni pagina.
1. **Utilizza il debugger per verificare la raccolta dati**: scarica e installa [CX Enterprise Debugger](../../validate/debugger.md) per assicurarti che i dati vengano inviati ad Adobe e che le variabili di pagina siano definite correttamente.

## Memorizzazione in cache

Il file JavaScript viene memorizzato nella cache del browser del visitatore dopo averlo caricato inizialmente, e in genere viene scaricato non più di una volta per sessione. Il file non viene scaricato su ogni pagina, anche se viene utilizzato da ogni pagina del sito. Nella maggior parte dei siti web, gli utenti visualizzano in media più di un paio di visualizzazioni di pagina per sessione, pertanto il trasferimento di JavaScript utilizzato più volte in questo file può comportare meno dati scaricati complessivamente.

## Compressione codice H

Se sei preoccupato della dimensione di download del file `s_code.js`, Adobe consiglia di comprimere il file `s_code.js` utilizzando GZIP. GZIP è supportato da tutti i principali browser e offre prestazioni migliori rispetto alla compressione JavaScript. Vedi [Modulo Apache mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html) nella documentazione di Apache.
