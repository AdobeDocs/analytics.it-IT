---
title: Gestione del consenso Opt-Out
description: Scopri le impostazioni di privacy di cui un visitatore ha rinunciato.
source-git-commit: 49b2c144fea5786564ccb6dc70adead3bc669596
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 2%

---

# Gestione del consenso Opt-Out

La dimensione &quot;Consent Management Opt-Out&quot; visualizza le impostazioni di privacy da cui un visitatore ha esplicitamente rinunciato. Puoi utilizzare questa dimensione per filtrare i dati in base alle impostazioni di privacy o per visualizzare i motivi più comuni di rinuncia alla privacy.

## Popolare questa dimensione con i dati

Questa dimensione raccoglie i dati seguenti [Variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md):

* `contextData.['cm.ssf']` quando è impostato su `1`. Se `cm.ssf` è `0` o è vuoto, questa variabile non esegue alcuna operazione.
* `contextData.['opt.dmp']` quando è impostato su `N`. Se `opt.dmp` è `Y`, [Gestione del consenso Opt-in](cm-opt-in.md) viene compilata.
* `contextData.['opt.sell']` quando è impostato su `N`. Se `opt.sell` è `Y`, [Gestione del consenso Opt-in](cm-opt-in.md) viene compilata.

La tua organizzazione determina la logica necessaria per implementare queste variabili di dati di contesto. Non persistono oltre l’hit su cui sono impostati, pertanto devi impostare ogni variabile di dati di contesto su ogni pagina.

## Elementi Dimension

Gli elementi di Dimension includono i tre valori seguenti:

* **`SSF`**: Il visitatore ha rinunciato [Inoltro lato server](/help/admin/admin/c-server-side-forwarding/ssf.md). Questo elemento dimensione è presente quando la variabile di dati di contesto `cm.ssf` è `1`. Vedi [Panoramica sulla privacy dei dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html) nella guida utente di Audience Manager per ulteriori informazioni.
* **`DMP`**: Il visitatore ha rinunciato alla condivisione su piattaforme di gestione dati. Questo elemento dimensione è presente quando la variabile di dati di contesto `opt.dmp` è `N`. L&#39;hit non viene inoltrato a Adobe Audience Manager.
* **`SELL`**: Il visitatore ha rinunciato alla condivisione o alla vendita dei dati a terzi. Questa dimensione è presente quando la variabile di dati di contesto `opt.sell` è `N`.
