---
title: Dimensioni del capitolo di Streaming Media
description: Dimensioni disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti.
feature: Dimensions
source-git-commit: 26c131a37fa1f30c83fd99b290523a97d3c954db
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 11%

---

# Dimensioni del capitolo di Streaming Media

*In questa pagina sono descritte le dimensioni disponibili quando si abilita [!UICONTROL Media Chapters] per una suite di rapporti. Per informazioni sulle metriche disponibili, vedere [Metriche del capitolo di Streaming Media](../metrics/sm-chapters.md).*

Le dimensioni del capitolo Streaming Media forniscono funzionalità di reporting supplementari per la raccolta dei dati tramite le librerie di raccolta di contenuti multimediali in streaming. L&#39;utilizzo di queste dimensioni richiede **[!UICONTROL Adobe Streaming Media Collection Add-on]**. Per informazioni, contatta il team dell’account Adobe.

Quando abiliti **[!UICONTROL Media Chapters]** in [Generazione rapporti multimediali](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/media-management.md), è disponibile la seguente dimensione:

| Nome dimensione | Descrizione | Inviato con | Variabile dati contestuali |
| --- | --- | --- | --- |
| Capitolo | ID del capitolo generato automaticamente. | Chiusura capitolo | `a.media.chapter.name` |

{style="table-layout:auto"}

Oltre alle quote di cui sopra, Adobe crea automaticamente le seguenti quote di classificazione. Per visualizzare i rapporti che utilizzano queste dimensioni, devi caricare i dati di classificazione.

| Nome classificazione | Dimensione principale | Descrizione |
| --- | --- | --- |
| Creatore | [Contenuto](sm-core.md) | Il creatore del contenuto. |
| Durata capitolo | Capitolo | Durata del capitolo in secondi. |
| Nome del capitolo | Capitolo | Il nome descrittivo del capitolo. |
| Offset capitolo | Capitolo | Offset del capitolo all’interno del contenuto dall’inizio, in secondi. |
| Posizione del capitolo | Capitolo | Posizione di indice del capitolo nel contenuto. |

{style="table-layout:auto"}
