---
title: Gestione del consenso Opt-in
description: Scopri le impostazioni di privacy a cui ha acconsentito un visitatore.
exl-id: b2768180-b763-41fb-8cba-665fac047e29
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 4%

---

# Gestione del consenso Opt-in

Il &quot;Consenso alla gestione del consenso&quot; [dimensione](overview.md) mostra le impostazioni di privacy a cui un visitatore ha acconsentito. Puoi utilizzare questa dimensione per filtrare i dati in base alle impostazioni della privacy o visualizzare i motivi più comuni di consenso alla privacy.

## Popola questa dimensione con i dati

Questa dimensione raccoglie dati dai seguenti elementi [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` se impostato su `Y`. Se `opt.dmp` è uguale a `N`, il [Rinuncia alla gestione del consenso](cm-opt-out.md) La dimensione viene invece compilata.
* `contextData.['opt.sell']` se impostato su `Y`. Se `opt.sell` è uguale a `N`, il [Rinuncia alla gestione del consenso](cm-opt-out.md) La dimensione viene invece compilata.

La tua organizzazione determina la logica per implementare queste variabili di dati di contesto. Non persistono oltre l’hit su cui sono impostati, pertanto devi impostare ogni variabile di dati di contesto su ogni pagina.

## Elementi dimensionali

Gli elementi Dimension includono i due valori seguenti:

* **`DMP`**: il visitatore ha acconsentito alla condivisione sulle piattaforme di gestione dei dati. Questo elemento dimensione è presente quando la variabile di dati di contesto `opt.dmp` è uguale a `Y`.
* **`SELL`**: il visitatore ha acconsentito alla condivisione o alla vendita dei dati a terzi. Questa dimensione è presente quando la variabile di dati di contesto `opt.sell` è uguale a `Y`.
