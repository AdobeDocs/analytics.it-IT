---
title: Tempo trascorso per visitatore (secondi)
description: null
translation-type: tm+mt
source-git-commit: 5282ad3f6fdd2853979cbfb2707cc07a698f63a7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 0%

---


# Tempo trascorso per visitatore (secondi)

La metrica &#39;Tempo trascorso per visitatore (secondi)&#39; mostra la quantità media di tempo che i visitatori interagiscono con un dato valore di dimensione durante l&#39;intera durata di un visitatore.

Questa metrica non è disponibile in Data Warehouse a causa della sua diversa architettura di elaborazione.

## Modalità di calcolo di questa metrica

Questa metrica utilizza la formula [`Total seconds spent`](total-seconds-spent.md)`divided by` [`Unique visitors`](unique-visitors.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo trascorso dall’intera dimensione per visitatore e il numeratore è il tempo trascorso per visitatore dal valore della dimensione. Se il tempo trascorso dall’intera dimensione per visitatore è inferiore al tempo trascorso per visitatore da un dato valore di dimensione, vedrete percentuali superiori al 100%. L&#39;ordinamento dei report classifica in base a questa metrica mostra il tempo di anomalia trascorso per i valori visitatore, che in genere non è prezioso. Adobe consiglia di ordinare i dati in base a un’altra metrica, ad esempio [Visite](visits.md), nei rapporti con classifica.

Consultate Panoramica sul [tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
