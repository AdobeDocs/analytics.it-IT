---
title: Gestione del consenso Opt-in
description: Vedi le impostazioni di privacy a cui un visitatore ha acconsentito.
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 3%

---

# Gestione del consenso Opt-in

La dimensione &quot;Consent Management Opt-in&quot; visualizza le impostazioni di privacy a cui un visitatore ha acconsentito. Puoi utilizzare questa dimensione per filtrare i dati in base alle impostazioni di privacy o per visualizzare i motivi più comuni di consenso alla privacy.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i dati seguenti [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['opt.dmp']` quando è impostato su `Y`. Se `opt.dmp` è `N`, [Gestione del consenso Opt-Out](cm-opt-out.md) viene compilata.
* `contextData.['opt.sell']` quando è impostato su `Y`. Se `opt.sell` è `N`, [Gestione del consenso Opt-Out](cm-opt-out.md) viene compilata.

La tua organizzazione determina la logica necessaria per implementare queste variabili di dati di contesto. Non persistono oltre l’hit su cui sono impostati, pertanto devi impostare ogni variabile di dati di contesto su ogni pagina.

## Elementi Dimension

Gli elementi di Dimension includono i due valori seguenti:

* **`DMP`**: Il visitatore ha acconsentito alla condivisione su piattaforme di gestione dati. Questo elemento dimensione è presente quando la variabile di dati di contesto `opt.dmp` è `Y`.
* **`SELL`**: Il visitatore ha acconsentito alla condivisione o alla vendita dei dati a terzi. Questa dimensione è presente quando la variabile di dati di contesto `opt.sell` è `Y`.
