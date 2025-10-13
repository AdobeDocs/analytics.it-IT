---
title: Tempo trascorso per visitatore (secondi)
description: La metrica "Tempo trascorso per visitatore (secondi)" mostra il tempo medio in cui i visitatori interagiscono con un dato elemento dimensionale durante l’intera vita di un visitatore.
feature: Metrics
exl-id: 80f38bab-2ee1-4d0d-ba53-9b2c7c85e481
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 2%

---

# Tempo trascorso per visitatore (secondi)

La [!UICONTROL Time spent per visitor (seconds)] [metrica](overview.md) mostra il tempo medio per cui i visitatori interagiscono con un dato elemento della dimensione durante l&#39;intera vita di un visitatore.

Questa metrica non è disponibile in Data Warehouse a causa della diversa architettura di elaborazione.

## Come è calcolata questa metrica

Questa metrica utilizza la formula [`Total seconds spent`](total-seconds-spent.md) `divided by` [`Unique visitors`](unique-visitors.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo trascorso dall’intera dimensione per visitatore e il numeratore è il tempo trascorso dall’elemento dimensione per visitatore. Se il tempo trascorso dell’intera dimensione per visitatore è inferiore al tempo trascorso per visitatore di un dato elemento della dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti classificati in base a questa metrica mostra il tempo di anomalia trascorso per i valori dei visitatori, che in genere non è prezioso. Adobe consiglia di ordinare i rapporti in base a un&#39;altra metrica, ad esempio [Visite](visits.md).

Consulta [Panoramica sul tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
