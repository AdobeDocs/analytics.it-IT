---
title: Occorrenze
description: Il numero di hit impostati o mantenuti da una variabile.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 1be9a8ceb03f8102a0799f4518db35c1e8cd7b14
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 1%

---

# Occorrenze

La metrica &quot;Occorrenze&quot; mostra il numero di hit in cui una determinata dimensione è stata impostata o persistente. Quando trascini una dimensione in Workspace in un’area di lavoro vuota, Adobe applica automaticamente questa metrica al progetto.

## Calcolo di questa metrica

Di tutti gli hit in una suite di rapporti, includi quelli in cui un elemento dimensione viene definito o mantenuto. Alcune dimensioni, ad esempio [eVar](../dimensions/evar.md), persistono oltre l’hit su cui sono impostati. Questa metrica conta sia i valori iniziali che quelli persistenti.

## Confronto con metriche simili

* **Occorrenze e [Istanze](instances.md)**: Le occorrenze contano gli hit in cui un elemento dimensione è stato impostato o mantenuto. Le istanze non includono gli hit in cui un elemento dimensione persiste.
* **Occorrenze e [Visualizzazioni pagina](page-views.md)**: Le occorrenze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione della pagina ([`t()`](/help/implement/vars/functions/t-method.md)), chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) e i dati dal riepilogo [Origini dati](/help/import/data-sources/overview.md). La metrica delle visualizzazioni di pagina include solo le chiamate di tracciamento delle visualizzazioni di pagina, escluse le chiamate di tracciamento dei collegamenti e le origini dei dati di riepilogo.
