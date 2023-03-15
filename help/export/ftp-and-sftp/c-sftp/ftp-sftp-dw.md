---
description: Adobe supporta l’esportazione delle richieste di Data Warehouse ai server SFTP.
keywords: ftp;sftp
title: Invio di richieste di Data Warehouse a server SFTP
feature: FTP Export
exl-id: 45694647-69ec-45e3-b614-4a936909a338
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 100%

---

# Invio di richieste di Data Warehouse a server SFTP

Adobe supporta l’esportazione delle richieste di Data Warehouse ai server SFTP.

Accertati che vengano completate le seguenti attività.

Adobe supporta l’esportazione di richieste di Data Warehouse ai server SFTP purché vengano soddisfatte le seguenti condizioni:

* Protocollo `sftp://` specificato nel campo host (ad esempio, `sftp://ftp.example.com`) e utilizzo della SOLA porta 22 durante la richiesta di un rapporto di Data Warehouse. È inoltre possibile utilizzare l’opzione `sftp+norename://`, come descritto di seguito.
* File Adobe `authorized_keys` nella directory `.ssh` all’interno della directory principale dell’utente con il quale effettui l’accesso
* La destinazione non è `ftp.omniture.com`. Il protocollo sFTP tra i server interni di Adobe non è supportato.
* La destinazione supporta un&#39;autenticazione a singolo fattore (PKI). Se è presente un&#39;incompatibilità tra due fattori, sarà impossibile consegnare il report. Accertati che il tuo server non sia configurato per effettuare un’autenticazione a due fattori. Adobe Analytics richiede che per l&#39;accesso venga utilizzata solamente la chiave.
* Adobe supporta la crittografia SSHv2 ed è retrocompatibile con la crittografia SSHv1 (solo chiave RSA).

Per inviare correttamente una richiesta di Data Warehouse tramite SFTP:

1. Ottenere il file `authorized_keys` chiedendo a uno degli utenti supportati della tua organizzazione di contattare l&#39;Assistenza clienti.
1. Dopo aver ottenuto questo file, accedi al sito FTP utilizzando le stesse credenziali utilizzate per la richiesta Data Warehouse.
1. Nella directory principale, accedi alla cartella denominata `.ssh` (se non esiste, creane una) e colloca al suo interno il file `authorized_keys`.

1. Accedi al gestore richieste di Data Warehouse. Configura la richiesta come desideri, quindi fai clic su **[!UICONTROL Advanced Delivery Options]**.

1. Nella finestra pop-up, fai clic su **[!UICONTROL FTP]**, quindi specifica il sito ftp (incluso il protocollo `sftp://`, come ad esempio `sftp://ftp.omniture.com`) tramite la porta 22.

   L’inclusione del protocollo `sftp://` è consentita solamente quando si utilizza l’SFTP. Le richieste FTP regolari devono omettere il prefisso del protocollo (come ad esempio `ftp.omniture.com` invece di `ftp://ftp.omniture.com`).

1. Inserisci il nome della cartella in cui desideri collocare il file nel campo Folder (Cartella). É necessaria una cartella.
1. Inserisci lo stesso nome utente e password utilizzata al Passaggio 2.
1. Fai clic su **[!UICONTROL Send]**.

Il comando sftp PUT colloca un file temporaneo con estensione .part all&#39;interno di una directory specificata. Al termine del caricamento, l&#39;estensione del file viene rinominata nell&#39;estensione definitiva. A questo punto è pronto per essere utilizzato.

In alternativa, è possibile specificare `sftp+norename://` invece di `sftp://` per caricare il file direttamente con il nome finale, senza utilizzare un nome file `.part` temporaneo. Questo approccio è appropriato quando il server SFTP gestisce automaticamente la ridenominazione del file durante il caricamento e non è possibile elaborare il file prima che venga completato.
