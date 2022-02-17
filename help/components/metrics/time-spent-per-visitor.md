---
title: Tempo trascorso per visitatore (secondi)
description: La metrica "Tempo trascorso per visitatore (secondi)" mostra la quantità media di tempo che i visitatori interagiscono con un dato elemento dimensionale durante l’intera durata di un visitatore.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Tempo trascorso per visitatore (secondi)

La [!UICONTROL Time spent per visitor (seconds)] mostra la quantità media di tempo che i visitatori interagiscono con un dato elemento dimensione durante l’intera vita di un visitatore.

Questa metrica non è disponibile nella Data Warehouse a causa della sua diversa architettura di elaborazione.

## Calcolo di questa metrica

Questa metrica utilizza la formula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo trascorso dall’intera dimensione per visitatore e il numeratore è il tempo trascorso dall’elemento dimensione per visitatore. Se il tempo trascorso dall’intera dimensione per visitatore è inferiore al tempo trascorso per visitatore di un dato elemento dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti con classifica in base a questa metrica mostra il tempo di anomalia trascorso per i valori dei visitatori, che in genere non è prezioso. L’Adobe consiglia l’ordinamento in base a un’altra metrica, ad esempio [Visite](visits.md), in rapporti con classifica.

Vedi [Panoramica del tempo trascorso](time-spent.md) informazioni più generali sul tempo trascorso.
