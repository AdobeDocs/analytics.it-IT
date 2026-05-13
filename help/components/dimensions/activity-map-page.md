---
title: Pagina di Activity Map
description: Il nome della pagina quando è stato fatto clic su un collegamento.
feature: Dimensions
role: User, Admin
exl-id: 8dc5d5a1-ee44-4c98-80fa-13dd1cf4edf2
TQID: https://experienceleague.adobe.com/WJ0uk-LqIABwehzzy79c2o1cd3EvI-AKUJ--vmLnKRE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 6%

---

# Pagina di Activity Map

La &#39;pagina Activity Map&#39; [dimensione](overview.md) mostra la pagina sulla quale si trovava un visitatore quando ha fatto clic su un collegamento. Puoi utilizzare questa dimensione per determinare quali pagine contengono i collegamenti più cliccati. Questa dimensione viene utilizzata anche dalla sovrapposizione Activity Map per determinare quali collegamenti visualizzare.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla [variabile di dati di contesto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.page`. Se l&#39;implementazione utilizza [Activity Map](/help/analyze/activity-map/overview.md), questa variabile di dati di contesto raccoglie automaticamente i dati quando si fa clic sui collegamenti.

Per un determinato collegamento su cui è stato fatto clic, questa variabile di dati di contesto raccoglie il valore nella dimensione [Pagina](page.md). Se la dimensione Pagina non contiene un valore, viene utilizzata la dimensione [URL pagina](page-url.md) (in modo simile al fallback utilizzato dalla dimensione Pagina). I dati di Activity Map vengono in genere inviati all’hit successivo dopo aver fatto clic su un collegamento. Questa dimensione ti consente di determinare il valore della pagina al momento del clic sul collegamento, invece del valore della pagina al momento dell’invio dei dati.

## Elementi dimensionali

Gli elementi Dimension includono tutti i valori trovati nella dimensione [Pagina](page.md).
