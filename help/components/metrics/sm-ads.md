---
title: Metriche e servizi multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Ads] per una suite di rapporti.
feature: Metrics
exl-id: f0ddf3e0-ab55-4a05-a8ae-f040ba26e704
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 5%

---

# Metriche e servizi multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Ads] per una suite di rapporti. Vedere [Dimensioni annuncio servizi multimediali in streaming](../dimensions/sm-ads.md) per le dimensioni disponibili.*

I servizi e le metriche di Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di servizi multimediali in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Ads]** in [Report multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Annuncio completato | Attivazione al completamento di un annuncio video. | Chiusura annuncio | `a.media.ad.complete` |
| Avvio annuncio | Attivazione all’avvio di un annuncio video. | Avvio annuncio | `a.media.ad.view` |
| Tempo trascorso dell’annuncio | La quantità totale di tempo trascorso a guardare l’annuncio, in secondi. | Chiusura annuncio | `a.media.ad.timePlayed` |
| Tempo trascorso dei contenuti multimediali | Somma la durata dell’evento per tutti gli eventi PLAY (sia contenuti principali che annuncio), in secondi. | Chiusura file multimediale | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
