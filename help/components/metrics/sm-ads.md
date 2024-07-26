---
title: Metriche degli annunci multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Ads] per una suite di rapporti.
feature: Metrics
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 5%

---

# Metriche degli annunci multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Ads] per una suite di rapporti. Per informazioni sulle dimensioni disponibili, vedere [Dimensioni annuncio file multimediali in streaming](../dimensions/sm-ads.md).*

Le metriche degli annunci per contenuti multimediali in streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di raccolta di contenuti multimediali in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Per informazioni, contatta il team dell’account Adobe.

Quando abiliti **[!UICONTROL Media Ads]** in [Report multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Annuncio completato | Attivazione al completamento di un annuncio video. | Chiusura annuncio | `a.media.ad.complete` |
| Avvio annuncio | Attivazione all’avvio di un annuncio video. | Avvio annuncio | `a.media.ad.view` |
| Tempo trascorso dell’annuncio | La quantità totale di tempo trascorso a guardare l’annuncio, in secondi. | Chiusura annuncio | `a.media.ad.timePlayed` |
| Tempo trascorso dei contenuti multimediali | Somma la durata dell’evento per tutti gli eventi PLAY (sia contenuti principali che annuncio), in secondi. | Chiusura file multimediale | `a.media.totalTimePlayed` |

{style="table-layout:auto"}
