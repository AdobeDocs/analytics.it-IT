---
title: Visualizzazioni pagina
description: Il numero di volte in cui un elemento dimensione è stato impostato o mantenuto in Adobe Analytics.
feature: Metrics
exl-id: 6b4fb7af-03e2-49e8-a431-f7746c89a626
source-git-commit: 60a630c9934d613aa69523bdb87b92165a135eb9
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 2%

---

# Visualizzazioni pagina

Il **[!UICONTROL Page views]** La metrica mostra il numero di volte in cui un dato elemento dimensione (valore di dimensione) è stato definito o mantenuto (ovvero quando scade) in una pagina. È una delle metriche più comuni e di base nei rapporti.

Ad esempio, il [!UICONTROL Days of Week] La dimensione è composta dai seguenti elementi dimensionali: domenica, lunedì, martedì, mercoledì, giovedì, venerdì e sabato.

## Modalità di calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) in una suite di rapporti. Per le dimensioni, include gli hit in cui un elemento dimensione viene definito o mantenuto. Non include le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) o dati del riepilogo [Origini dati](/help/import/data-sources/overview.md).

## Confronta con metriche simili

* **Visualizzazioni di pagina e [Visite](visits.md)**: le visualizzazioni di pagina contano il numero di volte in cui viene visualizzata una pagina. Le visite contano il numero di sessioni per i visitatori. Una visita può essere costituita da una o più visualizzazioni di pagina.
* **Visualizzazioni di pagina e [Eventi pagina](page-events.md)**: le visualizzazioni di pagina contano il numero di chiamate di tracciamento delle visualizzazioni di pagina (`t()`), ed esclude le chiamate di tracciamento dei collegamenti (`tl()`). Gli eventi di pagina sono l’opposto; contano il numero di chiamate di tracciamento dei collegamenti ed escludono le chiamate di tracciamento della visualizzazione della pagina.
