---
description: Spiega come confrontare segmenti in Analysis Workspace.
keywords: Analysis Workspace; IQ segmento
seo-description: Spiega come confrontare segmenti in Analysis Workspace.
seo-title: Confronto segmenti
solution: Analytics
title: Confronto segmenti
topic: Reports & Analytics
uuid: c 037 fd 1 b -1513-42 cf -8550-a 15 d 420 e 595 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Confronto segmenti

Spiega come confrontare segmenti in Analysis Workspace.

>[!NOTE]
>
>You can also compare segments within a [fallout analysis](../../../../analyze/analysis-workspace/visualizations/fallout/compare-segments-fallout.md#section_E0B761A69B1545908B52E05379277B56).

## Compare segments {#section_8F2BFC45131C49B4A2E08A063CD7A91F}

1. Navigate to **[!UICONTROL Analytics]** &gt; **[!UICONTROL Workspace]** and open a project.

1. Dalla barra **[!UICONTROL Panels]** (Pannelli) a sinistra, seleziona **[!UICONTROL Segment Comparison](Confronto segmenti) e trascina la selezione in un progetto nuovo o esistente.**

   ![](assets/seg-compare-panel.png)

1. Assicurati che l’intervallo di dati relativi al confronto sia impostato correttamente.
1. Seleziona i segmenti da confrontare e trascinali nel pannello. Ad esempio, supponiamo tu abbia il segmento “Acquirenti più importanti”.

   ![](assets/compare-audiences.png)

   Dopo aver trascinato il segmento nel pannello, Analytics crea automaticamente un segmento **[!UICONTROL Everyone Else] (Tutti), che include tutti quelli NON inclusi nel segmento scelto. In questo caso, tutti i "Acquirenti meno importanti".** In questo modo, non dovrai creare questo segmento. Tutti viene aggiunto automaticamente al pannello nel campo **[!UICONTROL Compare Against](Confronta con).** Hai la possibilità di eliminarlo e di confrontare l’acquirente più importante con un altro segmento a tua scelta.

   ![](assets/everyone-else.png)

1. Fai clic su **[!UICONTROL Show Advanced Options](Mostra opzioni avanzate) per escludere componenti (dimensioni, metriche o segmenti) dall'analisi del confronto dei segmenti.** Per ulteriori informazioni, vedi [Escludere componenti dal confronto](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/compare-segments.md#section_5E98FFA0744140C08D83700E3F025937).

1. After you've selected the right "Compare Against" segment, click **[!UICONTROL Build]**.

   Questa operazione avvia un processo di back-end, che attraversa tutte le dimensioni, le metriche e altri segmenti, ricercando differenze statistiche tra i segmenti. Nella parte superiore dello strumento, viene visualizzata una barra di avanzamento, che indica il tempo rimanente dopo aver analizzato tutte le metriche e le dimensioni al fine di rilevare differenze importanti. Inoltre, assegniamo priorità di esecuzione a metriche, dimensioni e segmenti da te più utilizzati, in modo da offrirti i risultati più rilevanti il prima possibile.

   Al termine dell’analisi del processo di back-end, potrai vedere diverse informazioni grafiche:

   ![](assets/new-viz.png)

   ![](assets/new-viz2.png)

1. Interpreta i risultati del confronto dei segmenti, analizzando [nuove visualizzazioni, tabelle e riepiloghi](../../../../analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md#concept_74FAC1C6D0204F9190A110B0D9005793).

## Exclude components from comparison {#section_5E98FFA0744140C08D83700E3F025937}

A volte può essere utile escludere alcune dimensioni, metriche o segmenti dal confronto di segmenti. Ad esempio, se desideri confrontare gli utenti mobile negli USA con quelli in Germania, non occorre includere dimensioni specifiche per diverse aree geografiche, in quanto ci saranno ovvie differenze per questi due segmenti. È quindi possibile escluderle effettuando le seguenti operazioni:

1. After you have dragged the segments you want to compare into the panel, click **[!UICONTROL Show Advanced Options]** to exclude components (dimensions, metrics, or segments) from your segment comparison analysis.

   ![](assets/show-advanced-settings.png)

1. Trascina i componenti da escludere nel campo **[!UICONTROL Excluded Components](Componenti esclusi).** Puoi considerarli come una “blacklist” di componenti da escludere. Puoi impostare questi componenti come predefiniti oppure puoi fare clic su **[!UICONTROL Clear All](Cancella tutto) e iniziare di nuovo.**

   ![](assets/excluded-components.png)

1. Click **[!UICONTROL Set as default]** to exclude these components from **all** segment comparisons.

1. Per modificare l’elenco dei componenti esclusi, fai doppio clic, ad esempio, su Dimensioni per visualizzare l’elenco delle dimensioni escluse:

   ![](assets/excluded-dimensions.png)

1. Just delete any unwanted dimensions by clicking the x next to them, then save the list by clicking **[!UICONTROL Set as Default]**.

