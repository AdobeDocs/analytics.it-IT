---
description: SFTP è un protocollo protetto per il trasferimento di dati che ne impediscono la visualizzazione ai dati. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i tuoi dati.
keywords: ftp; sftp
seo-description: SFTP è un protocollo protetto per il trasferimento di dati che ne impediscono la visualizzazione ai dati. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i tuoi dati.
seo-title: Secure File Transfer Protocol - overview
solution: Analytics
title: Secure File Transfer Protocol - overview
uuid: 7 dd 1 a 867-e 828-4 c 7 b-bf 11-75 a 81 d 4 c 149 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Secure File Transfer Protocol - overview

SFTP è un protocollo protetto per il trasferimento di dati che ne impediscono la visualizzazione ai dati. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i tuoi dati.

## Consegna push {#section_A47831BB1DCA490BB57F0940617AA506}

Significa che i server Adobe inviano i file in modalità "push" ai tuoi server; in altre parole i file vengono consegnati presso il tuo end point.

[I feed dati di Data Warehouse](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md#concept_904ADB7B4FE04DCCB90EFDB6D0DB1076) e [Analytics](https://marketing.adobe.com/resources/help/en_US/reference/analytics-data-feed.html) possono inviare dati tramite SFTP.

The following Analytics tools **cannot** push data via SFTP:

* Reporting e analisi
* Ad Hoc Analysis
* Generatore di report

## Consegna pull {#section_FA29FAEF02FE40B8B32452146A036F48}

Ciò significa che il file viene inviato a uno dei server Adobe utilizzando il normale FTP. Se desideri il file sul tuo server, devi estrarlo dal server di Adobe utilizzando SFTP dal server al server FTP di Adobe. Puoi eseguire questa operazione seguendo uno di questi tre metodi:

* [Connettiti ad Adobe tramite SFTP senza una password.](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md#concept_962A381F42A4472AA366A08CCC962846)
* [Connetti a un account Adobe FTP con SFTP.](../../../export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md#concept_01176600188441C6AFB28F5E264D89F8)
* Puoi inviare tramite push qualsiasi report desideri a feed dati/R&amp;A/Ad Hoc simil-FTP di Adobe e così via, e recuperarli in pull. Adobe non può consegnare questi rapporti al server SFTP configurato.

