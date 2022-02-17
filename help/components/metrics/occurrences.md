---
title: Occorrenze
description: Il numero di hit impostati o mantenuti da una variabile.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 1%

---

# Occorrenze

La metrica &quot;Occorrenze&quot; mostra il numero di hit in cui una determinata dimensione è stata impostata o persistente. Quando trascini una dimensione in Workspace in un’area di lavoro vuota, Adobe applica automaticamente questa metrica al progetto.

## Calcolo di questa metrica

Di tutti gli hit in una suite di rapporti, includi quelli in cui un elemento dimensione viene definito o mantenuto. Alcune dimensioni, ad esempio [eVar](../dimensions/evar.md), persistono oltre l’hit su cui sono impostati. Questa metrica conta sia i valori iniziali che quelli persistenti.

## Confronto con metriche simili

* **Occorrenze e [Istanze](instances.md)**: Le occorrenze contano gli hit in cui un elemento dimensione è stato impostato o mantenuto. Le istanze non includono gli hit in cui un elemento dimensione persiste.
* **Occorrenze e [Visualizzazioni pagina](page-views.md)**: Le occorrenze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione della pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)). La metrica delle visualizzazioni di pagina include solo le chiamate di tracciamento delle visualizzazioni di pagina ed esclude le chiamate di tracciamento dei collegamenti.
