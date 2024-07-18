---
title: Occorrenze
description: Numero di hit in cui una variabile è stata impostata o è persistente.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 100%

---

# Occorrenze

La [metrica](overview.md) “Occorrenze” mostra il numero di hit in cui una determinata dimensione è stata impostata o è persistente. Quando trascini una dimensione in Workspace su un’area di lavoro vuota, Adobe applica automaticamente questa metrica al progetto.

## Come è calcolata questa metrica

Di tutti gli hit in una suite di rapporti, includi gli hit in cui un elemento dimensionale è definito o persistente. Alcune dimensioni, come le [eVar](../dimensions/evar.md) persistono oltre l’hit su cui sono impostate. Questa metrica conta sia i valori iniziali che quelli persistenti.

## Confronto con metriche simili

* Differenza tra le **occorrenze e le [istanze](instances.md)**: le occorrenze contano gli hit in cui un elemento dimensionale è stato impostato o è persistente. Le istanze non includono gli hit in cui un elemento dimensionale persiste.
* Differenza tra le **occorrenze e le [visualizzazioni pagina](page-views.md)**: le occorrenze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)), le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) e i dati del riepilogo delle [Origini dati](/help/import/data-sources/overview.md). La metrica delle visualizzazioni pagina include solo le chiamate di tracciamento della visualizzazione della pagina, escluse le chiamate di tracciamento dei collegamenti e le origini dati di riepilogo.
