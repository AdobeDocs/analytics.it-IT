---
title: 'Spiegazione della metrica Visualizzazioni pagina | Adobe Analytics '
description: Scopri come la metrica delle visualizzazioni di pagina viene elaborata in Adobe Analytics e anche comprendere la differenza tra le visualizzazioni di pagina e le visite.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 0%

---

# Informazioni sulle visualizzazioni di pagina con Adobe Analytics

La metrica &quot;Visualizzazioni di pagina&quot; mostra il numero di volte in cui un dato elemento dimensione è stato impostato o mantenuto su una pagina. È una delle metriche più comuni e di base nei rapporti.

## Calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento della visualizzazione della pagina ([`t()`](/help/implement/vars/functions/t-method.md)) in una suite di rapporti. Per le dimensioni, include hit in cui un elemento dimensione viene definito o mantenuto. Non include le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Confronto con metriche simili

* **Visualizzazioni di pagina e [Visite](visits.md)**: Le visualizzazioni di pagina contano il numero di volte in cui viene visualizzata una pagina. Le visite contano il numero di sessioni per i visitatori. Una visita consiste in una o più pagine.
* **Visualizzazioni di pagina e [Eventi pagina](page-events.md)**: Le visualizzazioni di pagina contano il numero di chiamate di tracciamento delle visualizzazioni di pagina (`t()`) ed esclude le chiamate di tracciamento dei collegamenti (`tl()`). Gli eventi di pagina sono opposti; conta il numero di chiamate di tracciamento dei collegamenti ed esclude le visualizzazioni di pagina.
