---
title: Visualizza annotazioni
description: Come visualizzare le annotazioni in Analysis Workspace.
role: User, Admin
feature: Annotations
exl-id: 52b179fd-d9a4-4119-a3c6-f6a36f24f8ea
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 84%

---

# Visualizzare le annotazioni

Le annotazioni si presentano in modo leggermente diverso, a seconda di dove vengono visualizzate e se si estendono su un singolo giorno o su un intervallo di date.

## Visualizzare le annotazioni in Workspace

| Tipo di<br/>visualizzazione | Descrizione |
| --- | --- |
| **Linee &#x200B;**<br/>**Giorno singolo** | Quando selezioni ![Annota](/help/assets/icons/Annotate.svg) in una visualizzazione a linee, si apre un riquadro a comparsa con i dettagli dell’annotazione.<br/>![Annotazione per un giorno singolo](assets/annotation-single-day.png)<br/>Per modificare l’annotazione nel [generatore di annotazioni](create-annotations.md#annotation-builder), seleziona ![Modifica](/help/assets/icons/Edit.svg). Per eliminare l’annotazione, seleziona ![Elimina](/help/assets/icons/Delete.svg). |
| **Linee &#x200B;**<br/>**Intervallo date** | Quando selezioni ![AnnotateRange](/help/assets/icons/AnnotateRange.svg) si apre un riquadro a comparsa con i dettagli dell’annotazione e una linea in basso che indica l’intervallo di date.<br/>![Intervallo annotazione](assets/annotation-range.png)Per modificare l’annotazione nel [generatore di annotazioni](create-annotations.md#annotation-builder), seleziona ![Modifica](/help/assets/icons/Edit.svg). Per eliminare l’annotazione, seleziona ![Elimina](/help/assets/icons/Delete.svg). |
| **Tabella a forma libera** | In una tabella a forma libera, puoi accedere a tutte le annotazioni dal pulsante delle annotazioni in alto a destra della visualizzazione. Seleziona ![Annota](/help/assets/icons/Annotate.svg) per visualizzare un (elenco a scorrimento) di tutte le annotazioni.<br/>![Tabella annotazioni](assets/annotations-table.png)<br/>Per ogni annotazione, puoi selezionare ![Modifica](/help/assets/icons/Edit.svg) per modificare l’annotazione nel [generatore di annotazioni](create-annotations.md#annotation-builder) ed ![Elimina](/help/assets/icons/Delete.svg) per eliminarla. |

{style="table-layout:auto"}

## Visualizzare le annotazioni in un PDF

Quando scarichi il progetto come PDF o lo invii come PDF, le annotazioni vengono riepilogate nel PDF nella sezione Riepilogo annotazioni.

![Visualizzazione evidenziata di un file .pdf con spiegazioni delle annotazioni.](assets/annotations-pdf.png)


<!--
# View annotations

Annotations manifest slightly differently, depending on whether they span a single day or a date range.

## View annotations in Line charts or Tables

| Date | Appearance |
| --- | --- |
| **Single day** |   ![](assets/single-day.png)<p>When you hover over the annotation, you can see its details, you can edit it by selecting the pen icon, or you can delete it:<p> ![](assets/hover.png) |
| **Date range** |  The icon changes and when you hover over it, the date range appears.<p>![](assets/multi-day.png)<p>When you select it in the line chart, the annotation metadata appear, and you can edit or delete it:![](assets/multi-hover.png)<p>In a table, an icon appears on every date in the date range.<p>![](assets/multi-day-table.png)|
| **Overlapping annotations** | On days that have more than one annotation tied to them, the icon appears in a grey color.<p>![](assets/grey.png)<p>When you hover over the grey icon, all overlapping annotations appear:<p>![](assets/overlap.png) |

{style="table-layout:auto"}

## View annotations in a .pdf file

Since you cannot hover over icons in a .pdf file, this file (after export) provides notes of explanations at the bottom of a panel. Here is an example:

![](assets/ann-pdf.png)

## View annotations with non-trended data

Sometimes annotation are shown with non-trended data, but tied to a specific dimension. In that case, they appear only in a summary annotation in the bottom right corner. Here is an example:

![](assets/non-date.png)

The summary chart appears in all visualization types in the corner, not just in non-trended freeform tables and summary numbers. It also appears in visualizations like [!UICONTROL Donut], [!UICONTROL Flow],[!UICONTROL Fallout],[!UICONTROL Cohort], and so on.

![](assets/ann-summary.png)

-->