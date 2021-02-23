---
title: 'Metrica Visualizzazioni pagina spiegata |  Adobe Analytics '
description: Scoprite come la metrica delle visualizzazioni di pagina viene elaborata in  Adobe Analytics e come è possibile comprendere la differenza tra le visualizzazioni di pagina e le visite.
translation-type: tm+mt
source-git-commit: c588087b949093152435967f62e43758e9e86208
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---


# Ulteriori informazioni sulle visualizzazioni di pagina con  Adobe Analytics

La metrica Visualizzazioni di pagina mostra il numero di volte in cui un dato elemento dimensione è stato impostato o persistente su una pagina. È una delle metriche più comuni e di base nei report.

## Modalità di calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) in una suite di rapporti. Per le dimensioni, include hit in cui un elemento dimensione è definito o persistente. Non include le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Confronto con metriche simili

* **Visualizzazioni di pagina e  [visite](visits.md)**: Le visualizzazioni pagina contano il numero di volte che una pagina viene visualizzata. Le visite contano il numero di sessioni per i visitatori. Una visita consiste in una o più pagine.
* **Visualizzazioni di pagina e eventi [ di](page-events.md)** pagina: Le visualizzazioni di pagina contano il numero di chiamate di tracciamento delle visualizzazioni di pagina (`t()`) ed esclude le chiamate di tracciamento dei collegamenti (`tl()`). Eventi pagina è l’opposto; conteggia il numero di chiamate di tracciamento dei collegamenti ed esclude le visualizzazioni di pagina.