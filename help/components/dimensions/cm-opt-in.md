---
title: Gestione del consenso Opt-in
description: Scopri le impostazioni di privacy a cui ha acconsentito un visitatore.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 7%

---

# Gestione del consenso Opt-in

La &#39;Consent Management Opt-In&#39; [dimension](overview.md) visualizza le impostazioni di privacy a cui un visitatore ha acconsentito. Puoi utilizzare questa dimensione per filtrare i dati in base alle impostazioni della privacy o visualizzare i motivi più comuni di consenso alla privacy.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie dati dalle seguenti [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` se impostato su `Y`. Se `opt.dmp` è uguale a `N`, viene popolata la dimensione [Rinuncia gestione consenso](cm-opt-out.md).
* `contextData.['opt.sell']` se impostato su `Y`. Se `opt.sell` è uguale a `N`, viene popolata la dimensione [Rinuncia gestione consenso](cm-opt-out.md).

La tua organizzazione determina la logica per implementare queste variabili di dati di contesto. Non persistono oltre l’hit su cui sono impostati, pertanto devi impostare ogni variabile di dati di contesto su ogni pagina.

## Elementi dimensionali

Gli elementi Dimension includono i due valori seguenti:

* **`DMP`**: il visitatore ha acconsentito alla condivisione sulle piattaforme di gestione dati. Questo elemento dimensione è presente quando la variabile di dati di contesto `opt.dmp` è uguale a `Y`.
* **`SELL`**: il visitatore ha acconsentito alla condivisione o alla vendita dei dati a terzi. Questa dimensione è presente quando la variabile di dati di contesto `opt.sell` è uguale a `Y`.
