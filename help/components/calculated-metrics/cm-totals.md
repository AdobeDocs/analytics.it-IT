---
title: Totali delle metriche calcolate
description: Scopri i totali delle metriche calcolate in Analysis Workspace
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
TQID: https://experienceleague.adobe.com/3UJF1Hl3nLqjYAiQuvcE4Jpq26MaTgeba5BmnVfvEps
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e318d41c-1d01-4c1e-9b18-1f61d435ceee
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 143
ht-degree: 4%

---

# Totali delle metriche calcolate

Nella maggior parte dei casi, quando visualizzi i dati in Analysis Workspace, vengono visualizzati i totali delle metriche calcolate. In alcuni casi non è possibile fornire un totale, ad esempio quando le righe del rapporto sono in formato misto (ad esempio decimale e valuta).

Quando vengono visualizzati i totali, questi vengono spesso calcolati lato server, il che significa che il totale deduplica metriche quali visite o visitatori. In alcune circostanze, le metriche calcolate vengono generate lato client sommando tra le righe della tabella, il che significa che il totale non deduplica metriche quali visite o visitatori. Ciò si verifica:

* Quando si utilizzano [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) nelle tabelle a forma libera e si seleziona l&#39;opzione **[!UICONTROL Show as sum of current rows]** (predefinita).
* Nella visualizzazione [Anello](/help/analyze/analysis-workspace/visualizations/donut.md), la somma dei numeri è pari al 100%.

Per ulteriori informazioni sui totali in Analysis Workspace, visita [Totali Workspace](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md#static-row-total).
