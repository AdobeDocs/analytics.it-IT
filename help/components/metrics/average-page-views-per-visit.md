---
title: Visualizzazioni di pagina medie per visita
description: Numero medio di volte in cui un dato elemento dimensione è stato visualizzato in una visita.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
source-git-commit: 7966c7d9add0011831c97fbe0dfcca2acd8afb58
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 4%

---

# Visualizzazioni di pagina medie per visita

La dimensione &quot;Visualizzazioni di pagina medie per visita&quot; mostra quante visualizzazioni di pagina si sono verificate in media rispetto alla dimensione desiderata. Per le dimensioni basate sul tempo, puoi vedere come il numero medio di visualizzazioni di pagina all’interno delle tendenze di una visita nel tempo. Questa metrica è utile quando desideri comprendere la frequenza con cui vengono visualizzati gli elementi dimensionali in una visita.

>[!TIP]
>
>Utilizza questa metrica accanto a un’altra metrica (ad esempio [Visite](visits.md)) per ottenere informazioni migliori. Se utilizzi questa metrica da solo, ottieni elementi dimensionali contenenti anomalie nelle visualizzazioni di pagina per visita, che in genere non è prezioso.

## Calcolo di questa metrica

Questa metrica viene calcolata utilizzando la formula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la media di visualizzazioni di pagina per visita dell’intera dimensione e il numeratore è la media di visualizzazioni di pagina per visita dell’elemento dimensionale. Se le visualizzazioni di pagina medie per visita dell’intera dimensione sono inferiori alle visualizzazioni di pagina medie per visita di un dato elemento dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti con classifica in base a questa metrica mostra una media anomala delle visualizzazioni di pagina per valori di visita, che in genere non è preziosa. L’Adobe consiglia l’ordinamento in base a un’altra metrica, ad esempio [Visite](visits.md), in rapporti con classifica.
