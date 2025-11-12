---
title: Metriche e servizi multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Ads] per una suite di rapporti.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 5%

---

# Metriche e servizi multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Ads] per una suite di rapporti. Vedere [Dimensioni annuncio servizi multimediali in streaming](../dimensions/sm-ads.md) per le dimensioni disponibili.*

I servizi e le metriche di Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di servizi multimediali in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Ads]** in [Report multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Ad completes]** | Attivazione al completamento di un annuncio video. | Chiusura annuncio | `a.media.ad.complete` | `xdm.mediaReporting.`<br>`advertisingDetails.isCompleted` |
| **[!UICONTROL Ad starts]** | Attivazione all’avvio di un annuncio video. | Avvio annuncio | `a.media.ad.view` | `xdm.mediaReporting.`<br>`advertisingDetails.isStarted` |
| **[!UICONTROL Ad time spent]** | La quantità totale di tempo trascorso a guardare l’annuncio, in secondi. | Chiusura annuncio | `a.media.ad.timePlayed` | `xdm.mediaReporting.`<br>`advertisingDetails.timePlayed` |
| **[!UICONTROL Media time spent]** | Somma la durata dell&#39;evento per tutti gli eventi &#39;[!UICONTROL Play]&#39; (sia contenuto principale che annuncio), in secondi. | Chiusura file multimediale | `a.media.totalTimePlayed` | `xdm.mediaReporting.`<br>`sessionDetails.totalTimePlayed` |
