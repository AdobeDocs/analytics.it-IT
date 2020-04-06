---
description: Informazioni su come Adobe fornisce l'accesso a Origini dati.
subtopic: Data sources
title: Funzionamento di Origini dati
topic: Developer and implementation
uuid: ee9e6e74-9b00-4733-9a4b-d9f2b954cc7c
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Funzionamento di Origini dati

Informazioni su come Adobe fornisce l&#39;accesso a Origini dati.

>[!NOTE] Una volta inviati tramite Origini dati, i dati importati non sono distinguibili dai dati di reporting raccolti utilizzando altri metodi (beacon JavaScript, ActionSource, API di inserimento dati, ecc.). Non è possibile rimuovere i dati una volta importati.

![](assets/data_sources_overview.png)

Sono disponibili due metodi per inviare i dati:

* [FTP](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](/help/import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

Puoi creare e gestire origini dati basate su FTP tramite rapporti di marketing, che utilizzano il trasferimento di file FTP per importare file di dati in Origini dati. Dopo aver creato un&#39;origine dati, Adobe ti fornisce una posizione FTP che puoi utilizzare per caricare i file Origini dati. Una volta caricato, Origini dati li individua ed elabora automaticamente. Una volta elaborati, i dati sono disponibili per i rapporti di marketing.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe offre un&#39;API Origini dati che consente di collegare le applicazioni a livello di programmazione a Origini dati. Ciò elimina la necessità di un server FTP intermediario e trasferisce i dati tramite HTTP, SOAP e REST.

Consulta Documentazione [API](https://github.com/AdobeDocs/analytics-1.4-apis/tree/master/docs/data-sources-api)Origini dati.
