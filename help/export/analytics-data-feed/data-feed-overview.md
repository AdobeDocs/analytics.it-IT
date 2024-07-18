---
description: I dati raccolti da siti web, app mobili o caricati utilizzando API di servizi web o origini dati, vengono elaborati e memorizzati nel Data Warehouse di Adobe. Questi dati di click-stream non elaborati formano il set di dati utilizzato da Adobe Analytics.
keywords: clickstream;feed dati;datafeed;feed dati
title: Panoramica sui feed dati di Analytics
feature: Data Feeds
exl-id: 2cfff9ad-cdb5-4ae9-a266-4f3d3d046f0c
source-git-commit: 84bdeb5d502e46c922fc5123fcdd5b6819426c0e
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 96%

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
* Video sulla navigazione nell’interfaccia del feed dati:

  >[!VIDEO](https://video.tv.adobe.com/v/25452/?quality=12)

* Video su come trovare l’ID del proprio feed dati:

  >[!VIDEO](https://video.tv.adobe.com/v/335747/?quality=12)