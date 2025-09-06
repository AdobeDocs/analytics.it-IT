---
title: Metriche dei capitoli dei servizi multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Chapters] per una suite di rapporti.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 6%

---

# Metriche dei capitoli dei servizi multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti. Vedere [Dimensioni del capitolo dei servizi multimediali in streaming](../dimensions/sm-chapters.md) per le dimensioni disponibili.*

Le metriche dei capitoli dei servizi multimediali di streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di raccolta dei servizi multimediali di streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Chapters]** in [Report multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Completamenti del capitolo | Valore booleano che viene attivato al completamento di un capitolo. | Chiusura capitolo | `a.media.chapter.complete` |
| Inizio capitolo | Valore booleano che viene attivato all’avvio di un capitolo. | Inizio capitolo | `a.media.chapter.view` |
| Tempo trascorso su capitolo | La quantità di tempo trascorso sul capitolo, in secondi. | Chiusura capitolo | `a.media.chapter.timePlayed` |

{style="table-layout:auto"}
