---
title: Tempo trascorso per visita
description: Quantità di tempo trascorso per visita per l’elemento dimensione.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---


# Tempo trascorso per visita (secondi)

*In questa pagina dell’Aiuto viene descritto come &quot;Tempo trascorso per visita&quot; funziona come una metrica. Per ulteriori informazioni, consulta la dimensione[Tempo trascorso per visita](../dimensions/time-spent-per-visit.md).*

La metrica &quot;Tempo trascorso per visita (secondi)&quot; mostra la quantità media di tempo che i visitatori interagiscono con un dato elemento dimensione durante ogni visita.

Questa metrica non è disponibile nella Data warehouse a causa della sua diversa architettura di elaborazione.

## Modalità di calcolo di questa metrica

Questa metrica utilizza la formula [`Total seconds spent`](total-seconds-spent.md) ( `divided by`[`Visits`](visits.md) ) `minus` ( [`Bounces`](bounces.md)).

## Confronto con tempo medio sul sito

Questa metrica e il tempo [medio trascorso sul sito](average-time-on-site.md) sono simili, ma presentano diverse differenze chiave. Entrambe le metriche utilizzano il valore &quot;Totale secondi trascorsi&quot; come numeratore. Tuttavia, &#39;Tempo medio sul sito&#39; utilizza le sequenze che includono un elemento dimensione come denominatore. Il tempo trascorso per visita utilizza il conteggio visite come denominatore.

Di conseguenza, queste metriche producono risultati simili a livello di visita, ma sono diverse a livello di hit.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo trascorso dall&#39;intera dimensione per visita, e il numeratore è il tempo trascorso dall&#39;elemento della dimensione per visita. Se il tempo trascorso per visita dell&#39;intera dimensione è inferiore al tempo trascorso per visita di un dato elemento dimensione, vengono visualizzate percentuali superiori al 100%. L&#39;ordinamento dei report classifica in base a questa metrica mostra il tempo di anomalia trascorso per i valori delle visite, che in genere non è prezioso. Adobe consiglia di ordinare i dati in base a un’altra metrica, ad esempio [Visite](visits.md), nei rapporti con classifica.

Consultate Panoramica sul [tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
