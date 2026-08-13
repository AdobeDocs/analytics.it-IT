---
title: Tempo trascorso per visita (metriche)
description: La quantità di tempo trascorso per visita per l’elemento dimensione.
feature: Metrics
exl-id: 0f951196-66a2-4733-bb62-4555a9331efb
TQID: https://experienceleague.adobe.com/X1RtHTTmu0VIblFC3jANE7d6bIbtm4W5OvqFZDp8bLE
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 263
ht-degree: 1%

---

# Tempo trascorso per visita (secondi)

*Questa pagina della guida descrive come funziona il &quot;Tempo trascorso per visita&quot; come metrica. Per ulteriori informazioni, vedere la dimensione [Tempo trascorso per visita](../dimensions/time-spent-per-visit.md).*

Il valore &quot;Tempo trascorso per visita (secondi)&quot; [metrica](overview.md) mostra il tempo medio di interazione dei visitatori con un dato elemento della dimensione durante ogni visita.

Questa metrica non è disponibile in Data Warehouse a causa della diversa architettura di elaborazione.

## Come è calcolata questa metrica

Questa metrica utilizza la formula [`[Total seconds spent]`](total-seconds-spent.md) `divided by (`[`[Visits]`](visits.md) `minus` [`[Bounces]`](bounces.md)`)`.

## Confronto con il tempo medio sul sito

Questa metrica e il tempo medio [trascorso sul sito](average-time-on-site.md) sono simili, ma presentano diverse differenze chiave. Entrambe le metriche utilizzano il numeratore &quot;Totale secondi trascorsi&quot;. Tuttavia, &quot;Tempo medio sul sito&quot; utilizza le sequenze che includono un elemento dimensione come denominatore. Il tempo trascorso per visita utilizza il conteggio delle visite come denominatore.

Di conseguenza, queste metriche producono risultati simili a livello di visita, ma sono diverse a livello di hit.

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è l’intero tempo trascorso per visita della dimensione e il numeratore è il tempo trascorso per visita dell’elemento dimensionale. Se il tempo trascorso per visita dell’intera dimensione è inferiore al tempo trascorso per visita di un dato elemento dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti classificati per questa metrica mostra il tempo di anomalia trascorso per i valori di visita, che in genere non è prezioso. Adobe consiglia di ordinare i rapporti in base a un&#39;altra metrica, ad esempio [Visite](visits.md).

Consulta [Panoramica sul tempo trascorso](time-spent.md) per informazioni più generali sul tempo trascorso.
