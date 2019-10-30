---
description: Istruzioni per la configurazione di un trasferimento sicuro con server Adobe FTP.
keywords: ftp;sftp
seo-description: Istruzioni per la configurazione di un trasferimento sicuro con server Adobe FTP.
seo-title: Connessione a un account Adobe FTP con SFTP
solution: Analytics
title: Connessione a un account Adobe FTP con SFTP
uuid: 4faf27b8-7276-4c68-87cb-35802b809e27
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Connessione a un account Adobe FTP con SFTP

Istruzioni per la configurazione di un trasferimento sicuro con server Adobe FTP.

1. Richiedi un account FTP ospitato da Adobe (spazio di 50 MB).
1. Crea chiavi RSA pubbliche/private. In Linux, esegui:

   ```
   ssh-keygen -t rsa
   ```

   Se ti trovi in ambiente Windows, usa puttyGen per creare le chiavi.

1. Create a file named [!DNL authorized_keys] (no extension).
1. Copy the contents of the Public key into [!DNL authorized_keys].
1. Upload [!DNL authorized_keys] to an FTP account:

   * Connettiti all'account Adobe FTP.
   * Create a [!DNL .ssh] directory (if it does not already exist).
   * Upload the [!DNL authorized_keys] file to the [!DNL .ssh] directory.

1. Verificare la connessione effettuando l'accesso all'account FTP utilizzando SFTP.

[Per ulteriori informazioni, consultate ](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)Come connettersi ad Adobe tramite sFTP senza password_....
