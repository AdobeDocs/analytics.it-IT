---
title: Tempo trascorso per visita
description: Il tempo totale impiegato dalla visita.
translation-type: tm+mt
source-git-commit: 52e00470df0f0c6bff84b26c1548e64ff5114fb8
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 0%

---


# Tempo trascorso per visita

*Questa pagina della guida descrive il funzionamento di &#39;Tempo trascorso per visita&#39; nelle rispettive dimensioni. Per ulteriori informazioni, vedi la metrica[Tempo trascorso per visita](../metrics/time-spent-per-visit.md).*

Le dimensioni &quot;Tempo trascorso per visita&quot; registrano la quantità di tempo trascorso da un visitatore per l’intera visita. Per misurare il calcolo viene utilizzato il seguente passaggio:

1. Osservate la marca temporale del primo hit della visita.
2. Confronta questo hit con la marca temporale dell’ultimo hit della visita.
3. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso.

Queste dimensioni sono utili per comprendere quanto tempo i visitatori interagiscono con il sito in generale.

>[!TIP] Il tempo trascorso richiede almeno due hit in una visita per misurare il tempo. Le visite composte da un singolo hit non vengono visualizzate in questa dimensione.

Questa dimensione è basata sulle visite, il che significa che il valore si applica a ogni hit all’interno della visita e non cambia. Confronta questa dimensione con il [tempo trascorso sulla pagina](time-spent-on-page.md), che è una dimensione basata sugli hit.

Questa dimensione è correlata al tempo [medio trascorso sul sito](../metrics/average-time-on-site.md) e al [tempo trascorso per visita](../metrics/time-spent-per-visit.md) metriche.

## Compilare questa dimensione con i dati

Queste dimensioni funzionano automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, queste dimensioni funzionano.

## Valori dimensione

Esistono più dimensioni per il tempo trascorso per visita:

* **Tempo trascorso per visita - allungato**: Il tempo trascorso è intasato. I valori delle dimensioni variano da `"Less than 1 minute"` a `"More than 15 hours"`. Le visite non durano generalmente più di 12 ore; tuttavia, le visite possono superare le 12 ore se si utilizzano hit con marca temporale o origini dati.
* **Tempo trascorso per visita - granulare**: Ogni numero di secondi è un valore di dimensione univoco. Questa dimensione non è disponibile in Reporting e analisi o Data Warehouse.

Consultate Panoramica sul [tempo trascorso](../metrics/time-spent.md) per informazioni più generali sul tempo trascorso.
