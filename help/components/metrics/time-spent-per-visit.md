---
title: Tempo trascorso per visita (metriche)
description: Quantità di tempo trascorso per visita per l’elemento dimensione.
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# Tempo trascorso per visita (secondi)

*Questa pagina di aiuto descrive come funziona come una metrica il tempo trascorso per visita. Consulta la sezione [Tempo trascorso per visita](../dimensions/time-spent-per-visit.md) per ulteriori informazioni.*

La metrica &quot;Tempo trascorso per visita (secondi)&quot; mostra la quantità media di tempo che i visitatori interagiscono con un dato elemento dimensionale durante ogni visita.

Questa metrica non è disponibile nella Data Warehouse a causa della sua diversa architettura di elaborazione.

## Calcolo di questa metrica

Questa metrica utilizza la formula [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Confronto con tempo medio sul sito

Questa metrica e [Tempo medio trascorso sul sito](average-time-on-site.md) sono simili, ma presentano diverse differenze chiave. Entrambe le metriche utilizzano il valore &quot;Totale secondi trascorsi&quot; come numeratore. Tuttavia, &quot;Tempo medio sul sito&quot; utilizza le sequenze che includono un elemento dimensione come denominatore. Il tempo trascorso per visita utilizza come denominatore il conteggio delle visite.

Di conseguenza, queste metriche producono risultati simili a livello di visita, ma sono diverse a livello di hit.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è il tempo trascorso dall’intera dimensione per visita e il numeratore è il tempo trascorso dall’elemento dimensionale per visita. Se il tempo trascorso dall’intera dimensione per visita è inferiore al tempo trascorso da un dato elemento dimensione per visita, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti con classifica in base a questa metrica mostra il tempo di anomalia trascorso per valori di visita, che in genere non è prezioso. L’Adobe consiglia l’ordinamento in base a un’altra metrica, ad esempio [Visite](visits.md), in rapporti con classifica.

Vedi [Panoramica del tempo trascorso](time-spent.md) informazioni più generali sul tempo trascorso.
