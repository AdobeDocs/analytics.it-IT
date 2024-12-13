---
title: Metriche dei capitoli per contenuti multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Chapters] per una suite di rapporti.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: fdd66c9558f070cd760f37a39e5911f0dac22612
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 6%

---

# Metriche dei capitoli per contenuti multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti. Per informazioni sulle dimensioni disponibili, vedere [Dimensioni del capitolo di Streaming Media](../dimensions/sm-chapters.md).*

Le metriche dei capitoli di Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di raccolta di contenuti multimediali in streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Streaming Media Collection]**. Per informazioni, contatta il team dell’account Adobe.

Quando abiliti **[!UICONTROL Media Chapters]** in [Report multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Completamenti del capitolo | Valore booleano che viene attivato al completamento di un capitolo. | Chiusura capitolo | `a.media.chapter.complete` |
| Inizio capitolo | Valore booleano che viene attivato all’avvio di un capitolo. | Inizio capitolo | `a.media.chapter.view` |
| Tempo trascorso su capitolo | La quantità di tempo trascorso sul capitolo, in secondi. | Chiusura capitolo | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
