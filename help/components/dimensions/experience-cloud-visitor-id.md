---
title: ID visitatore di Experience Cloud
description: L’Experience Cloud ID (ECID) del visitatore, disponibile in Data Warehouse.
feature: Dimensions
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
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
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 13%
---
# ID visitatore di Experience Cloud

La &#39;Experience Cloud Visitor ID&#39; [dimensione](overview.md) fornisce l&#39;ECID per ogni visitatore. È un numero a 128 bit composto da due numeri concatenati a 64 bit aggiunti a 19 cifre.

>[!IMPORTANT]
>
>Questa dimensione è disponibile solo in Data Warehouse.

## Popolare questa dimensione con i dati

Questa dimensione richiede un’implementazione che utilizza il servizio ID visitatore (VisitorAPI) o il servizio Experience Platform Identity. Corrisponde alla colonna `mcvisid` nei feed dati. Per ulteriori informazioni, vedere [Riferimento colonna dati](../../export/analytics-data-feed/c-df-contents/datafeeds-reference.md).

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (impostato dal servizio ID visitatore di Adobe) |
| **Campo Web SDK / XDM** | Nessuno (impostato dal servizio Experience Platform Identity) |
| **Parametro query** | [`mid`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<marketingCloudVisitorId>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi Dimension includono l’ECID di ciascun visitatore.
