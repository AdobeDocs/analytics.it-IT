---
title: Area geografica di Activity Map
description: L’area del sito su cui hai fatto clic.
feature: Dimensions
role: User, Admin
source-git-commit: 05010d58ba2a3376473097e9d4543ee4415e83e1
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 5%

---

# Area geografica di Activity Map

Nella &#39;Area Activity Map&#39; [dimensione](overview.md) sono visualizzate le aree del sito in cui si è fatto più clic. Questa dimensione è utile quando desideri confrontare i clic tra aree generali del sito anziché tra singoli collegamenti. È utile anche per le aree del sito che forniscono contenuti dinamici. Ad esempio, se hai una pagina iniziale con articoli di notizie rotanti, utilizzare la dimensione [Collegamento Activity Map](activity-map-link.md) sarebbe difficile perché il testo del collegamento cambia costantemente. Tuttavia, poiché tali collegamenti utilizzano la stessa area, è possibile analizzarne le prestazioni anche se i singoli collegamenti potrebbero cambiare ogni giorno.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla [variabile di dati di contesto](/help/implement/vars/page-vars/contextdata.md) `c.a.activitymap.region`. Se l&#39;implementazione utilizza [Activity Map](/help/analyze/activity-map/overview.md), questa variabile di dati di contesto raccoglie automaticamente i dati quando si fa clic sui collegamenti.

Per un determinato collegamento su cui è stato fatto clic, controlla l’elemento DOM principale in base all’ordine:

* Valore nell&#39;attributo impostato da [`ActivityMap.regionIDAttribute`](/help/implement/vars/config-vars/activitymap-regionidattribute.md) - impostato sull&#39;attributo `id` per impostazione predefinita
* Un valore nell&#39;attributo `aria-label` quando l&#39;attributo `role="region"`
* Elementi semantici `<header>`, `<main>`, `<footer>` o `<nav>` (solo Web SDK)

Se l&#39;elemento DOM padre non soddisfa nessuno dei criteri di cui sopra, la ricerca continua in modo ricorsivo fino alla gerarchia DOM. Se non vengono trovati elementi corrispondenti, viene restituito il valore `BODY`.

## Elementi dimensionali

Gli elementi di Dimension includono le aree etichettate sul sito. I valori di regione specifici dipendono dagli attributi utilizzati e dalla presenza di elementi HTML semantici.
