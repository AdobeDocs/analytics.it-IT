---
description: Istruzioni per configurare il trasferimento sicuro con i server FTP di Adobe.
keywords: ftp;sftp
title: Connessione a un account Adobe FTP con SFTP
feature: FTP Export
exl-id: 727d4f7a-d7d1-40cf-bdcd-c783ca47f51c
TQID: 'https://experienceleague.adobe.com/5X1Nx0V0hievpCe9G1Q6gJS1c55T3xl5FuneZxPx4TI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 214
ht-degree: 19%

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

1. Crea un file denominato [!DNL `authorized_keys`] (senza estensione).

1. Copia il contenuto della chiave pubblica in [!DNL `authorized_keys`].

1. Carica [!DNL `authorized_keys`] in un account FTP:

   * Connettiti all’account FTP di Adobe.
   * Crea una directory [!DNL .ssh] (se non esiste già).
   * Carica il file [!DNL `authorized_keys`] nella directory [!DNL .ssh].

1. Verifica la connessione accedendo all’account FTP tramite SFTP.

Per informazioni più dettagliate, consulta [Connessione ad Adobe tramite SFTP senza password](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md).

