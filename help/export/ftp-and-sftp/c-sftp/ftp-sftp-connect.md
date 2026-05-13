---
description: Istruzioni per configurare il trasferimento sicuro con i server FTP di Adobe.
keywords: ftp;sftp
title: Connessione a un account Adobe FTP con SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
TQID: https://experienceleague.adobe.com/uXtJtDP58tSIzb9AvoAknAYoMt7SknJSgxRKNgIAXM8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 9%

---

# Connettersi a un account FTP con SFTP

Per impostare il trasferimento sicuro con FTP:

1. (Condizionale) Se desideri impostare un trasferimento sicuro con i server FTP di Adobe:

   1. Richiedi un account FTP ospitato da Adobe (quota 50 MB).

   1. Crea chiavi pubbliche/private.

      * In ambiente Linux, eseguire:

        ```
        ssh-keygen -t ed25519 -C "your-comment-or-email"
        ```

        Se i criteri non consentono di utilizzare ed25519, eseguire:

        ```
        ssh-keygen -t rsa -b 4096 -C "your-comment-or-email"
        ```

        **Nota:** questo si applica in genere ai clienti che operano con FIPS 186-4, in quanto ed25519 è inizialmente supportato nel più recente FIPS 186-5.

      * In un ambiente Windows, utilizza puttyGen.

1. (Condizionale) Se desideri impostare un trasferimento sicuro con la tua posizione FTP, devi disporre di un host SFTP, un nome utente e il sito di destinazione che contengano una chiave pubblica RSA o ed25519 valida. Puoi scaricare la chiave pubblica adatta al momento della creazione del feed.

1. Creare un file denominato [!DNL `authorized_keys`] (senza estensione).

1. Copia il contenuto della chiave pubblica in [!DNL `authorized_keys`].

1. Carica [!DNL `authorized_keys`] in un account FTP:

   * Connettiti all’account FTP di Adobe.
   * Creare una directory [!DNL .ssh] (se non esiste già).
   * Caricare il file [!DNL `authorized_keys`] nella directory [!DNL .ssh].

1. Verifica la connessione accedendo all’account FTP tramite SFTP.

Per informazioni più dettagliate, consulta [Connessione ad Adobe tramite SFTP senza password](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).

