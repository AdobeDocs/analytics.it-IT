---
description: Risorse e collegamenti per l’API di reporting.
title: API di reportistica di Analytics
uuid: 68ec3490-6e47-4606-860d-dd5e89c574a1
feature: API
role: Developer
exl-id: 003a8b83-6ef0-4313-903a-b76078558d55
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 90%

---

# API di reportistica di Analytics

La documentazione delle API di Adobe Analytics è disponibile su [Adobe Developer](https://developer.adobe.com/analytics-apis/docs/2.0/).

## Confronto delle API di Analytics

| **Tipo API** | **Elaborazione completa** | **Tempo reale** | **Livestream** | **Data Warehouse** |
| --- | --- | --- | --- | --- |
| **Descrizione** | Dati completamente elaborati e finalizzati disponibili in tutte le interfacce di Analytics. | Metriche limitate ed elaborate parzialmente, disponibili entro pochi secondi dalla raccolta. | Dati dei risultati elaborati parzialmente, disponibili entro pochi secondi dalla raccolta. | Dati completamente elaborati e finalizzati utilizzati per eseguire il pull di esportazioni dati di grandi dimensioni. |
| [**Latenza**](/help/technotes/latency.md) | 30-90 minuti | Secondi -10 minuti | Secondi -10 minuti | 90+ minuti |
| **Completamento elaborazione** | a schermo intero | Parziale | Parziale | a schermo intero |
| **Interfacce di reporting** | Analysis Workspace, Report Builder, API | Rapporto in tempo reale in Report Builder, API 1.4 | Solo API | Data Warehouse, API |
| **Granularità dei dati** | Di riepilogo | Di riepilogo | Livello di hit | Di riepilogo |
| **Elaborazione profilo visitatore** | Sì | No | No | Sì |
| **Supporto dei segmenti** | Sì | No | No | Parziale |
