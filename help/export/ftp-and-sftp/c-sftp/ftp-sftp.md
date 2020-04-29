---
description: SFTP è un protocollo sicuro per il trasferimento di dati che assicura che nessuno possa vedere i tuoi dati tranne te. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i dati.
keywords: ftp;sftp
title: 'Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica'
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica

SFTP è un protocollo sicuro per il trasferimento di dati che assicura che nessuno possa vedere i tuoi dati tranne te. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i dati.

## Consegna push {#section_A47831BB1DCA490BB57F0940617AA506}

Significa che i server Adobe inviano i file in modalità &quot;push&quot; ai tuoi server; in altre parole i file vengono consegnati presso il tuo end point.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) e Feed [dati di](https://docs.adobe.com/content/help/it-IT/analytics/export/analytics-data-feed/data-feed-overview.html) Analytics possono inviare dati push tramite SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis 
* Report Builder

## Consegna pull {#section_FA29FAEF02FE40B8B32452146A036F48}

Ciò significa che il file viene inviato a uno dei server Adobe utilizzando il normale FTP. Se desideri il file sul tuo server, devi estrarlo dal server di Adobe utilizzando SFTP dal tuo server al server FTP di Adobe. Puoi eseguire questa operazione seguendo uno di questi tre metodi:

* [Connessione ad Adobe tramite SFTP senza password.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Connessione a un account Adobe FTP con SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Puoi inviare tramite push qualsiasi report desideri a feed dati/R&amp;A/Ad Hoc simil-FTP di Adobe e così via, e recuperarli in pull. Adobe non può inviare questi rapporti al server SFTP configurato.

