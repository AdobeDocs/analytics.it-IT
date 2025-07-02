---
title: Panoramica del pannello Segment Comparison
description: Scopri come utilizzare il pannello di confronto dei segmenti in Analysis Workspace.
keywords: Analysis Workspace, segmento IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: 810e52260443ccc076e07b8d638563d56db9956e
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 19%

---

# Panoramica del pannello di confronto dei segmenti {#segment-comparison-overview}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_button"
>title="Confronto dei segmenti"
>abstract="Confronta rapidamente due segmenti su tutti i punti dati per trovare automaticamente differenze rilevanti."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_segmentcomparison_panel"
>title="Pannello Confronto dei segmenti"
>abstract="Confronta rapidamente due segmenti su tutti i punti dati per trovare automaticamente differenze rilevanti.<br/><br/>**Parametri &#x200B;**<br/>**Aggiungi un segmento**: il primo segmento che desideri analizzare.<br/>**Confronta con**: il secondo segmento di cui vuoi eseguire il confronto, popolato automaticamente con *Tutti gli altri* (l&#39;inverso del primo segmento). Puoi sostituire *Tutti gli altri* con un segmento diverso, se lo desideri.<br/>**Impostazioni avanzate**: la possibilità di escludere i componenti dall’analisi nel confronto tra segmenti."
<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

_Questo articolo documenta il pannello di confronto dei segmenti in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _&#x200B;**Adobe Analytics**._<br/>_Nessun pannello equivalente in_ ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _&#x200B;**Customer Journey Analytics**._

>[!ENDSHADEBOX]

Il pannello Confronto segmenti rileva le differenze più importanti dal punto di vista statistico tra un numero illimitato di segmenti. La funzione esegue un’analisi automatizzata di tutte le dimensioni e metriche a cui hai accesso. Rileva automaticamente le caratteristiche chiave dei segmenti di pubblico che guidano i KPI della tua azienda e ti consente di vedere quanto segmenti si sovrappongono.


