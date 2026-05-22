---
title: Aggiornamento dei servizi SFTP - Domande frequenti
description: Domande frequenti sull’aggiornamento pianificato dei servizi SFTP.
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
TQID: 'https://experienceleague.adobe.com/HKI-iOTx-gHbsmL8BJszgs5e5nlflk67s64eqs2dd-k'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7aid: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2: id: a8bf2e97-0add-4437-b976-1fc5154911a8
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 444
ht-degree: 8%

---

# Aggiornamento dei servizi SFTP - Domande frequenti

Il 20 settembre 2022 Adobe Analytics aggiornerà i servizi [SFTP] del protocollo Secure File Transfer Protocol per migliorare la sicurezza dei trasferimenti di file. Con questa modifica, alcune configurazioni client SFTP non saranno più supportate. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non sarà interessato. Per evitare interruzioni del servizio, assicurati che i client SFTP (codice, strumenti, servizi) siano in linea con le modifiche dettagliate di seguito.

## Come posso determinare quali algoritmi, tipi di connessione e protocolli sono attualmente utilizzati dalla mia organizzazione?

Il software FTP/SFTP in uso deve indicare le impostazioni specifiche utilizzate nelle connessioni configurate per lo scambio di dati con Adobe Analytics. Questo software deve includere anche la documentazione sulle diverse opzioni disponibili per le connessioni. Le opzioni che saranno supportate dopo questo aggiornamento sono ampiamente supportate e accettate nel settore.

Le opzioni di connessione che verranno rimosse sono generalmente considerate obsolete e non vengono utilizzate nel software corrente. Se hai aggiornato il software FTP/SFTP negli ultimi tre anni, probabilmente disponi già di una connessione conforme.

## Quali funzioni di Adobe Analytics utilizzano SFTP per l’acquisizione dei dati?

Le seguenti funzioni forniscono un’opzione per caricare dati in Adobe Analytics utilizzando SFTP.

* [Classificazioni](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-saint.md)

* [Attributi cliente](https://experienceleague.adobe.com/docs/core-services/interface/services/customer-attributes/attributes.html)

* [Feed dati](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datafeeds.md)

* [Origini dati](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-datasources.md)

* [Report consegnati di Data Warehouse](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-dw-reports.md)

* Inoltre, alcune implementazioni personalizzate create tramite [Engineering Services](/help/export/ftp-and-sftp/c-set-up-ftp-accounts/ftp-eng-services.md) possono utilizzare SFTP per scambiare dati con Adobe.

## Quali modifiche specifiche saranno incluse in questo aggiornamento?

Di seguito è riportato un elenco dettagliato di quali connessioni e algoritmi verranno rimossi e quali
supportati:

* Algoritmi mac del protocollo SFTP:

   * Non supporteremo più: hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * Supporteremo solo: hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* Algoritmo di crittografia del protocollo SFTP:

   * Non supporteremo più: 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * Supporteremo solo: aes128-ctr, aes192-ctr, aes256-ctr

* Connessioni supportate dal protocollo SFTP:

   * Non supporteremo più l&#39;utilizzo di comandi o connessioni scp e rsync tramite il protocollo sftp

   * Supporteremo solo connessioni con protocollo SFTP puro

* Client/protocolli FTP/SFTP supportati:

   * FTP: vsftpd versione 3.0.2-25 o successiva

   * SFTP: openssh versione 7.4p1-21 o successiva
