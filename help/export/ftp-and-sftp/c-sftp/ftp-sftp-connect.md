---
description: Istruzioni per la configurazione di un trasferimento sicuro con server Adobe FTP.
keywords: ftp;sftp
title: Connessione a un account Adobe FTP con SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
source-git-commit: 62132284ca70f3bdb1a8896e4548b8b63a5c03c8
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 31%

---

# Connessione a un account FTP con SFTP

Per impostare il trasferimento sicuro con FTP:

1. (Condizionale) Se desideri impostare un trasferimento sicuro con i server FTP di Adobe:

   1. Richiedi un account FTP ospitato da Adobe (spazio di 50 MB).

   1. Crea chiavi RSA pubbliche/private.

      * In ambiente Linux, eseguire:

        ```
        ssh-keygen -t rsa
        ```

      * In un ambiente Windows, utilizza puttyGen.

1. (Condizionale) Se desideri impostare un trasferimento sicuro con la tua posizione FTP, devi disporre di un host SFTP, un nome utente e il sito di destinazione che contengano una chiave pubblica RSA o DSA valida. Puoi scaricare la chiave pubblica adatta al momento della creazione del feed.

1. Crea un file denominato [!DNL authorized_keys] (nessuna estensione).

1. Copia il contenuto della chiave pubblica in [!DNL authorized_keys].

1. Carica [!DNL authorized_keys] a un account FTP:

   * Connettiti all&#39;account Adobe FTP.
   * Creare un [!DNL .ssh] (se non esiste già).
   * Carica [!DNL authorized_keys] file in [!DNL .ssh] directory.

1. Verifica la connessione accedendo all’account FTP tramite SFTP.

Per informazioni più dettagliate, consulta [Come connettersi ad Adobe tramite sFTP senza una password_...](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).
