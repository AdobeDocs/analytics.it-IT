---
title: Trimestre dell’anno
description: Trimestre numerico dell'anno, indipendentemente dall'anno.
feature: Dimensions
exl-id: 0de5f916-9cc1-4594-9dfc-68ef831dcc0a
TQID: https://experienceleague.adobe.com/a41aEgQ2NkPzWzcn59JfOd8LgL3vmhr1y11lsIwHpjI
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
source-wordcount: '172'
ht-degree: 13%
---
# Trimestre dell’anno

La [dimensione](overview.md) del &#39;Trimestre dell&#39;anno&#39; riporta il trimestre di un dato anno come elemento dimensione. Questo rapporto è utile se desideri un rapporto suddiviso per il trimestre dell’anno, ma non vuoi una data statica come elementi dimensionali. È possibile aggregare i rapporti su base annua per trimestre, in modo che i dati del primo trimestre di quest’anno vengano aggregati con i dati del primo trimestre dell’anno precedente nello stesso elemento dimensionale.

## Popolare questa dimensione con i dati

Questa dimensione è derivata dalla marca temporale di ciascun hit. Non esiste una variabile da impostare; funziona come previsto in qualsiasi implementazione.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal timestamp dell’hit) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal timestamp dell’hit) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi di Dimension includono i trimestri numerici dell&#39;anno (`1` a `4`), che rappresentano il trimestre dell&#39;anno in cui si è verificato l&#39;hit.
