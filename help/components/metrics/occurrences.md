---
title: Occorrenze
description: Numero di hit impostati o persistenti da una variabile.
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 1%

---


# Occorrenze

La metrica &#39;Occorrenze&#39; mostra il numero di hit in cui una determinata dimensione è stata impostata o persistente. Quando si trascina una dimensione in Workspace su un quadro vuoto,  Adobe applica automaticamente questa metrica al progetto.

## Modalità di calcolo di questa metrica

Tra tutti gli hit in una suite di rapporti, puoi includere quelli in cui un elemento dimensione è definito o persistente. Alcune dimensioni, come [eVar](../dimensions/evar.md), persistono oltre l’hit su cui sono impostate. Questa metrica conta sia i valori iniziali che quelli persistenti.

## Confronto con metriche simili

* **Occorrenze e[istanze](instances.md)**: Gli hit di conteggio delle occorrenze in cui un elemento dimensione è stato impostato o persistente. Le istanze non includono hit in cui un elemento dimensione persiste.
* **Occorrenze e visualizzazioni[](page-views.md)** pagina: Le occorrenze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione della pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)). La metrica delle visualizzazioni di pagina include solo le chiamate di tracciamento delle visualizzazioni di pagina ed esclude le chiamate di tracciamento dei collegamenti.
