---
description: Informazioni su come Adobe consente l'accesso a Origini dati.
subtopic: Data sources
title: Funzionamento di Origini dati
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 81%

---


# Funzionamento di Origini dati

Informazioni su come Adobe consente l&#39;accesso a Origini dati.

>[!NOTE]
>
>Una volta inviati tramite Origini dati, i dati importati non sono distinguibili dai dati di reporting raccolti utilizzando altri metodi (beacon JavaScript, ActionSource, API di inserimento dati, ecc.). Non puoi rimuovere i dati una volta importati.

![](assets/data_sources_overview.png)

Sono disponibili due metodi per inviare i dati:

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

Puoi creare e gestire origini dati basate su FTP tramite rapporti di marketing, utilizzando il trasferimento di file FTP per importare file di dati in Origini dati. Dopo la creazione di un&#39;origine dati, Adobe ti fornisce un percorso FTP che puoi utilizzare per caricare i file Origini dati. Una volta caricati, Origini dati li individua automaticamente e li elabora. Una volta elaborati, i dati sono disponibili per i rapporti di marketing.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe offre un&#39;API Origini dati che ti consente di collegare sistematicamente le tue applicazioni in Origini dati. Ciò elimina la necessità di un server FTP intermediario e trasferisce i dati tramite HTTP, SOAP e REST.

Consulta [Documentazione sull&#39;API Origini dati](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api).
