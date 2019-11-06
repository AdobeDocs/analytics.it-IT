---
description: Mostra il tempo dedicato dai visitatori alla pagina
solution: Analytics
title: Tempo trascorso nella pagina
topic: Rapporti
translation-type: tm+mt
source-git-commit: 77eac41cdcfe0ad71ffe81525f6de4dc6b2b48d4

---


# Tempo trascorso sulla pagina

Adobe Analytics offre diversi modi per determinare il tempo trascorso nei report di Analytics. Nella maggior parte dei casi, il tempo trascorso è calcolato utilizzando i seguenti passaggi:

1. Per un dato hit, controlla la marca temporale e il valore della dimensione.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita.
3. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso per tale pagina.

Quando visualizzi i dati della dimensione del tempo trascorso, tieni presente quanto segue:

* Il tempo trascorso prende in considerazione l'allocazione e la scadenza.
* Sia le visualizzazioni di pagina che i tipi di hit di tracciamento dei collegamenti vengono considerati nel calcolo del tempo trascorso.
* Il tempo trascorso non viene misurato durante l’ultimo hit della visita, in quanto non esiste una richiesta immagine successiva per misurare il tempo trascorso.
* I rimbalzi non possono misurare il tempo trascorso, poiché la visita consiste in un singolo hit.

Il tempo trascorso sulla pagina misura il tempo trascorso tra gli hit in una visita. Esistono dimensioni separate tra **granulare** e **fisso**.

* **** Granulare: Ogni valore di dimensione è un numero diverso di secondi trascorsi tra due hit.
* **** Esteso: Ogni valore di dimensione è un bucket predefinito:
   * Inferiore a 15 secondi
   * 15-29 secondi
   * Da 1 a 3 minuti
   * Da 3 a 5 minuti
   * Da 5 a 10 minuti
   * da 10 a 15 minuti
   * Da 15 a 20 minuti
   * 20-30 minuti
   * Più di 30 minuti

Questa dimensione è basata sugli hit, che se utilizzata come suddivisione può fornire dati più significativi. Confronta questa dimensione con il [tempo trascorso per visita](reports-time-spent-per-visit.md), una dimensione basata sulle visite.

![Tempo trascorso](assets/time-spent1.png)
