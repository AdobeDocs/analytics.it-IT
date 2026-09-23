---
title: Visite a pagina singola (dimensioni)
description: Un flag che indica che la visita era costituita da una singola pagina.
feature: Dimensions
exl-id: f7b58941-add4-4e7b-8645-a64280fd9dcb
TQID: https://experienceleague.adobe.com/mMxxlVpQi7IsSuxSZGijnvWeoqCa-ybf8otPRDf6AyQ
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
source-wordcount: '187'
ht-degree: 11%
---
# Visite a pagina singola

>[!BEGINSHADEBOX]

*Questa pagina della Guida descrive il funzionamento di &#39;Visite a pagina singola&#39; come [dimensione](overview.md). Per ulteriori informazioni, consulta la metrica [Visite a pagina singola](../metrics/single-page-visits.md).*

>[!ENDSHADEBOX]

La dimensione &quot;Visite a pagina singola&quot; riporta il numero di visite costituito da un singolo elemento dimensione univoco [Pagina](page.md). È la dimensione della metrica [Visite a pagina singola](../metrics/single-page-visits.md).

Questa dimensione viene comunemente utilizzata come componente all&#39;interno di [segmentazione](../segmentation/seg-home.md). In genere non viene utilizzata come dimensione nei rapporti.

## Popolare questa dimensione con i dati

Adobe calcola questa dimensione lato server valutando se ogni visita conteneva una singola pagina univoca. Non esiste una variabile da impostare; funziona automaticamente per tutte le implementazioni.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (calcolato da Adobe) |
| **Campo Web SDK / XDM** | Nessuno (calcolato da Adobe) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

L&#39;unico elemento dimensione è `"Enabled"`. Se una visita è costituita da una singola pagina, l’hit viene impostato su questo valore. Tutti gli altri hit vengono omessi da questo rapporto.
