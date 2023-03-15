---
description: I feed dati sono un'esportazione dei dati clickstream ricevuti da Adobe, che offre sia feed di dati standard, che personalizzati.
keywords: ftp;sftp
title: Feed dati
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 80%

---

# Feed dati

I feed dati sono un esportazione dei dati clickstream ricevuti da Adobe, la quale offre sia [feed dati](/help/export/analytics-data-feed/data-feed-overview.md) standard, che personalizzati.

Se hai acquistato Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] puoi impostare feed dati di Analytics personalizzati. Questi feed possono essere inviati a un qualsiasi account FTP (uno configurato da Adobe o un FTP esterno). Adobe Engineering Services offre servizi personalizzati [!UICONTROL Data Feeds] che possono essere inviate con qualsiasi mezzo.

[!UICONTROL Data Feed]Gli account FTP consentono 10 GB (per impostazione predefinita). Tutti gli altri account FTP standard consentono di archiviare 50 MB, per impostazione predefinita. Quando i client utilizzano l&#39;account FTP in maniera corretta e per il proprio utilizzo previsto, alcuni utenti che generano elevate quantità di traffico potrebbero riempire velocemente questi account. Quando un account FTP è pieno, non è possibile trasmettervi in push nessun altro file. Di conseguenza, tutti i file inviati a tale account FTP ( [!UICONTROL Data Feeds], richieste di data warehouse e così via) non vengono consegnate. Questo è solo uno dei motivi per cui è importante gestire il tuo account Adobe FTP rimuovendo i file ricevuti e già scaricati.

Quando un account FTP è pieno dovrai scaricare e rimuovere tutti i file contenuti e comunicare ad Adobe che è stato liberato spazio utile. Adobe può quindi inviare nuovamente file eventualmente non consegnati. Alcuni strumenti, come ad esempio data warehouse, permettono agli utenti di inviare nuovamente tali file. Il nuovo invio potrebbe non richiedere l&#39;intervento di Adobe. Se ritieni che il tuo account FTP si riempia velocemente, contatta l&#39;Assistenza clienti di Adobe, la quale può consigliarti alternative per la consegna che possono includere un aumento dello spazio FTP e della porzione dedicata ai file nell&#39;account.
