---
description: Adobe supporta l'esportazione di richieste di data warehouse a server SFTP.
keywords: ftp;sftp
seo-description: Adobe supporta l'esportazione di richieste di data warehouse a server SFTP.
seo-title: Invio di richieste di Data Warehouse a server SFTP
solution: Analytics
title: Invio di richieste di Data Warehouse a server SFTP
uuid: 393634a1-0643-4d63-bb6e-fb80f1ba76c1
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Invio di richieste di Data Warehouse a server SFTP

Adobe supporta l'esportazione di richieste di data warehouse a server SFTP.

Accertati che vengano completate le seguenti attività.

Adobe supporta l'esportazione di richieste di data warehouse a server SFTP, a condizione che siano soddisfatte le seguenti condizioni:

* [!DNL sftp://] il protocollo è specificato nel campo host (ad esempio, [!DNL sftp://ftp.example.com]) e viene utilizzata solo la porta 22 quando si richiede un rapporto Data Warehouse.

   Potete anche utilizzare l' [!DNL sftp+norename://] opzione, come descritto di seguito.

* Adobe's [!DNL authorized_keys] file is in the [!DNL .ssh] directory within the root directory of the user you log in with

* La destinazione non è [!DNL ftp.omniture.com]. Il protocollo sFTP tra i server interni di Adobe non è supportato.
* La destinazione supporta un'autenticazione a singolo fattore (PKI). Se è presente un'incompatibilità tra due fattori, sarà impossibile consegnare il report. Accertati che il tuo server non sia configurato per effettuare un'autenticazione a due fattori. Adobe Analytics richiede che per l'accesso venga utilizzata solamente la chiave.
* Adobe supporta la crittografia SSHv2 ed è retrocompatibile con la crittografia SSHv1 (solo chiave RSA).

To successfully send a [!DNL Data Warehouse] request via SFTP:

1. Ottenere il file [!DNL authorized_keys] chiedendo a uno degli utenti supportati della tua organizzazione di contattare l'Assistenza clienti.
1. Dopo aver ottenuto questo file, accedi al sito FTP utilizzando le stesse credenziali utilizzate per la richiesta [!DNL Data Warehouse].
1. In the root directory, navigate to the folder named [!DNL .ssh] (if one does not exist, create one) and place the [!DNL authorized_keys] file there.

1. Go to the [!DNL Data Warehouse] request manager. Configure the request as desired, then click **[!UICONTROL Advanced Delivery Options]**.

1. In the pop-up window, click **[!UICONTROL FTP]**, then specify the ftp site (including the [!DNL sftp://] protocol, such as [!DNL sftp://ftp.omniture.com]) via port 22.

   Including the [!DNL sftp://] protocol is only permitted when using SFTP. Regular FTP requests should omit the protocol prefix (such as, [!DNL ftp.omniture.com] instead of [!DNL ftp://ftp.omniture.com]).

1. Inserisci il nome della cartella in cui desideri collocare il file nel campo Folder (Cartella). É necessaria una cartella.
1. Inserisci lo stesso nome utente e password utilizzata al Passaggio 2.
1. Fai clic su **[!UICONTROL Send]**.

Il comando sftp PUT colloca un file temporaneo con estensione .part all'interno di una directory specificata. Al termine del caricamento, l'estensione del file viene rinominata nell'estensione definitiva. A questo punto è pronto per essere utilizzato.

Alternatively, [!DNL sftp+norename://] can be specified instead of [!DNL sftp://] to upload the file directly with the final name, without a temporary [!DNL .part] file name during upload. Questo approccio è appropriato quando il server SFTP gestisce automaticamente la ridenominazione dei file durante il caricamento e non esiste alcuna possibilità che il file venga elaborato prima del completamento del caricamento.
