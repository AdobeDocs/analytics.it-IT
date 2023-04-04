---
title: Visualizzazioni pagina
description: Il numero di volte in cui un elemento dimensione è stato impostato o mantenuto in Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 1be9a8ceb03f8102a0799f4518db35c1e8cd7b14
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 2%

---

# Visualizzazioni pagina

La metrica &quot;Visualizzazioni di pagina&quot; mostra il numero di volte in cui un dato elemento dimensione è stato impostato o mantenuto su una pagina. È una delle metriche più comuni e di base nei rapporti.

## Calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento della visualizzazione della pagina ([`t()`](/help/implement/vars/functions/t-method.md)) in una suite di rapporti. Per le dimensioni, include hit in cui un elemento dimensione viene definito o mantenuto. Non include le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) o i dati dal riepilogo [Origini dati](/help/import/data-sources/overview.md).

## Confronto con metriche simili

* **Visualizzazioni di pagina e [Visite](visits.md)**: Le visualizzazioni di pagina contano il numero di volte in cui viene visualizzata una pagina. Le visite contano il numero di sessioni per i visitatori. Una visita consiste in una o più visualizzazioni di pagina.
* **Visualizzazioni di pagina e [Eventi pagina](page-events.md)**: Le visualizzazioni di pagina contano il numero di chiamate di tracciamento delle visualizzazioni di pagina (`t()`) ed esclude le chiamate di tracciamento dei collegamenti (`tl()`). Gli eventi di pagina sono opposti; contano il numero di chiamate di tracciamento dei collegamenti ed escludono le chiamate di tracciamento delle visualizzazioni di pagina.
