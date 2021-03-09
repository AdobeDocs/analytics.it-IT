---
title: Tempo trascorso per visitatore (secondi)
description: La metrica "Tempo trascorso per visitatore (secondi)" mostra la quantità media di tempo che i visitatori interagiscono con un dato elemento dimensionale durante l’intera durata di un visitatore.
translation-type: tm+mt
source-git-commit: 4d0d5ca99049e48fcf1f248f78ecef94534b6815
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---


# Tempo trascorso per visitatore (secondi)

La metrica [!UICONTROL Time spent per visitor (seconds)] mostra la quantità media di tempo che i visitatori interagiscono con un dato elemento dimensione durante l’intera durata di un visitatore.

Questa metrica non è disponibile nella Data Warehouse a causa della sua diversa architettura di elaborazione.

## Calcolo di questa metrica

Questa metrica utilizza la formula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo trascorso dall’intera dimensione per visitatore e il numeratore è il tempo trascorso dall’elemento dimensione per visitatore. Se il tempo trascorso dall’intera dimensione per visitatore è inferiore al tempo trascorso per visitatore di un dato elemento dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti con classifica in base a questa metrica mostra il tempo di anomalia trascorso per i valori dei visitatori, che in genere non è prezioso. Adobe consiglia di ordinare in base a un’altra metrica, ad esempio [Visite](visits.md), nei rapporti con classifica.

Per informazioni più generali sul tempo trascorso, consulta [Panoramica sul tempo trascorso](time-spent.md) .
