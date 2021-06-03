---
description: SFTP è un protocollo sicuro per il trasferimento di dati che assicura che nessuno possa vedere i tuoi dati, tranne te. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i tuoi dati.
keywords: ftp;sftp
title: 'Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica'
uuid: 7dd1a867-e828-4c7b-bf11-75a81d4c149c
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 40%

---

# Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica

SFTP è un protocollo sicuro per il trasferimento di dati che assicura che nessuno possa vedere i tuoi dati, tranne te. Adobe Engineering Services può configurare un account SFTP per conservare in modo sicuro i tuoi dati.

## Consegna push {#section_A47831BB1DCA490BB57F0940617AA506}

Significa che i server Adobe inviano i file in modalità &quot;push&quot; ai tuoi server; in altre parole i file vengono consegnati presso il tuo end point.

[Data ](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) Warehouse e  [Analytics Data ](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html) Feedback possono inviare dati in push tramite SFTP.

I seguenti strumenti di Analytics **non possono** inviare dati push tramite SFTP:

* Reports &amp; Analytics
* Ad Hoc Analysis
* Report Builder

## Consegna pull {#section_FA29FAEF02FE40B8B32452146A036F48}

Ciò significa che il file viene inviato a uno dei server Adobe utilizzando il normale FTP. Se desideri il file sul server, devi estrarlo dal server Adobe utilizzando SFTP dal server al server FTP Adobe. Puoi eseguire questa operazione seguendo uno di questi tre metodi:

* [Connessione ad Adobe tramite SFTP senza password.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Connessione a un account FTP di Adobe con SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Puoi inviare tramite push qualsiasi report desideri a feed dati/R&amp;A/Ad Hoc simil-FTP di Adobe e così via, e recuperarli in pull. Adobe non è in grado di inviare questi report al server SFTP configurato.
