---
description: I feed di dati sono un’esportazione dei dati di click-stream ricevuti da Adobe che offre feed di dati sia standard che personalizzati.
keywords: ftp;sftp
title: Feed dati
feature: FTP Export
exl-id: 286050fa-e197-4b70-b167-da6921615c1b
TQID: https://experienceleague.adobe.com/SWXC-g3KTGuKiT0CBFfptUSBigs8pgkPVdRLzWhl6z4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 322
ht-degree: 1%

---

# Feed dati

>[!NOTE]
>
>Le seguenti informazioni sono relative ai tipi di destinazione FTP e SFTP. FTP e SFTP sono tipi di destinazione legacy. Durante la configurazione di un feed di dati, è necessario utilizzare un tipo di destinazione cloud più sicuro. Per ulteriori informazioni sulla configurazione dei tipi di destinazione cloud per un feed dati, vedere [Creare un feed dati](/help/export/analytics-data-feed/create-feed.md).

I feed di dati sono un&#39;esportazione dei dati clickstream ricevuti da Adobe che offre [feed di dati](/help/export/analytics-data-feed/data-feed-overview.md) standard e personalizzati.

Se hai acquistato Adobe Data Warehouse, [!UICONTROL Standard Data Feeds] puoi impostare i tuoi feed dati di Analytics. Possono essere inviati a qualsiasi account FTP (configurato da Adobe o da un FTP esterno). Adobe Engineering Services offre [!UICONTROL Data Feeds] personalizzati che possono essere inviati con qualsiasi mezzo.

[!UICONTROL Data Feed] account FTP consentono 10 GB (per impostazione predefinita). Tutti gli altri account FTP standard hanno una dimensione predefinita di 50 MB. Nei casi in cui i clienti utilizzano l’account FTP per il suo corretto utilizzo, alcuni utenti con grandi quantità di traffico possono riempire rapidamente questi account. Quando un account FTP è pieno, non è possibile inviare loro altri file. Di conseguenza, tutti i file consegnati a tale account FTP ( [!UICONTROL Data Feeds], richieste data warehouse e così via) non vengono consegnati. Questo è uno dei motivi per cui è importante gestire il tuo account FTP di Adobe rimuovendo i file che sono stati ricevuti e scaricati.

Quando un account FTP è pieno, devi scaricare e rimuovere i file correnti e comunicare ad Adobe che lo spazio è stato cancellato. Adobe può quindi inviare nuovamente i file che non sono stati consegnati. Alcuni strumenti, ad esempio data warehouse, consentono agli utenti di inviare nuovamente questi file. L’invio può non richiedere il coinvolgimento di Adobe. Se l’account FTP sembra riempirsi frequentemente, contatta l’Assistenza clienti di Adobe, che può suggerire alternative di consegna che possono includere l’aumento dello spazio FTP e della quota del numero di file sull’account.
