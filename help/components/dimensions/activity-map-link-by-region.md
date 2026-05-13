---
title: Collegamento ad Activity Map per area geografica
description: Valore concatenato di collegamento e area geografica.
feature: Dimensions
role: User, Admin
exl-id: 33014dc1-da4e-47b7-b73c-3e89e04f3ed6
TQID: https://experienceleague.adobe.com/xvYVA064hA0rsBdnLpxXllq3PD0zYAikFRjc6xNErvg
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
source-wordcount: 151
ht-degree: 11%

---

# Collegamento ad Activity Map per area geografica

La dimensione [dimensione](overview.md) di &#39;Collegamento Activity Map per area&#39; visualizza una concatenazione di [Collegamento Activity Map](activity-map-link.md) e [Area Activity Map](activity-map-link-by-region.md). Questa dimensione è utile quando disponi di collegamenti denominati in modo simile, ma che risiedono in aree diverse del sito. Ad esempio, se disponi di più collegamenti alla pagina principale tutti etichettati come &quot;Home page&quot;, puoi utilizzare questa dimensione per distinguere tali collegamenti in ogni area del sito.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalle [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.link` e `c.a.activitymap.region`. Questi due valori sono concatenati e separati da una barra verticale (`|`). Se l&#39;implementazione utilizza [Activity Map](/help/analyze/activity-map/overview.md), queste variabili di dati di contesto raccolgono automaticamente i dati quando si fa clic sui collegamenti.

## Elementi dimensionali

Gli elementi Dimension includono valori di [Activity Map Link](activity-map-link.md) e [Area geografica Activity Map](activity-map-link-by-region.md). La struttura e l’implementazione del sito della tua organizzazione determinano i valori esatti raccolti.
