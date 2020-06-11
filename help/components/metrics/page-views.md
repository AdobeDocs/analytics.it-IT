---
title: Visualizzazioni pagina
description: Il numero di volte in cui è stata visualizzata una pagina.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 2%

---


# Visualizzazioni pagina

La metrica Visualizzazioni di pagina mostra il numero di volte in cui un dato valore di dimensione è stato impostato o persistente su una pagina. È una delle metriche più comuni e di base nei report.

## Modalità di calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) in una suite di rapporti. Per le dimensioni, include hit in cui viene definito o mantenuto un valore di dimensione. Non include le chiamate per il tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Confronto con metriche simili

* **Visualizzazioni di pagina e[visite](visits.md)**: Le visualizzazioni pagina contano il numero di volte che una pagina viene visualizzata. Le visite contano il numero di sessioni per i visitatori. Una visita consiste in una o più pagine.
* **Visualizzazioni di pagina e eventi[di](page-events.md)**pagina: Le visualizzazioni di pagina contano il numero di chiamate di tracciamento delle visualizzazioni di pagina (`t()`) ed esclude le chiamate di tracciamento dei collegamenti (`tl()`). Eventi pagina è l’opposto; conteggia il numero di chiamate di tracciamento dei collegamenti ed esclude le visualizzazioni di pagina.