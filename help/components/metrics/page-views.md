---
title: Visualizzazioni pagina
description: Il numero di volte in cui un elemento dimensione è stato impostato o reso persistente in Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 100%

---

# Visualizzazioni pagina

La metrica **[!UICONTROL Page views]** mostra il numero di volte in cui un dato elemento dimensione (valore di dimensione) è stato definito o reso persistente (per esempio quando scade) su una pagina.[](overview.md) È una delle metriche più comuni e di base nei rapporti.

Ad esempio, la dimensione [!UICONTROL Days of Week] è composta dai seguenti elementi dimensionali: domenica, lunedì, martedì, mercoledì, giovedì, venerdì e sabato.

## Come è calcolata questa metrica

Questa metrica calcola tutte le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) in una suite di rapporti. Per le dimensioni, include gli hit in cui un elemento dimensione viene definito o reso persistente. Non include le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) o dati del riepilogo [Origini dati](/help/import/data-sources/overview.md).

## Confronto con metriche simili

* **Visualizzazioni di pagina rispetto a [Visite](visits.md)**: le visualizzazioni di pagina calcolano il numero di volte in cui viene visualizzata una pagina. Le visite calcolano il numero di sessioni per i visitatori. Una visita può essere costituita da una o più visualizzazioni di pagina.
* **Visualizzazioni di pagina rispetto a [Eventi di pagina](page-events.md)**: le visualizzazioni di pagina calcolano il numero di chiamate di tracciamento delle visualizzazioni di pagina (`t()`) ed escludono le chiamate di tracciamento dei collegamenti (`tl()`). Gli eventi di pagina sono l’opposto: calcolano il numero di chiamate di tracciamento dei collegamenti ed escludono le chiamate di tracciamento della visualizzazione di pagina.
