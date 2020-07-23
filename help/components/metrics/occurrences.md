---
title: Occorrenze
description: Numero di hit impostati o persistenti da una variabile.
translation-type: tm+mt
source-git-commit: 422e99d9ea70f0192443d7ebc3631c6bf99e7591
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 1%

---


# Occorrenze

La metrica &#39;Occorrenze&#39; mostra il numero di hit in cui una determinata dimensione è stata impostata o persistente. Quando si trascina una dimensione in Workspace su un quadro vuoto, Adobe applica automaticamente questa metrica al progetto.

## Modalità di calcolo di questa metrica

Tra tutti gli hit in una suite di rapporti, puoi includere quelli in cui un elemento dimensione è definito o persistente. Alcune dimensioni, come [eVar](../dimensions/evar.md), persistono oltre l’hit su cui sono impostate. Metriche come visualizzazioni [di](page-views.md) pagina e [occorrenze](occurrences.md) contano sia i valori iniziali che quelli persistenti.

## Confronto con metriche simili

* **Occorrenze e[istanze](instances.md)**: Gli hit di conteggio delle occorrenze in cui un elemento dimensione è stato impostato o persistente. Le istanze non includono hit in cui un elemento dimensione persiste.
* **Occorrenze e visualizzazioni[](page-views.md)**pagina: Le occorrenze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione della pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)). La metrica delle visualizzazioni di pagina include solo le chiamate di tracciamento delle visualizzazioni di pagina ed esclude le chiamate di tracciamento dei collegamenti.
