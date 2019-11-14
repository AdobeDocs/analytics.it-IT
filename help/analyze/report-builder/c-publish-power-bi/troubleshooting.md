---
description: Di seguito sono riportati alcuni errori comuni nell'utilizzo di Generatore di report con Power BI.
title: Risoluzione dei problemi di integrazione di Power BI
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Risoluzione dei problemi di integrazione di Power BI

Di seguito sono riportati alcuni errori comuni nell'utilizzo di Generatore di report con Power BI.

## Passaggio 1: Errore di pubblicazione in Power BI {#section_5B87DC1C302C4FD8AB9E4DD6B162DC9B}

Le cartelle di lavoro pianificate che richiedono la pubblicazione di Power BI dipendono dall'attivazione e dall'esecuzione dei servizi Power BI. Due motivi principali per la mancata pubblicazione sono:

* I servizi Power BI potrebbero non essere disponibili.
* L'utente che ha pianificato la cartella di lavoro non dispone più di credenziali account Microsoft valide.

A ogni attività pianificata del Generatore di report vengono assegnati tre tentativi per esecuzione programmata:

* Dopo il primo tentativo non riuscito, riceverai il messaggio seguente: ""Impossibile pubblicare la cartella di lavoro pianificata in Microsoft Power BI. Riproveremo a breve."
* Dopo il secondo tentativo non riuscito, non verrà visualizzato alcun messaggio.
* Dopo il terzo tentativo non riuscito, riceverai il messaggio seguente: "Impossibile pubblicare la cartella di lavoro in Power BI."

## Passaggio 2: Visualizzazioni interrotte in Power BI {#section_FFFE200D06F843B2AF093710FD678166}

Di seguito sono riportati i motivi principali per cui è possibile ottenere visualizzazioni interrotte dopo la pubblicazione delle richieste del Generatore di report in Power BI:

* È stata modificata una richiesta in Generatore di report, ad esempio la modifica di metriche o dimensioni, quindi ripubblicata in Power BI. Le richieste di modifica possono interrompere le visualizzazioni.
* Hai eliminato una richiesta utilizzata in una visualizzazione.

