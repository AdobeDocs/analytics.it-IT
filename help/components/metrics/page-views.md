---
title: Visualizzazioni pagina
description: Il numero di volte in cui un elemento dimensione è stato impostato o reso persistente in Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 46%

---

# Visualizzazioni pagina

Il **[!UICONTROL Page views]** [metrica](overview.md) mostra quante volte un dato elemento dimensionale è stato impostato o mantenuto in una pagina. È una delle metriche più comuni e di base nei rapporti.

## Come è calcolata questa metrica

Questa metrica calcola tutte le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) in una suite di rapporti. Per le dimensioni, include gli hit in cui un elemento dimensione viene impostato o mantenuto. Non include le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) o dati da [Origini dati](/help/import/data-sources/overview.md).

## Confronto con metriche simili

* **Visualizzazioni di pagina e [Visite](visits.md)**: le visualizzazioni di pagina contano il numero di volte in cui viene visualizzata una pagina. Le visite calcolano il numero di sessioni per i visitatori. Una visita è costituita da una o più visualizzazioni di pagina.
* **Visualizzazioni di pagina e [Eventi pagina](page-events.md)**: le visualizzazioni di pagina contano il numero di chiamate di tracciamento delle visualizzazioni di pagina (`t()`) ed escludono le chiamate di tracciamento dei collegamenti (`tl()`). Gli eventi di pagina sono l’opposto: calcolano il numero di chiamate di tracciamento dei collegamenti ed escludono le chiamate di tracciamento della visualizzazione di pagina.
