---
title: Tempo trascorso per visita (dimensioni)
description: Quantità totale di tempo impiegata per la visita.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 3%

---

# Tempo trascorso per visita

*In questa pagina della guida viene descritto il funzionamento di &#39;Tempo trascorso per visita&#39; come le rispettive [dimensioni](overview.md). Per ulteriori informazioni, vedere la metrica [Tempo trascorso per visita](../metrics/time-spent-per-visit.md).*

Le dimensioni &quot;Tempo trascorso per visita&quot; registrano il tempo trascorso da un visitatore per l’intera visita. Per misurare il calcolo, utilizza i passaggi seguenti:

1. Osserva la marca temporale del primo hit della visita.
2. Confronta questo hit con la marca temporale dell’ultimo hit della visita.
3. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso.

Queste dimensioni sono utili per comprendere per quanto tempo i visitatori interagiscono con il sito in generale.

>[!TIP]
>
>Il tempo trascorso richiede almeno due hit in una visita per misurare il tempo. Le visite costituite da un singolo hit non vengono visualizzate in questa dimensione.

Questa dimensione è basata sulle visite, il che significa che il valore si applica a ogni hit all’interno della visita e non cambia. Confronta questa dimensione con [Tempo trascorso sulla pagina](time-spent-on-page.md), che è una dimensione basata sugli hit.

Questa dimensione è correlata alle metriche [Tempo medio trascorso sul sito](../metrics/average-time-on-site.md) e [Tempo trascorso per visita](../metrics/time-spent-per-visit.md).

## Popolare questa dimensione con i dati

Queste dimensioni funzionano in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, queste dimensioni funzionano.

## Elementi dimensionali

Esistono più dimensioni per il tempo trascorso per visita:

* **Tempo trascorso per visita - a blocchi**: la quantità di tempo è a blocchi. Gli elementi di Dimension sono compresi tra `"Less than 1 minute"` e `"More than 15 hours"`. Le visite in genere non durano più di 12 ore; tuttavia, le visite possono superare le 12 ore se si utilizzano hit con marca temporale o origini dati.
* **Tempo trascorso per visita - granulare**: ogni numero di secondi è un elemento dimensione univoco. Dimensione non disponibile in Data Warehouse.

Consulta [Panoramica sul tempo trascorso](../metrics/time-spent.md) per informazioni più generali sul tempo trascorso.
