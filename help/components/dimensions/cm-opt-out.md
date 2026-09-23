---
title: Gestione del consenso Opt-Out
description: Scopri quali impostazioni di privacy hanno rinunciato un visitatore.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
TQID: https://experienceleague.adobe.com/tsMhHR84qhEUZIZjPTluCJOHMPc37-JRwLsipAycgJI
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
source-wordcount: '278'
ht-degree: 8%
---
# Gestione del consenso Opt-Out

La &#39;Rinuncia alla gestione del consenso&#39; [dimensione](overview.md) mostra quali impostazioni di privacy hanno esplicitamente escluso un visitatore. Puoi utilizzare questa dimensione per filtrare i dati in base alle impostazioni della privacy o visualizzare i motivi di rinuncia alla privacy più comuni.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalle seguenti [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` se impostato su `1`. Se `cm.ssf` è uguale a `0` o è vuoto, questa variabile non esegue alcuna operazione.
* `contextData.['opt.dmp']` se impostato su `N`. Se `opt.dmp` è uguale a `Y`, viene popolata la dimensione [Consent Management Opt-In](cm-opt-in.md).
* `contextData.['opt.sell']` se impostato su `N`. Se `opt.sell` è uguale a `Y`, viene popolata la dimensione [Consent Management Opt-In](cm-opt-in.md).

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

Gli elementi di Dimension includono i tre valori seguenti:

* **`SSF`**: il visitatore ha rinunciato a [Inoltro lato server](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md). Questo elemento dimensione è presente quando la variabile di dati di contesto `cm.ssf` è uguale a `1`. Per ulteriori informazioni, consulta la [Panoramica sulla privacy dei dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=it) nella guida utente di Audience Manager. L’hit non viene inoltrato a Adobe Audience Manager.
* **`DMP`**: il visitatore ha rinunciato alla condivisione sulle piattaforme di gestione dati. Questo elemento dimensione è presente quando la variabile di dati di contesto `opt.dmp` è uguale a `N`. Simile a `SSF`, l&#39;hit non viene inoltrato a Adobe Audience Manager.
* **`SELL`**: il visitatore ha rinunciato alla condivisione o alla vendita dei dati a terzi. Questa dimensione è presente quando la variabile di dati di contesto `opt.sell` è uguale a `N`.
