---
title: Occorrenze
description: Numero di hit impostati o persistenti da una variabile.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 1%

---


# Occorrenze

La metrica &#39;Occorrenze&#39; mostra il numero di hit in cui una determinata dimensione è stata impostata o persistente. Quando si trascina una dimensione in Workspace su un quadro vuoto, Adobe applica automaticamente questa metrica al progetto.

## Modalità di calcolo di questa metrica

Tra tutti gli hit in una suite di rapporti, includi quelli in cui è definito o persistente un valore di dimensione. Alcune dimensioni, come [eVar](../dimensions/evar.md), persistono oltre l’hit su cui sono impostate. Metriche come visualizzazioni [di](page-views.md) pagina e [occorrenze](occurrences.md) contano sia i valori iniziali che quelli persistenti. Questa metrica non conta i valori persistenti.

## Confronto con metriche simili

* **Occorrenze e[istanze](instances.md)**: Le occorrenze contano gli hit in cui un valore di dimensione è stato impostato o persistente. Le istanze non includono hit in cui persiste un valore di dimensione.
* **Occorrenze e visualizzazioni[](page-views.md)**pagina: Le occorrenze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione della pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)). La metrica delle visualizzazioni di pagina include solo le chiamate di tracciamento delle visualizzazioni di pagina ed esclude le chiamate di tracciamento dei collegamenti.