---
title: Occorrenze
description: Numero di hit in cui una variabile è stata impostata o è persistente.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
source-git-commit: 0c5062363e10d9b545a3209ebaefcc6fa5d02c8b
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 57%

---

# Occorrenze

La [metrica](overview.md) “Occorrenze” mostra il numero di hit in cui una determinata dimensione è stata impostata o è persistente. Quando trascini una dimensione in Workspace su un’area di lavoro vuota, Adobe applica automaticamente questa metrica al progetto.

## Come è calcolata questa metrica

Di tutti gli hit in una suite di rapporti, includi gli hit in cui un elemento dimensionale è definito o persistente. Alcune dimensioni, come le [eVar](../dimensions/evar.md) persistono oltre l’hit su cui sono impostate. Questa metrica conta sia i valori iniziali che quelli persistenti.

## Confronto con metriche simili

* Differenza tra le **occorrenze e le [istanze](instances.md)**: le occorrenze contano gli hit in cui un elemento dimensionale è stato impostato o è persistente. Le istanze non includono gli hit in cui un elemento dimensionale persiste.
* Differenza tra le **occorrenze e le [visualizzazioni pagina](page-views.md)**: le occorrenze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)), le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) e i dati del riepilogo delle [Origini dati](/help/import/data-sources/overview.md). La metrica delle visualizzazioni pagina include solo le chiamate di tracciamento della visualizzazione della pagina, escluse le chiamate di tracciamento dei collegamenti e le origini dati di riepilogo.

## Persistenza

La persistenza è la capacità di un dato valore di dimensione di riferirsi a una metrica oltre l’evento su cui è impostato. Utilizza una combinazione di allocazione e scadenza. L’allocazione consente di determinare quale valore viene mantenuto quando più elementi dimensionali possono persistere alla volta in una singola colonna. Scadenza consente di determinare per quanto tempo un elemento dimensione persiste oltre l’evento su cui è impostato.

La persistenza è disponibile solo sulle dimensioni ed è retroattiva per i dati a cui viene applicata. Si tratta di una trasformazione immediata dei dati che avviene prima dell’applicazione di filtri o di altre operazioni di analisi. Se la persistenza non è abilitata, la dimensione si riferisce solo alle metriche esistenti nello stesso evento.