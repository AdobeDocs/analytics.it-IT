---
title: Dimensioni del capitolo di Streaming Media
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: 936644c719f46a1327c8a5aa247ed69a14d3da1e
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 5%

---

# Dimensioni del capitolo dei servizi multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere il capitolo [Metriche dei servizi multimediali in streaming](../metrics/sm-chapters.md).*

Le dimensioni del capitolo dei servizi di contenuti multimediali in streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie dei servizi di contenuti multimediali in streaming. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Add-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Chapters]** in [Generazione rapporti multimediali](/help/admin/tools/manage-rs/edit-settings/media-management.md), è disponibile la seguente dimensione:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali | Campo XDM |
| --- | --- | --- | --- | --- |
| **[!UICONTROL Chapter]** | ID del capitolo generato automaticamente. | Chiusura capitolo | `a.media.chapter.name` | `xdm.mediaReporting.`<br>`chapterDetails.ID` |

Oltre alle dimensioni di cui sopra, Adobe crea automaticamente le seguenti dimensioni di classificazione. Per visualizzare i rapporti che utilizzano queste dimensioni, devi caricare i dati di classificazione.

| Nome classificazione | Dimensione principale | Descrizione |
| --- | --- | --- |
| **[!UICONTROL Originator]** | [[!UICONTROL Content]](sm-core.md) | Il creatore del contenuto. |
| **[!UICONTROL Chapter length]** | [!UICONTROL Chapter] | Durata del capitolo in secondi. |
| **[!UICONTROL Chapter name]** | [!UICONTROL Chapter] | Il nome descrittivo del capitolo. |
| **[!UICONTROL Chapter offset]** | [!UICONTROL Chapter] | Offset del capitolo all’interno del contenuto dall’inizio, in secondi. |
| **[!UICONTROL Chapter position]** | [!UICONTROL Chapter] | Posizione di indice del capitolo nel contenuto. |
