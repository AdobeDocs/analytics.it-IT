---
description: SFTP è un protocollo sicuro per il trasferimento di dati che garantisce che nessuno possa visualizzare i tuoi dati, a parte te. Adobe Engineering Services può configurare un account SFTP per la conservazione sicura dei dati.
keywords: ftp;sftp
title: 'Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica'
feature: FTP Export
exl-id: ea0448f9-1685-4a8f-b2f9-49d315c6ab71
TQID: https://experienceleague.adobe.com/kJYtQSuxz-2NMUYqZb01wsr6ltQQbD5itpPYYzsmlCM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 220
ht-degree: 5%

---

# Secure File Transfer Protocol (protocollo di trasferimento file sicuro): panoramica

SFTP è un protocollo sicuro per il trasferimento di dati che garantisce che nessuno possa visualizzare i tuoi dati, a parte te. Adobe Engineering Services può configurare un account SFTP per la conservazione sicura dei dati.

## Consegna push {#section_A47831BB1DCA490BB57F0940617AA506}

Ciò significa che i server di Adobe &quot;inviano&quot; il file ai server. In sostanza, li consegniamo al vostro punto finale.

[Data Warehouse](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-dw.md) e [Feed dati di Analytics](/help/export/analytics-data-feed/data-feed-overview.md) possono inviare dati tramite SFTP.

Report Builder **non può** inviare dati tramite SFTP.

## Consegna pull {#section_FA29FAEF02FE40B8B32452146A036F48}

Questo significa che il file viene inviato a uno dei server di Adobe utilizzando il normale FTP. Se desideri che il file si trovi sul server, devi estrarlo dal server di Adobe utilizzando SFTP dal server al server FTP di Adobe. Puoi eseguire questa operazione utilizzando uno dei tre metodi seguenti:

* [Connettiti ad Adobe tramite SFTP senza password.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-cert-auth.md)
* [Connettiti a un account FTP di Adobe con SFTP.](/help/export/ftp-and-sftp/c-sftp/ftp-sftp-connect.md)
* Puoi inviare tutti i rapporti che desideri ai feed di dati/R&amp;A/Ad Hoc di Adobe di tipo FTP e così via, quindi estrarli. Adobe non può inviare questi rapporti al server SFTP configurato.
