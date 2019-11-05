---
description: I feed dati sono un'esportazione dei dati clickstream ricevuti da Adobe, che offre sia feed di dati standard, che personalizzati.
keywords: ftp;sftp
seo-description: I feed dati sono un'esportazione dei dati clickstream ricevuti da Adobe, che offre sia feed di dati standard, che personalizzati.
seo-title: Feed dati
solution: Analytics
title: Feed dati
uuid: 3c70eea3-ca59-4aa5-9b11-64e1bb677bfa
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Feed dati

I feed dati sono un esportazione dei dati clickstream ricevuti da Adobe, la quale offre sia [feed dati](/help/export/analytics-data-feed/c-getstarted/data-feed-overview.md) standard, che personalizzati.

Se hai acquistato Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] puoi configurare i tuoi feed di dati Analytics. Questi feed possono essere inviati a un qualsiasi account FTP (uno configurato da Adobe o un FTP esterno). Adobe Engineering Services offers custom [!UICONTROL Data Feeds] that can be sent by virtually any means.

[!UICONTROL Data Feed]Per impostazione predefinita, gli account FTP consentono 2 GB o 63 file. Tutti gli altri account FTP standard consentono di archiviare 50 MB, per impostazione predefinita. Quando i client utilizzano l'account FTP in maniera corretta e per il proprio utilizzo previsto, alcuni utenti che generano elevate quantità di traffico potrebbero riempire velocemente questi account. Quando un account FTP è pieno, non è possibile trasmettervi in push nessun altro file. Therefore, any files being delivered to that FTP account ( [!UICONTROL Data Feeds], data warehouse requests, and so forth) are not delivered. Questo è solo uno dei motivi per cui è importante gestire il tuo account Adobe FTP rimuovendo i file ricevuti e già scaricati.

Quando un account FTP è pieno dovrai scaricare e rimuovere tutti i file contenuti e comunicare ad Adobe che è stato liberato spazio utile. Adobe può quindi inviare nuovamente file eventualmente non consegnati. Alcuni strumenti, come ad esempio data warehouse, permettono agli utenti di inviare nuovamente tali file. Il nuovo invio potrebbe non richiedere l'intervento di Adobe. Se ritieni che il tuo account FTP si riempia velocemente, contatta l'Assistenza clienti di Adobe, la quale può consigliarti alternative per la consegna che possono includere un aumento dello spazio FTP e della porzione dedicata ai file nell'account.

Per informazioni sulla conservazione dei dati e sui limiti dell'FTP, consulta [Conservazione dei dati e limitazioni dell'FTP](/help/export/ftp-and-sftp/ftp-limits.md).
