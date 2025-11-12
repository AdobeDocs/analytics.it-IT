---
title: Dimensioni dei metadati audio di Streaming Media Services
description: Dimensioni disponibili quando si abilita [!UICONTROL Audio Metadata] per una suite di rapporti.
feature: Dimensions
exl-id: 2e4dc1e9-267b-47a2-b791-23d1e754a2c1
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '134'
ht-degree: 4%

---

# Dimensioni dei metadati audio di Streaming Media Services

I servizi e le dimensioni di Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di Streaming Media Services. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Audio Metadata]** in [Generazione rapporti multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Album]** | Nome dell&#39;album. | Avvio file multimediale, Chiusura file multimediale | `a.media.album` | `xdm.mediaCollection.`<br>`sessionDetails.album`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.album` |
| **[!UICONTROL Artist]** | Il nome dell&#39;artista. | Avvio file multimediale, Chiusura file multimediale | `a.media.artist` | `xdm.mediaCollection.`<br>`sessionDetails.artist`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.artist` |
| **[!UICONTROL Author]** | Nome dell&#39;autore dell&#39;audiolibro. | Avvio file multimediale, Chiusura file multimediale | `a.media.author` | `xdm.mediaCollection.`<br>`sessionDetails.author`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.author` |
| **[!UICONTROL Label]** | Nome dell&#39;etichetta discografica. | Avvio file multimediale, Chiusura file multimediale | `a.media.label` | `xdm.mediaCollection.`<br>`sessionDetails.label`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.label` |
| **[!UICONTROL Publisher]** | Nome dell&#39;autore del contenuto audio. | Avvio file multimediale, Chiusura file multimediale | `a.media.publisher` | `xdm.mediaCollection.`<br>`sessionDetails.publisher`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.publisher` |
| **[!UICONTROL Station]** | Nome o ID della stazione radio. | Avvio file multimediale, Chiusura file multimediale | `a.media.station` | `xdm.mediaCollection.`<br>`sessionDetails.station`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.station` |
