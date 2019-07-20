---
description: Istruzioni per la configurazione di un trasferimento sicuro con server Adobe FTP.
keywords: ftp; sftp
seo-description: Istruzioni per la configurazione di un trasferimento sicuro con server Adobe FTP.
seo-title: Connessione a un account Adobe FTP con SFTP
solution: Analytics
title: Connessione a un account Adobe FTP con SFTP
uuid: 4 faf 27 b 8-7276-4 c 68-87 cb -35802 b 809 e 27
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

For more detailed information, see [How to Connect to Adobe via sFTP Without a Password_...](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846).
