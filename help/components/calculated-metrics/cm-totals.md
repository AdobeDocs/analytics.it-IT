---
title: Totali delle metriche calcolate
description: Scopri i totali delle metriche calcolate in Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: 325a42c080290509309e90c9127138800d5ac496
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 4%

---

# Totali delle metriche calcolate

Nella maggior parte dei casi, quando visualizzi i dati in Analysis Workspace, vengono visualizzati i totali delle metriche calcolate. In alcuni casi non è possibile fornire un totale, ad esempio quando le righe del rapporto sono in formato misto (ad esempio decimale e valuta).

Quando vengono visualizzati i totali, questi vengono spesso calcolati lato server, il che significa che il totale deduplica metriche quali visite o visitatori. In alcune circostanze, le metriche calcolate vengono generate lato client sommando tra le righe della tabella, il che significa che il totale non deduplica metriche quali visite o visitatori. Ciò si verifica:

* Quando si utilizzano [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) nelle tabelle a forma libera e si seleziona l&#39;opzione **[!UICONTROL Show as sum of current rows]** (predefinita).
* Nella visualizzazione [Anello](/help/analyze/analysis-workspace/visualizations/donut.md), la somma dei numeri è pari al 100%.

Per ulteriori informazioni sui totali in Analysis Workspace, visita [Totali Workspace](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total).
