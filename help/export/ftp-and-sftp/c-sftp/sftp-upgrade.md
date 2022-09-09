---
title: Aggiornamento dei servizi SFTP - Domande frequenti
description: Domande frequenti sull’aggiornamento pianificato dei servizi SFTP.
feature: FTP Export
exl-id: e271b545-0769-4a69-9d7f-dc46bc654737
source-git-commit: 4edae431cf4bca1c3e7d7c1017bbc4a89b0e1d7f
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 6%

---

# Aggiornamento dei servizi SFTP - Domande frequenti

A metà settembre 2022, Adobe Analytics aggiornerà il protocollo Secure File Transfer [SFTP] servizi per migliorare la sicurezza dei trasferimenti di file. Con questa modifica, alcune configurazioni client SFTP non saranno più supportate. Questo influisce solo sui dati inviati o recuperati da Adobe Analytics tramite SFTP. Il protocollo FTP non sarà interessato. Per evitare interruzioni del servizio, assicurati che i clienti SFTP (codice, strumenti, servizi) siano in linea con le modifiche descritte di seguito.

## Come posso determinare quali algoritmi, tipi di connessione e protocolli sono attualmente utilizzati dalla mia organizzazione?

Il software FTP/SFTP utilizzato deve indicare quali impostazioni specifiche vengono utilizzate nelle connessioni configurate per lo scambio di dati con Adobe Analytics. Questo software dovrebbe includere anche la documentazione sulle diverse opzioni disponibili per le connessioni. Le opzioni che saranno supportate dopo questo aggiornamento sono ampiamente supportate e accettate nel settore.

Le opzioni di connessione che verranno rimosse sono generalmente considerate obsolete e non utilizzate nel software corrente. Se hai aggiornato il software FTP/SFTP negli ultimi tre anni, probabilmente disponi già di una connessione conforme.

## Quali funzioni di Adobe Analytics utilizzano SFTP per l’acquisizione dei dati?

Le seguenti funzioni forniscono un’opzione per caricare i dati in Adobe Analytics utilizzando SFTP.

* [Classificazioni](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-saint.html)

* [Feed dati](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datafeeds.html)

* [Origini dati](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-datasources.html)

* [Report consegnati di Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-dw-reports.html)

* Inoltre, alcune implementazioni personalizzate create tramite [Servizi tecnici](https://experienceleague.adobe.com/docs/analytics/export/ftp-and-sftp/set-up-ftp-accounts/ftp-eng-services.html) può utilizzare SFTP per scambiare dati con Adobe.

## Quali modifiche specifiche verranno incluse in questo aggiornamento?

Di seguito è riportato un elenco dettagliato delle connessioni e degli algoritmi che verranno rimossi e che verranno supportati:

* Algoritmi mac del protocollo SFTP:

   * Non supporteremo più: hmac-md5, hmac-md5-96, hmac-ripemd160, hmacripemd160@openssh.com, hmac-sha1, hmac-sha1-96, hmac-sha1-etm@openssh.com, umac-64-etm@openssh.com, umac-64@openssh.com

   * Sosterremo solo: hmac-sha2-512-etm@openssh.com, hmac-sha2-256-etm@openssh.com, umac-128-etm@openssh.com, hmac-sha2-512, hmacsha2-256, umac-128@openssh.com

* Algoritmo di crittografia del protocollo SFTP:

   * Non supporteremo più: 3des-cbc, aes128-cbc, aes128-gcm@openssh.com, aes192-cbc, aes256-cbc, aes256-gcm@openssh.com, arcfour, arcfour128, arcfour256, blowfish-cbc, cast128-cbc, rijndael-cbc@lysator.liu.se

   * Sosterremo solo: aes128-ctr, aes192-ctr, aes256-ctr

* Connessioni supportate dal protocollo SFTP:

   * Non supporteremo più l&#39;utilizzo di comandi scp e rsync o connessioni tramite il protocollo sftp

   * Supporteremo solo connessioni di protocollo SFTP pure

* Client/protocolli FTP/SFTP supportati:

   * FTP: vsftpd versione 3.0.2-25 o successiva

   * SFTP: openssh versione 7.4p1-21 o successiva
