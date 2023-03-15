---
title: Visualizzazioni pagina
description: Il numero di volte in cui un elemento dimensione è stato impostato o mantenuto in Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 65f87bf4b5b3897c9ef68d091858332c08cbf699
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 2%

---

# Visualizzazioni pagina

La metrica &quot;Visualizzazioni pagina&quot; mostra quante volte un dato elemento dimensione è stato impostato o mantenuto in una pagina. È una delle metriche più comuni e di base nei rapporti.

## Modalità di calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) in una suite di rapporti. Per le dimensioni, include gli hit in cui un elemento dimensione viene definito o mantenuto. Non include le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Confronta con metriche simili

* **Visualizzazioni di pagina e [Visite](visits.md)**: le visualizzazioni di pagina contano il numero di volte in cui viene visualizzata una pagina. Le visite contano il numero di sessioni per i visitatori. Una visita è costituita da una o più visualizzazioni di pagina.
* **Visualizzazioni di pagina e [Eventi pagina](page-events.md)**: le visualizzazioni di pagina contano il numero di chiamate di tracciamento delle visualizzazioni di pagina (`t()`), ed esclude le chiamate di tracciamento dei collegamenti (`tl()`). Gli eventi di pagina sono l’opposto; contano il numero di chiamate di tracciamento dei collegamenti ed escludono le chiamate di tracciamento della visualizzazione della pagina.
