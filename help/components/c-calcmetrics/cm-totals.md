---
title: Totali delle metriche calcolate
description: Scopri i totali delle metriche calcolate in Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 2%

---

# Totali delle metriche calcolate [!DNL Analysis Workspace]

Nella maggior parte dei casi, quando visualizzi i dati in Analysis Workspace, vengono visualizzati i totali delle metriche calcolate. In alcuni casi non è possibile fornire un totale, ad esempio quando le righe del rapporto sono in formato misto (ad esempio decimale e valuta).

Quando vengono visualizzati i totali, questi vengono spesso calcolati lato server, il che significa che il totale deduplica metriche quali visite o visitatori. In alcune circostanze, le metriche calcolate vengono generate lato client sommando tra le righe della tabella, il che significa che il totale non deduplica metriche quali visite o visitatori. Ciò si verifica:

* Quando [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) sono utilizzati nelle tabelle a forma libera e **[!UICONTROL Show as sum of current rows]** (impostazione predefinita) è selezionata.
* In [Visualizzazione ad anello](/help/analyze/analysis-workspace/visualizations/donut.md), in modo che i numeri arrivino al 100%.

Per ulteriori informazioni sui totali in Analysis Workspace, visita [Totali in Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html#static-row-total).
