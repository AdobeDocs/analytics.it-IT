---
title: Visualizzazioni di pagina medie per visita
description: Il numero medio di volte in cui un dato elemento dimensione è apparso in una visita.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 4%

---

# Visualizzazioni di pagina medie per visita

La dimensione &quot;Visualizzazioni di pagina medie per visita&quot; mostra quante visualizzazioni di pagina si sono verificate in media rispetto alla dimensione desiderata. Per le dimensioni basate sul tempo, puoi vedere le tendenze nel tempo del numero medio di visualizzazioni di pagina all’interno di una visita. Questa metrica è utile quando vuoi comprendere con quale frequenza vengono visualizzati gli elementi dimensionali in una visita.

>[!TIP]
>
>Utilizza questa metrica insieme a un’altra metrica (ad esempio [Visite](visits.md)) per ottenere informazioni migliori. Se utilizzi questa metrica da sola, otterrai elementi dimensionali contenenti visualizzazioni di pagina anomale per visita, che in genere non sono preziose.

## Modalità di calcolo di questa metrica

Questa metrica viene calcolata utilizzando la formula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la media di visualizzazioni di pagina per visita dell’intera dimensione e il numeratore è la media di visualizzazioni di pagina per visita dell’elemento dimensione. Se la media di visualizzazioni di pagina per visita dell’intera dimensione è inferiore alla media di visualizzazioni di pagina per visita di un dato elemento dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti classificati in base a questa metrica mostra anomalie nella media delle visualizzazioni di pagina per visita, valori che in genere non sono preziosi. L’Adobe consiglia di ordinare per un’altra metrica, ad esempio [Visite](visits.md), nei rapporti classificati.
