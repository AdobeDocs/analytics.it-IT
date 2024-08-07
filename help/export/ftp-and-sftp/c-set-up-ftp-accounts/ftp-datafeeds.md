---
description: I feed dati sono un'esportazione dei dati clickstream ricevuti da Adobe, che offre sia feed di dati standard, che personalizzati.
keywords: ftp;sftp
title: Feed dati
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
source-git-commit: 05b4dc07de567b25e71b47fd92743bee0b5621f8
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 61%

---

# Feed dati

>[!NOTE]
>
>Le seguenti informazioni sono relative ai tipi di destinazione FTP e SFTP. FTP e SFTP sono tipi di destinazione legacy. Durante la configurazione di un feed di dati, è necessario utilizzare un tipo di destinazione cloud più sicuro. Per ulteriori informazioni sulla configurazione dei tipi di destinazione cloud per un feed dati, vedere [Creare un feed dati](/help/export/analytics-data-feed/create-feed.md).

I feed di dati sono un&#39;esportazione dei dati clickstream ricevuti da Adobe che offre [feed di dati](/help/export/analytics-data-feed/data-feed-overview.md) sia standard che personalizzati.

Se hai acquistato Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] puoi impostare feed di dati di Analytics personalizzati. Questi feed possono essere inviati a un qualsiasi account FTP (uno configurato da Adobe o un FTP esterno). Adobe Engineering Services offre [!UICONTROL Data Feeds] personalizzati che possono essere inviati con qualsiasi mezzo.

[!UICONTROL Data Feed] account FTP consentono 10 GB (per impostazione predefinita). Tutti gli altri account FTP standard consentono di archiviare 50 MB, per impostazione predefinita. Quando i client utilizzano l&#39;account FTP in maniera corretta e per il proprio utilizzo previsto, alcuni utenti che generano elevate quantità di traffico potrebbero riempire velocemente questi account. Quando un account FTP è pieno, non è possibile trasmettervi in push nessun altro file. Di conseguenza, tutti i file consegnati a tale account FTP ( [!UICONTROL Data Feeds], richieste data warehouse e così via) non vengono consegnati. Questo è solo uno dei motivi per cui è importante gestire il tuo account Adobe FTP rimuovendo i file ricevuti e già scaricati.

Quando un account FTP è pieno dovrai scaricare e rimuovere tutti i file contenuti e comunicare ad Adobe che è stato liberato spazio utile. Adobe può quindi inviare nuovamente file eventualmente non consegnati. Alcuni strumenti, come ad esempio data warehouse, permettono agli utenti di inviare nuovamente tali file. Il nuovo invio potrebbe non richiedere l&#39;intervento di Adobe. Se ritieni che il tuo account FTP si riempia velocemente, contatta l&#39;Assistenza clienti di Adobe, la quale può consigliarti alternative per la consegna che possono includere un aumento dello spazio FTP e della porzione dedicata ai file nell&#39;account.
