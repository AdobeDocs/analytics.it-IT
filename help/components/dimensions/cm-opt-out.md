---
title: Gestione del consenso Opt-Out
description: Scopri quali impostazioni di privacy hanno rinunciato un visitatore.
exl-id: 2bf4d22c-5b24-47fb-b489-49388fcca5b1
feature: Dimensions
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 3%

---

# Gestione del consenso Opt-Out

La dimensione &quot;Rinuncia alla gestione del consenso&quot; mostra quali impostazioni di privacy hanno esplicitamente escluso un visitatore. Puoi utilizzare questa dimensione per filtrare i dati in base alle impostazioni della privacy o visualizzare i motivi di rinuncia alla privacy più comuni.

## Popola questa dimensione con i dati

Questa dimensione raccoglie dati dai seguenti elementi [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` se impostato su `1`. Se `cm.ssf` è uguale a `0` o è vuoto, questa variabile non esegue alcuna operazione.
* `contextData.['opt.dmp']` se impostato su `N`. Se `opt.dmp` è uguale a `Y`, il [Gestione del consenso Opt-in](cm-opt-in.md) La dimensione viene invece compilata.
* `contextData.['opt.sell']` se impostato su `N`. Se `opt.sell` è uguale a `Y`, il [Gestione del consenso Opt-in](cm-opt-in.md) La dimensione viene invece compilata.

La tua organizzazione determina la logica per implementare queste variabili di dati di contesto. Non persistono oltre l’hit su cui sono impostati, pertanto devi impostare ogni variabile di dati di contesto su ogni pagina.

## Elementi dimensionali

Gli elementi Dimension includono i tre valori seguenti:

* **`SSF`**: il visitatore ha rinunciato a [Inoltro lato server](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-server-side-forwarding/ssf.md). Questo elemento dimensione è presente quando la variabile di dati di contesto `cm.ssf` è uguale a `1`. Consulta [Panoramica sulla privacy dei dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) per ulteriori informazioni, consulta la guida utente di Audience Manager. L’hit non viene inoltrato a Adobe Audience Manager.
* **`DMP`**: il visitatore ha rinunciato alla condivisione sulle piattaforme di gestione dei dati. Questo elemento dimensione è presente quando la variabile di dati di contesto `opt.dmp` è uguale a `N`. Simile a `SSF`, l’hit non viene inoltrato a Adobe Audience Manager.
* **`SELL`**: il visitatore ha rinunciato alla condivisione o alla vendita dei dati a terzi. Questa dimensione è presente quando la variabile di dati di contesto `opt.sell` è uguale a `N`.
