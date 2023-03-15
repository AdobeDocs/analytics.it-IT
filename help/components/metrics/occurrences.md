---
title: Occorrenze
description: Numero di hit impostati o persistenti per una variabile.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 1%

---

# Occorrenze

La metrica &quot;Occorrenze&quot; mostra il numero di hit in cui una determinata dimensione è stata impostata o persistita. Quando trascini una dimensione in Workspace su un’area di lavoro vuota, Adobe applica automaticamente questa metrica al progetto.

## Modalità di calcolo di questa metrica

Di tutti gli hit in una suite di rapporti, includi gli hit in cui un elemento dimensione è definito o persistente. Alcune dimensioni, come [eVar](../dimensions/evar.md), persistono oltre l&#39;hit su cui sono impostati. Questa metrica conta sia i valori iniziali che quelli persistenti.

## Confronta con metriche simili

* **Occorrenze e [Istanze](instances.md)**: occorrenze che contano gli hit in cui è stato impostato o mantenuto un elemento dimensione. Le istanze non includono gli hit in cui un elemento dimensione persiste.
* **Occorrenze e [Visualizzazioni pagina](page-views.md)**: le occorrenze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)). La metrica delle visualizzazioni di pagina include solo le chiamate di tracciamento della visualizzazione della pagina ed esclude le chiamate di tracciamento dei collegamenti.
