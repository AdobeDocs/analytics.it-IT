---
description: Risorse e collegamenti per l’API di reporting.
title: API di reportistica di Analytics
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: 8f25dfefbc6fba1fb525d2e9e0fce654e21ef362
workflow-type: tm+mt
source-wordcount: '132'
ht-degree: 92%

---

# API di reportistica di Analytics

La documentazione per le API di Adobe Analytics è disponibile su [Sviluppatore Adobe](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Confronto delle API di Analytics

| **Tipo API** | **Elaborazione completa** | **Tempo reale** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Descrizione** | Dati completamente elaborati e finalizzati disponibili in tutte le interfacce di Analytics. | Metriche limitate ed elaborate parzialmente, disponibili entro pochi secondi dalla raccolta. | Dati dei risultati elaborati parzialmente, disponibili entro pochi secondi dalla raccolta. | Dati completamente elaborati e finalizzati utilizzati per eseguire il pull di esportazioni dati di grandi dimensioni. |
| [**Latenza**](/help/technotes/latency.md) | 30-90 minuti | Secondi -10 minuti | Secondi -10 minuti | 90+ minuti |
| **Completamento elaborazione** | a schermo intero | Parziale | Parziale | a schermo intero |
| **Interfacce di reporting** | Analysis Workspace, Reports &amp; Analytics, Report Builder, API | Rapporti in tempo reale in Reports &amp; Analytics, Report Builder, API 1.4 | Solo API | Data Warehouse, API |
| **Granularità dei dati** | Di riepilogo | Di riepilogo | Livello di hit | Di riepilogo |
| **Elaborazione profilo visitatore** | Sì | No | No | Sì |
| **Supporto dei segmenti** | Sì | No | No | Parziale |
