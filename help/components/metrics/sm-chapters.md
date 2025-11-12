---
title: Metriche dei capitoli dei servizi multimediali in streaming
description: Metriche disponibili quando abiliti [!UICONTROL Media Chapters] per una suite di rapporti.
feature: Metrics
exl-id: bef379d5-9dc9-404f-8197-1ba66d11299d
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 6%

---

# Metriche dei capitoli dei servizi multimediali in streaming

*In questa pagina sono descritte le metriche disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti. Vedere [Dimensioni del capitolo dei servizi multimediali in streaming](../dimensions/sm-chapters.md) per le dimensioni disponibili.*

Le metriche dei capitoli dei servizi multimediali di streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di raccolta dei servizi multimediali di streaming. L&#39;utilizzo di queste metriche richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Chapters]** in [Report multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), sono disponibili le metriche seguenti:

| Nome della metrica | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Chapter completes]** | Valore booleano che viene attivato al completamento di un capitolo. | Chiusura capitolo | `a.media.chapter.complete` | `xdm.mediaReporting.`<br>`chapterDetails.isCompleted` |
| **[!UICONTROL Chapter starts]** | Valore booleano che viene attivato all’avvio di un capitolo. | Inizio capitolo | `a.media.chapter.view` | `xdm.mediaReporting.`<br>`chapterDetails.isStarted` |
| **[!UICONTROL Chapter time spent]** | La quantità di tempo trascorso sul capitolo, in secondi. | Chiusura capitolo | `a.media.chapter.timePlayed` | `xdm.mediaReporting.`<br>`chapterDetails.timePlayed` |
