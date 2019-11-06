---
description: nulle
solution: Analytics
title: Tempo trascorso per ciascuna visita
topic: Rapporti
uuid: 76441e36-b7fe-4cf3-8d72-c51d558afa13
translation-type: tm+mt
source-git-commit: 77eac41cdcfe0ad71ffe81525f6de4dc6b2b48d4

---


# Tempo trascorso per ciascuna visita

Adobe Analytics offre diversi modi per determinare il tempo trascorso nei report di Analytics. Nella maggior parte dei casi, il tempo trascorso è calcolato utilizzando i seguenti passaggi:

1. Per una determinata visita, osserva la marca temporale del primo hit.
2. Confronta questo hit con la marca temporale dell’ultimo hit della visita.
3. Il tempo trascorso tra queste due occorrenze determina il tempo trascorso per tale visita.

Quando visualizzi i dati della dimensione del tempo trascorso, tieni presente quanto segue:

* Sia le visualizzazioni di pagina che i tipi di hit di tracciamento dei collegamenti vengono considerati nel calcolo del tempo trascorso.
* Il tempo trascorso non viene misurato durante l’ultimo hit della visita, in quanto non esiste una richiesta immagine successiva per misurare il tempo trascorso.
* I rimbalzi non possono misurare il tempo trascorso, poiché la visita consiste in un singolo hit.

Il tempo trascorso per visita misura il tempo totale trascorso in una visita. Esistono dimensioni separate tra **granulare** e **fisso**.

* **** Granulare: Ogni valore di dimensione è un numero diverso di secondi che compongono una visita.
* **** Esteso: Ogni valore di dimensione è un bucket predefinito:
   * Meno di 1 minuto
   * 1-5 minuti
   * 5-10 minuti
   * 30-60 minuti
   * 1-2 ore
   * 2-5 ore
   * 5-10 ore
   * 10-15 ore
   * 15+ ore

> [!NOTE] Le [visite](../c-metrics/metrics-visit.md) generalmente terminano dopo 12 ore di attività. Tuttavia, le visite possono superare le 12 ore utilizzando hit con marca temporale o origini dati.

Questa dimensione è basata sulle visite. Confronta questa dimensione con il [tempo trascorso sulla pagina](reports-time-spent-on-page.md), che è una dimensione basata sugli hit.
