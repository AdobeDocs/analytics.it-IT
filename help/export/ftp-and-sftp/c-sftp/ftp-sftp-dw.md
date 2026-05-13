---
description: Adobe supporta l’esportazione delle richieste di Data Warehouse ai server SFTP.
keywords: ftp;sftp
title: Invio di richieste di Data Warehouse a server SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
TQID: https://experienceleague.adobe.com/nBerOKEbILwAK5OyayVgdBPN8vq24kk-DXY6XMT50wg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 258
ht-degree: 31%

---

# Invio di richieste di Data Warehouse a server SFTP

Adobe supporta l&#39;esportazione di richieste Data Warehouse ai server SFTP, come descritto in [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) nell&#39;articolo [Configurare una destinazione di report per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

Accertati che vengano completate le seguenti attività.

* Quando si richiede un rapporto Data Warehouse, viene utilizzata solo la porta 22.
* Il file `authorized_keys` di Adobe si trova nella directory `.ssh` all&#39;interno della directory principale dell&#39;utente con cui si effettua l&#39;accesso.
* La destinazione non è `ftp.omniture.com`. Il protocollo SFTP tra i server interni di Adobe non è supportato.
* La destinazione supporta l&#39;autenticazione a un fattore (PKI). In caso di problemi a due fattori, la consegna del rapporto non riuscirà. Accertati che il tuo server non sia configurato per effettuare un’autenticazione a due fattori. Adobe Analytics richiede che per accedere venga utilizzata solo la chiave e nient’altro.
* Adobe supporta la crittografia SSHv2 e il fallback a SSHv1 (solo chiave RSA).

Per inviare correttamente una richiesta di Data Warehouse tramite SFTP:

1. Completa i passaggi descritti in [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) nell&#39;articolo [Configurare una destinazione di report per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), incluso il download della chiave pubblica.
1. Accedi al sito SFTP con le stesse credenziali utilizzate per la richiesta Data Warehouse.
1. Nella directory principale, accedi alla cartella denominata `.ssh` (se non esiste, creane una) e colloca al suo interno il file `authorized_keys`.

1. Completare la richiesta di Data Warehouse se non lo si è già fatto, come descritto in [Configurare una destinazione di report per una richiesta di Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