>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Confronto segmenti](https://video.tv.adobe.com/v/23976?quality=12&learn=on){target="_blank"} per un video demo.

>[!ENDSHADEBOX]



## Utilizzo

Per usare un pannello **[!UICONTROL Attribution]**:

1. Crea un pannello **[!UICONTROL Attribution]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](../panels.md#create-a-panel).

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.



### Input del pannello

Puoi configurare il pannello [!UICONTROL Segment comparison] usando le seguenti impostazioni di input:

![Pannello input penna per confronto segmenti](assets/segment-comparison-input.png)

| Input | Descrizione |
| --- | --- |
| **[!UICONTROL Add a segment]** | Selezionate la quota rispetto alla quale desiderate eseguire il confronto. |
| **[!UICONTROL Compare against]** | Seleziona la dimensione da utilizzare per confrontare il segmento selezionato iniziale. Se non si seleziona un segmento specifico, verrà utilizzato il segmento predefinito **[!UICONTROL Everyone else]**. |
| **[!UICONTROL Show / hide advanced settings]** | Selezionare **[!UICONTROL Show advanced settings]** per configurare **[!UICONTROL Excluded components]**, selezionare **[!UICONTROL Hide advanced settings]** per nascondere **[!UICONTROL Excluded components]**. |
| **[!UICONTROL Excluded components]** | Componenti che è possibile specificare, come **[!UICONTROL Dimensions]**, **[!UICONTROL Metrics]** o **[!UICONTROL Segments]** per l&#39;esclusione.<br><ul><li>Trascinare una o più dimensioni, metriche o segmenti dai contenitori al contenitore **[!UICONTROL Excluded components]**.</li><li>Per rimuovere un componente, selezionare il tipo (**[!UICONTROL Dimension]** **[!UICONTROL Metrics]** o **[!UICONTROL Segments]**) e selezionare ![CrossSize75](/help/assets/icons/CrossSize75.svg) per rimuovere un componente. Per rimuovere tutti i componenti, selezionare **[!UICONTROL Clear all]**.</li><li>Per impostare la selezione corrente di dimensioni, metriche e segmenti come predefinita, selezionare **[!UICONTROL Set as default]**.</li></ul> |

Seleziona **[!UICONTROL Build]** per creare il pannello.

### Output del pannello

Adobe Analytics Al termine dell’analisi dei due segmenti desiderati, i pannelli di output mostrano i risultati tramite diverse visualizzazioni:

![Confronto segmenti output pannello](assets/segment-comparison-output.png)

| Visualizzazione | Descrizione |
|---|---|
| **[!UICONTROL Size and overlap]** | Illustra con una visualizzazione [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) le dimensioni comparative di ciascun segmento selezionato e il livello di sovrapposizione tra di essi. |
| **[!UICONTROL Unique visitors for 1st segment]** | Una visualizzazione [Summary number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che mostra i visitatori univoci per il primo segmento (nell&#39;esempio Visite a pagina singola) |
| **[!UICONTROL Unique visitors for 2nd segment]** | Una visualizzazione [Summary number](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) che mostra i visitatori univoci per il secondo segmento (nell&#39;esempio First Time Visits) |
| **[!UICONTROL Top metrics against Segments]** | Una [tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra le metriche principali per i segmenti selezionati. |
| **[!UICONTROL Metric over time by Segment]** | Una visualizzazione [Line](/help/analyze/analysis-workspace/visualizations/line.md) che mostra le metriche nel tempo per i segmenti selezionati. |
| **[!UICONTROL Top dimension items against Segments]** | Una [tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra gli elementi dimensionali misti per i segmenti selezionati. |
| **[!UICONTROL Dimension items by Segments]** | Una visualizzazione [Barra orizzontale](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) che mostra gli elementi dimensionali per segmento. |
| **[!UICONTROL Top segments against Segments]** | Una [tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) che mostra i segmenti principali rispetto ai segmenti. |
| **[!UICONTROL Segment overlap]** | Visualizzazione [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) che mostra la sovrapposizione dei segmenti. |

Utilizza ![Modifica](/help/assets/icons/Edit.svg) per riconfigurare e ricreare il pannello.


<!--
#### Size and overlap

Illustrates the comparative sizes of each selected segment and how much they overlap with each other using a venn diagram. You can hover over the visual to see how many visitors were in each overlapping or non-overlapping section. You can also right click on the overlap to create a brand new segment for further analysis. If the two segments are mutually exclusive, no overlap is shown between the two circles (typically seen with segments using a hit container).

![Size and overlap](assets/size-overlap.png)

#### Population summaries

To the right of the Size and Overlap visualization, the total unique visitor count in each segment and overlap is shown.

![Population summaries](assets/population_summaries.png)

#### Top metrics

Displays the most statistically significant metrics between the two segments. Each row in this table represents a differentiating metric, ranked by how different it is between each segment. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific metric is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific metric. If a metric is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Metrics added to this table after the segment comparison has finished do not receive a Difference Score.

![Top metrics](assets/top-metrics.png)

#### Metric over time by segment

To the right of the metrics table is a linked visualization. You can click a line item in the table on the left, and this visualization updates to show that metric trended over time.

![Top metrics line](assets/linked-viz.png)

#### Top dimensions

Shows the most statistically significant dimension items across all of your dimensions. Each row shows the percentage of each segment exhibiting this dimension item. For example, this table might reveal that 100% of visitors in 'Segment A' had the dimension item 'Browser Type: Google', whereas only 19.6% of 'Segment B' had this dimension item. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific dimension item is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific dimension item. If a dimension item is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Dimension items added to this table after the segment comparison has finished do not receive a Difference Score.

![Top dimensions](assets/top-dimension-item1.png)

#### Dimension items by segment

To the right of the dimensions table is a linked bar chart visualization. It shows all displayed dimension items in a bar chart. Clicking a line item in the table on the left updates the visualization on the right.

![Top dimensions bar chart](assets/top-dimension-item.png)

#### Top segments

Shows which other segments (other than the two segments selected for comparison) have statistically significant overlap. For example, this table can show that a third segment, 'Repeat Visitors', overlaps highly with 'Segment A' but does not overlap with 'Segment B'. A difference score of 1 means it is statistically significant, while a difference score of 0 means there is no statistical significance.

This visualization is similar to freeform tables in Analysis Workspace. If deeper analysis on a specific segment is desired, hover over a line item and click 'Create visual'. A new table is created to analyze that specific segment. If a segment is irrelevant to your analysis, hover over the line item and click the 'X' to remove it.

>[!NOTE]
>
>Segments added to this table after the segment comparison has finished do not receive a Difference Score.

![Top segments](assets/top-segments.png)

#### Segment overlap

To the right of the segments table is a linked venn diagram visualization. It shows the most statistically significant segment applied to your compared segments. For example, 'Segment A' + 'Statistically significant segment' vs. 'Segment B' + 'Statistically significant segment'. Clicking a segment line item in the table on the left updates the venn diagram on the right.

![Top segments venn diagram](assets/segment-overlap.png)

-->
