---
title: Dimensioni del capitolo di Streaming Media
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti.
feature: Dimensions
exl-id: cac66a0b-3f83-46a9-b35c-ba08e0eafb92
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 11%

---

# Dimensioni del capitolo dei servizi multimediali in streaming

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere il capitolo [Metriche dei servizi multimediali in streaming](../metrics/sm-chapters.md).*

Le dimensioni del capitolo dei servizi di contenuti multimediali in streaming forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie dei servizi di contenuti multimediali in streaming. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Analytics for Streaming Media Ad-on]**. Per informazioni, contatta il team del tuo account di Adobe.

Quando abiliti **[!UICONTROL Media Chapters]** in [Generazione rapporti multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), è disponibile la seguente dimensione:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Capitolo | ID del capitolo generato automaticamente. | Chiusura capitolo | `a.media.chapter.name` |

{style="table-layout:auto"}

Oltre alle dimensioni di cui sopra, Adobe crea automaticamente le seguenti dimensioni di classificazione. Per visualizzare i rapporti che utilizzano queste dimensioni, devi caricare i dati di classificazione.

| Nome classificazione | Dimensione principale | Descrizione |
| --- | --- | --- |
| Creatore | [Contenuto](sm-core.md) | Il creatore del contenuto. |
| Durata capitolo | Capitolo | Durata del capitolo in secondi. |
| Nome del capitolo | Capitolo | Il nome descrittivo del capitolo. |
| Offset capitolo | Capitolo | Offset del capitolo all’interno del contenuto dall’inizio, in secondi. |
| Posizione del capitolo | Capitolo | Posizione di indice del capitolo nel contenuto. |

{style="table-layout:auto"}
