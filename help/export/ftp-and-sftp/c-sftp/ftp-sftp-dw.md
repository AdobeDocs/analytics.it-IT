---
description: Adobe supporta l’esportazione delle richieste di Data Warehouse ai server SFTP.
keywords: ftp;sftp
title: Invio di richieste di Data Warehouse a server SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: d8bfad5d388f906c7c7301a9126813f5c2a5dbaa
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 59%

---

# Invio di richieste di Data Warehouse a server SFTP

Adobe supporta l’esportazione delle richieste Data Warehouse ai server SFTP, come descritto in [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) nell’articolo, [Configurare una destinazione di rapporto per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).

Accertati che vengano completate le seguenti attività.

* Quando si richiede un rapporto di Data Warehouse, viene utilizzata solo la porta 22.
* File Adobe `authorized_keys` nella directory `.ssh` all’interno della directory principale dell’utente con il quale effettui l’accesso.
* La destinazione non è `ftp.omniture.com`. Il protocollo sFTP tra i server interni di Adobe non è supportato.
* La destinazione supporta un&#39;autenticazione a singolo fattore (PKI). Se è presente un&#39;incompatibilità tra due fattori, sarà impossibile consegnare il report. Accertati che il tuo server non sia configurato per effettuare un’autenticazione a due fattori. Adobe Analytics richiede che per l&#39;accesso venga utilizzata solamente la chiave.
* Adobe supporta la crittografia SSHv2 ed è retrocompatibile con la crittografia SSHv1 (solo chiave RSA).

Per inviare correttamente una richiesta di Data Warehouse tramite SFTP:

1. Completa i passaggi descritti in [SFTP](/help/export/data-warehouse/create-request/dw-request-report-destinations.md#sftp) nell’articolo, [Configurare una destinazione di rapporto per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md), incluso il download della chiave pubblica.
1. Accedi al sito SFTP con le stesse credenziali utilizzate per la richiesta Data Warehouse.
1. Nella directory principale, accedi alla cartella denominata `.ssh` (se non esiste, creane una) e colloca al suo interno il file `authorized_keys`.

1. Se non lo hai già fatto, completa la richiesta Data Warehouse come descritto in [Configurare una destinazione di rapporto per una richiesta Data Warehouse](/help/export/data-warehouse/create-request/dw-request-report-destinations.md).
