---
title: Tempo trascorso per visita (metriche)
description: La quantità di tempo trascorso per visita per l’elemento dimensione.
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
source-git-commit: 10ff98f7ca4697afe5c2dae66be415c0d68c4aac
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 0%

---

# Tempo trascorso per visita (secondi)

*Questa pagina di aiuto descrive come funziona il &quot;Tempo trascorso per visita&quot; come metrica. Consulta la [Tempo trascorso per visita](../dimensions/time-spent-per-visit.md) per ulteriori informazioni.*

La metrica &quot;Tempo trascorso per visita (secondi)&quot; mostra il tempo medio in cui i visitatori interagiscono con un dato elemento dimensionale durante ogni visita.

Questa metrica non è disponibile in Data Warehouse a causa della diversa architettura di elaborazione.

## Modalità di calcolo di questa metrica

Questa metrica utilizza la formula [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Confronto con il tempo medio sul sito

Questa metrica e [Tempo medio trascorso sul sito](average-time-on-site.md) sono simili, ma presentano diverse differenze chiave. Entrambe le metriche utilizzano il numeratore &quot;Totale secondi trascorsi&quot;. Tuttavia, &quot;Tempo medio sul sito&quot; utilizza le sequenze che includono un elemento dimensione come denominatore. Il tempo trascorso per visita utilizza il conteggio delle visite come denominatore.

Di conseguenza, queste metriche producono risultati simili a livello di visita, ma sono diverse a livello di hit.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è l’intero tempo trascorso per visita della dimensione e il numeratore è il tempo trascorso per visita dell’elemento dimensionale. Se il tempo trascorso per visita dell’intera dimensione è inferiore al tempo trascorso per visita di un dato elemento dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti classificati per questa metrica mostra il tempo di anomalia trascorso per i valori di visita, che in genere non è prezioso. L’Adobe consiglia di ordinare per un’altra metrica, ad esempio [Visite](visits.md), nei rapporti classificati.

Consulta [Panoramica sul tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
