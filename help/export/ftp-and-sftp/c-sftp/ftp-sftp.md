---
description: SFTP è un protocollo sicuro per il trasferimento di dati che garantisce che nessuno possa visualizzare i tuoi dati, a parte te. Adobe Engineering Services può configurare un account SFTP per la conservazione sicura dei dati.
keywords: ftp;sftp
title: 'Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica'
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 37%

---

# Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica

SFTP è un protocollo sicuro per il trasferimento di dati che garantisce che nessuno possa visualizzare i tuoi dati, a parte te. Adobe Engineering Services può configurare un account SFTP per la conservazione sicura dei dati.

## Consegna push {#section_A47831BB1DCA490BB57F0940617AA506}

Significa che i server Adobe inviano i file in modalità &quot;push&quot; ai tuoi server; in altre parole i file vengono consegnati presso il tuo end point.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) e [Feed dati di Analytics](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=it) può inviare dati tramite SFTP.

Report Builder **non può** inviare dati tramite SFTP.

## Consegna pull {#section_FA29FAEF02FE40B8B32452146A036F48}

Ciò significa che il file viene inviato a uno dei server Adobe utilizzando il normale FTP. Se desideri che il file si trovi sul server, devi estrarlo dal server di Adobe utilizzando SFTP dal server al server FTP di Adobe. Puoi eseguire questa operazione seguendo uno di questi tre metodi:

* [Connettiti a Adobe tramite SFTP senza password.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Connettiti a un account FTP di Adobe con SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Puoi inviare tramite push qualsiasi report desideri a feed dati/R&amp;A/Ad Hoc simil-FTP di Adobe e così via, e recuperarli in pull. L’Adobe non può consegnare questi rapporti al server SFTP configurato.
