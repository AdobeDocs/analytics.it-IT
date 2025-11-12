---
title: Dimensioni dei metadati video di Streaming Media Services
description: Dimensioni disponibili quando si abilita [!UICONTROL Video Metadata] per una suite di rapporti.
feature: Dimensions
exl-id: e476c19a-9542-4a6f-9b79-5f801e2a7bf8
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Dimensioni dei metadati video di Streaming Media Services

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Video Metadata] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere [Metriche metadati video di Streaming Media Services](../metrics/sm-video-metadata.md).*

I servizi e le dimensioni di Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dati tramite le librerie di raccolta di servizi multimediali in streaming. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Video Metadata]** in [Generazione rapporti multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le seguenti dimensioni:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad loads]** | Tipo di annuncio caricato. | | `a.media.adLoad` | `xdm.mediaCollection.`<br>`sessionDetails.adLoad` |
| **[!UICONTROL Day part]** | L’ora del giorno in cui il contenuto è stato trasmesso o riprodotto. Qualsiasi valore stringa è supportato. | Avvio file multimediale, Chiusura file multimediale | `a.media.dayPart` | `xdm.mediaCollection.`<br>`sessionDetails.dayPart`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.dayPart` |
| **[!UICONTROL Episode]** | Numero dell’episodio. | Avvio file multimediale, Chiusura file multimediale | `a.media.episode` | `xdm.mediaCollection.`<br>`sessionDetails.episode`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.episode` |
| **[!UICONTROL Media feed type]** | Tipo di feed. | Avvio file multimediale, Chiusura file multimediale | `a.media.feed` | `xdm.mediaCollection.`<br>`sessionDetails.feed`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.feed` |
| **[!UICONTROL Genre]** | Tipo o raggruppamento di contenuti definiti dal produttore del contenuto. Questa dimensione supporta più valori, delimitati da virgole. | Avvio file multimediale, Chiusura file multimediale | `a.media.genre` | `xdm.mediaCollection.`<br>`sessionDetails.genre`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.genreList` |
| **[!UICONTROL MVPD]** | Il MVPD fornito dall’autenticazione di Adobe. | Avvio file multimediale, Chiusura file multimediale | `a.media.pass.mvpd` | `xdm.mediaCollection.`<br>`sessionDetails.mvpd`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.mvpd` |
| **[!UICONTROL Network]** | Il nome della rete o del canale. | Avvio file multimediale, Chiusura file multimediale | `a.media.network` | `xdm.mediaCollection.`<br>`sessionDetails.network`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.network` |
| **[!UICONTROL Season]** | Il numero di stagione a cui appartiene lo spettacolo. | Avvio file multimediale, Chiusura file multimediale | `a.media.season` | `xdm.mediaCollection.`<br>`sessionDetails.season`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.season` |
| **[!UICONTROL Show]** | Il nome del programma o della serie. | Avvio file multimediale, Chiusura file multimediale | `a.media.show` | `xdm.mediaCollection.`<br>`sessionDetails.show`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.show` |
| **[!UICONTROL Show type]** | Numero intero che rappresenta il tipo di contenuto.<br>`0`: episodio completo<br>`1`: anteprima o trailer<br>`2`: clip<br>`3`: altro | Avvio file multimediale, Chiusura file multimediale | `a.media.type` | `xdm.mediaCollection.`<br>`sessionDetails.showType`<br><br>`xdm.mediaReporting.`<br>`sessionDetails.showType` |

