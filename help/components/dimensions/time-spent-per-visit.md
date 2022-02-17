---
title: Tempo trascorso per visita
description: Il tempo totale impiegato dalla visita.
feature: Dimensions
exl-id: f241eb2d-7e22-47ee-ade8-8aeb7b2b9694
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 2%

---

# Tempo trascorso per visita

*Questa pagina di aiuto descrive il funzionamento di &quot;Tempo trascorso per visita&quot; nelle rispettive dimensioni. Consulta la sezione [Tempo trascorso per visita](../metrics/time-spent-per-visit.md) per ulteriori informazioni.*

Le dimensioni &quot;Tempo trascorso per visita&quot; registrano la quantità di tempo trascorso da un visitatore per l’intera visita. Per misurare il calcolo, utilizza i seguenti passaggi:

1. Osserva la marca temporale del primo hit della visita.
2. Confronta questo hit con la marca temporale dell’ultimo hit della visita.
3. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso.

Queste dimensioni sono utili per comprendere quanto tempo i visitatori interagiscono con il tuo sito in generale.

>[!TIP]
>
>Il tempo trascorso richiede almeno due hit in una visita per misurare il tempo. Le visite costituite da un singolo hit non vengono visualizzate in questa dimensione.

Questa dimensione è basata sulle visite, il che significa che il valore si applica a ogni hit all’interno della visita e non cambia. Confronta questa dimensione con [Tempo trascorso sulla pagina](time-spent-on-page.md), che è una dimensione basata su hit.

Questa dimensione è correlata al [Tempo medio trascorso sul sito](../metrics/average-time-on-site.md) e [Tempo trascorso per visita](../metrics/time-spent-per-visit.md) metriche.

## Popolare questa dimensione con i dati

Queste dimensioni funzionano automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, queste dimensioni funzionano.

## Elementi Dimension

Esistono più dimensioni per il tempo trascorso per visita:

* **Tempo trascorso per visita - a blocchi**: Il tempo viene intasato. Intervallo di elementi Dimension `"Less than 1 minute"` a `"More than 15 hours"`. Le visite generalmente non durano più di 12 ore; tuttavia, le visite possono superare le 12 ore utilizzando hit con marca temporale o origini dati.
* **Tempo trascorso per visita - granulare**: Ogni numero di secondi è un elemento di dimensione univoco. Questa dimensione non è disponibile in Reports &amp; Analytics o Data Warehouse.

Vedi [Panoramica del tempo trascorso](../metrics/time-spent.md) informazioni più generali sul tempo trascorso.
