---
title: Prodotto
description: Il nome del prodotto.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
TQID: https://experienceleague.adobe.com/SMFFeSTkQyQoSWNFc8qHJRxYkJQmiJoKd0v4rS6xRKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 6%
---
# Prodotto

La [dimensione](overview.md) &quot;Prodotto&quot; riporta il nome del prodotto nell&#39;hit. È utile per le implementazioni che utilizzano la variabile `products` e desiderano visualizzare metriche relative ai prodotti, ad esempio articoli più venduti o più visualizzati. Questa dimensione può essere intenzionalmente vuota se non hai prodotti sul sito.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento al nome del prodotto nella variabile [`products`](/help/implement/vars/page-vars/products.md), che è la stringa tra il primo e il secondo punto e virgola (`;`).

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`products`](/help/implement/vars/page-vars/products.md) |
| **Campo Web SDK / XDM** | [`productListItems[].name`](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **Parametro query** | [`products`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<products>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 100 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di stabilire una convenzione di denominazione coerente per i prodotti. [Le classificazioni](../classifications/classifications-overview.md) sono disponibili se desideri raggruppare i prodotti in modo diverso o fornire un nome più descrittivo. Adobe consiglia di utilizzare entrambe le dimensioni &quot;Prodotto&quot; e &quot;Categoria&quot;.
