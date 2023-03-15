---
description: Istruzioni per la configurazione di un trasferimento sicuro con server Adobe FTP.
keywords: ftp;sftp
title: Connessione a un account Adobe FTP con SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 54%

---

# Connessione a un account Adobe FTP con SFTP

Istruzioni per la configurazione di un trasferimento sicuro con server Adobe FTP.

1. Richiedi un account FTP ospitato da Adobe (spazio di 50 MB).
1. Crea chiavi RSA pubbliche/private. In Linux, esegui:

   ```
   ssh-keygen -t rsa
   ```

   Se ti trovi in ambiente Windows, usa puttyGen per creare le chiavi.

1. Crea un file denominato [!DNL authorized_keys] (nessuna estensione).
1. Copia il contenuto della chiave pubblica in [!DNL authorized_keys].
1. Carica [!DNL authorized_keys] a un account FTP:

   * Connettiti all&#39;account Adobe FTP.
   * Creare un [!DNL .ssh] (se non esiste già).
   * Carica [!DNL authorized_keys] file in [!DNL .ssh] directory.

1. Verifica la connessione accedendo all’account FTP tramite SFTP.

Per informazioni più dettagliate, consulta [Come connettersi ad Adobe tramite sFTP senza una password_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
