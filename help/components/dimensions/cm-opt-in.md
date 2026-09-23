---
title: Gestione del consenso Opt-in
description: Scopri le impostazioni di privacy a cui ha acconsentito un visitatore.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
TQID: https://experienceleague.adobe.com/hvtKcglMPFz4FbInpuSs9haS5SwGNQpVWXn12M1x658
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
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 11%
---
# Gestione del consenso Opt-in

La &#39;Consent Management Opt-In&#39; [dimension](overview.md) visualizza le impostazioni di privacy a cui un visitatore ha acconsentito. Puoi utilizzare questa dimensione per filtrare i dati in base alle impostazioni della privacy o visualizzare i motivi più comuni di consenso alla privacy.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalle seguenti [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` se impostato su `Y`. Se `opt.dmp` è uguale a `N`, viene popolata la dimensione [Rinuncia gestione consenso](cm-opt-out.md).
* `contextData.['opt.sell']` se impostato su `Y`. Se `opt.sell` è uguale a `N`, viene popolata la dimensione [Rinuncia gestione consenso](cm-opt-out.md).

La tua organizzazione determina la logica per implementare queste variabili di dati di contesto. Imposta ogni variabile di dati di contesto su ogni pagina.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (impostato tramite segnali di consenso) |
| **Campo Web SDK / XDM** | Nessuno |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | 100 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi di Dimension includono i due valori seguenti:

* **`DMP`**: il visitatore ha acconsentito alla condivisione sulle piattaforme di gestione dati. Questo elemento dimensione è presente quando la variabile di dati di contesto `opt.dmp` è uguale a `Y`.
* **`SELL`**: il visitatore ha acconsentito alla condivisione o alla vendita dei dati a terzi. Questa dimensione è presente quando la variabile di dati di contesto `opt.sell` è uguale a `Y`.
