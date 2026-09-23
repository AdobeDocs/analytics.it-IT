---
title: ID acquisto
description: L’identificatore univoco di un acquisto, disponibile in Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 12%
---
# ID acquisto

L&#39;ID acquisto [dimension](overview.md) fornisce l&#39;identificatore univoco per un acquisto.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo in Data Warehouse.

## Popolare questa dimensione con i dati

Questa dimensione viene impostata utilizzando la variabile [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Corrisponde alla colonna `purchaseid` nei feed dati. Per ulteriori informazioni, vedere [Riferimento colonna dati](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) |
| **Campo Web SDK / XDM** | [`commerce.order.purchaseID`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **Parametro query** | [`purchaseID`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<purchaseId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 20 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli oggetti Dimension includono gli ID acquisto raccolti sul tuo sito.
