---
title: Tempo trascorso per visitatore (secondi)
description: null
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 0%

---


# Tempo trascorso per visitatore (secondi)

La metrica &#39;Tempo trascorso per visitatore (secondi)&#39; mostra la quantità media di tempo che i visitatori interagiscono con un dato elemento dimensione durante l&#39;intera durata di un visitatore.

Questa metrica non è disponibile nella Data warehouse a causa della sua diversa architettura di elaborazione.

## Modalità di calcolo di questa metrica

Questa metrica utilizza la formula [`Total seconds spent`](total-seconds-spent.md)`divided by` [`Unique visitors`](unique-visitors.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo trascorso dall’intera dimensione per visitatore e il numeratore è il tempo trascorso dall’elemento dimensione per visitatore. Se il tempo trascorso dall’intera dimensione per visitatore è inferiore al tempo trascorso per visitatore di un dato elemento dimensione, vengono visualizzate percentuali superiori al 100%. L&#39;ordinamento dei report classifica in base a questa metrica mostra il tempo di anomalia trascorso per i valori visitatore, che in genere non è prezioso. Adobe consiglia di ordinare i dati in base a un’altra metrica, ad esempio [Visite](visits.md), nei rapporti con classifica.

Consultate Panoramica sul [tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
