---
title: Occorrenze
description: Numero di hit in cui una variabile è stata impostata o è persistente.
feature: Metrics
exl-id: 8428e813-0fb4-4620-884e-1aa92fe33209
TQID: https://experienceleague.adobe.com/04bDCj1dkVb9gIDMbpvvGea92oOzd-N0XLfzf4t-6iA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: 5e560c5a1c241a297a7bc876978f2996e793e1ea
workflow-type: tm+mt
source-wordcount: 280
ht-degree: 66%

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
