---
description: Scopri come utilizzare i feed di dati per estrarre dati non elaborati da Adobe Analytics. Scopri i prerequisiti per l’utilizzo dei feed di dati e cosa fare dopo.
keywords: clickstream;feed dati;datafeed;feed dati
title: Panoramica sui feed dati di Analytics
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
TQID: 'https://experienceleague.adobe.com/XVFQdMEfIM7lQlnU3b-zRbQ9-RliqtaBjr-7ptxkI1o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: ede9f3ba-4ee4-4497-9d8e-e9da5848bda0
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 335
ht-degree: 77%

---

# Panoramica sui feed dati di Analytics

I feed di dati offrono un modo potente per estrarre dati grezzi da Adobe Analytics. Puoi utilizzare i dati non elaborati in altre piattaforme al di fuori di Adobe, in base alle esigenze della tua organizzazione. I dati vengono consegnati in batch orari alla conclusione di ogni ora oppure in batch giornalieri alla conclusione di ogni giorno.

## Prerequisiti

Prima di utilizzare i feed di dati, è necessario soddisfare tutti i seguenti requisiti.

* Un’implementazione funzionante che invia dati ai server di raccolta dati di Adobe. Consulta [Convalidare e pubblicare un’implementazione](/help/implement/launch/validate-publish-prod.md) nella Guida per l’implementazione.
* Il tuo account deve essere quello di un amministratore di prodotto Analytics oppure deve appartenere a un profilo di prodotto con accesso ai feed di dati.
* Bucket configurato su Amazon S3, Google Cloud Platform, Azure RBAC o Azure SAS.
* (Legacy: obbligatorio solo per i tipi di destinazione FTP e SFTP legacy) Tieni a portata di mano un sito FTP e le relative credenziali (credenziali FTP fornite dalla tua organizzazione).

## Passaggi successivi

Le risorse seguenti sono utili per comprendere il flusso di lavoro di base per ottenere dei feed di dati. Una volta compreso il flusso di lavoro di base, puoi lavorare con i team della tua organizzazione per archiviare o acquisire dati non elaborati in un database.

* [Best practice per il feed di dati](/help/export/analytics-data-feed/data-feeds-best-practices.md): best practice per la creazione e la gestione dei feed di dati.
* [Creare un feed di dati](create-feed.md): dettagli tecnici per la creazione di un feed di dati, con informazioni più dettagliate sui singoli campi
* [Gestire i feed dati](df-manage-feeds.md): ulteriori informazioni sulla navigazione nell’interfaccia del feed dati
* [Contenuto feed dati](c-df-contents/datafeeds-contents.md): informazioni sul contenuto del file compresso <!-- Is this still the output users can download from the destination? I aske Jun. -->
* [Definizioni delle colonne dati](c-df-contents/datafeeds-reference.md): un elenco completo di tutte le colonne disponibili.

>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Naviga nell&#39;interfaccia feed dati](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/exporting/data-feeds/data-feeds-management-ui){target="_blank"} per vedere un video dimostrativo.

>[!ENDSHADEBOX]



>[!BEGINSHADEBOX]

Consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Trova il tuo ID feed dati](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/exporting/data-feeds/find-your-data-feed-id){target="_blank"} per vedere un video dimostrativo.

>[!ENDSHADEBOX]
