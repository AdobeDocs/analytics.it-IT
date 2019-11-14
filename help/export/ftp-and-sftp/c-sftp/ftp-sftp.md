---
description: SFTP è un protocollo sicuro per il trasferimento di dati che assicura che nessuno possa vedere i tuoi dati tranne te. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i dati.
keywords: ftp;sftp
solution: Analytics
title: 'Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica'
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica

SFTP è un protocollo sicuro per il trasferimento di dati che assicura che nessuno possa vedere i tuoi dati tranne te. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i dati.

## Consegna push {#section_A47831BB1DCA490BB57F0940617AA506}

Significa che i server Adobe inviano i file in modalità "push" ai tuoi server; in altre parole i file vengono consegnati presso il tuo end point.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) e Feed [dati](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) Analytics possono inviare dati push tramite SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reporting e analisi
* Ad Hoc Analysis
* Report Builder

## Consegna pull {#section_FA29FAEF02FE40B8B32452146A036F48}

Ciò significa che il file viene inviato a uno dei server Adobe utilizzando il normale FTP. Se desideri il file sul tuo server, devi estrarlo dal server di Adobe utilizzando SFTP dal server al server FTP di Adobe. Puoi eseguire questa operazione seguendo uno di questi tre metodi:

* [Connessione ad Adobe tramite SFTP senza password.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Connessione a un account Adobe FTP con SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Puoi inviare tramite push qualsiasi report desideri a feed dati/R&amp;A/Ad Hoc simil-FTP di Adobe e così via, e recuperarli in pull. Adobe non può inviare questi rapporti al server SFTP configurato.

