---
description: Informazioni su come Adobe consente l'accesso a Origini dati.
seo-description: Informazioni su come Adobe consente l'accesso a Origini dati.
seo-title: Funzionamento delle Origini dati
solution: Analytics
subtopic: Origini dati
title: Funzionamento delle Origini dati
topic: Sviluppatore e implementazione
uuid: ee 9 e 6 e 74-9 b 00-4733-9 a 4 b-d 9 f 2 b 954 cc 7 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Funzionamento delle Origini dati

Informazioni su come Adobe consente l'accesso a Origini dati.

>[!NOTE]
>
>Una volta inviati tramite Origini dati, i dati importati non sono distinguibili dai dati di reporting raccolti utilizzando altri metodi (beacon javascript, actionsource, API di inserimento dati, ecc.). Non puoi rimuovere i dati una volta importati.

![](assets/data_sources_overview.png)

Sono disponibili due metodi per inviare i dati:

* [FTP](../../import/c-data-sources/datasrc-how-data-sources-works.md#section_0E70022648F94061AF5B4AD6C7145243)
* [API](../../import/c-data-sources/datasrc-how-data-sources-works.md#section_65DACC9CE00C437BBFDD02D19C25A4BD)

## FTP {#section_0E70022648F94061AF5B4AD6C7145243}

Puoi creare e gestire origini dati basate su FTP tramite rapporti di marketing, utilizzando il trasferimento di file FTP per importare file di dati in Origini dati. Dopo la creazione di un'origine dati, Adobe ti fornisce un percorso FTP che puoi utilizzare per caricare i file Origini dati. Una volta caricati, Origini dati li individua automaticamente e li elabora. Una volta elaborati, i dati sono disponibili per i rapporti di marketing.

## API {#section_65DACC9CE00C437BBFDD02D19C25A4BD}

Adobe offre un'API Origini dati che ti consente di collegare sistematicamente le tue applicazioni in Origini dati. Ciò elimina la necessità di un server FTP intermediario e trasferisce i dati tramite HTTP, SOAP e REST.

Consulta [Documentazione sull'API Origini dati](https://marketing.adobe.com/developer/documentation/data-sources/c-data-sources-api).
