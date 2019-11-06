---
description: Adobe Analytics offre diverse metriche e dimensioni Time Spent. Scopri cosa sono e come vengono calcolati.
solution: Analytics
title: Durata
topic: Metriche
translation-type: tm+mt
source-git-commit: ee9a6462138fe3483ca8a4ba042cb4eb39536031

---


# Tempo trascorso metriche

Adobe Analytics offre diversi modi per determinare il tempo trascorso nei report di Analytics. Nella maggior parte dei casi, il tempo trascorso è calcolato utilizzando i seguenti passaggi:

1. Per un dato hit, controlla la marca temporale e il valore della dimensione.
1. Confronta questo hit con la marca temporale dell’hit successivo nella visita.
1. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso per tale valore di dimensione.

Quando visualizzi le metriche relative al tempo trascorso, tieni presente quanto segue:

* Il tempo trascorso prende in considerazione l'allocazione e la scadenza.
* Sia le visualizzazioni di pagina che i tipi di hit di tracciamento dei collegamenti vengono considerati nel calcolo del tempo trascorso.
* Il tempo trascorso non viene misurato durante l’ultimo hit della visita, in quanto non esiste una richiesta immagine successiva per misurare il tempo trascorso.
* I rimbalzi non possono misurare il tempo trascorso, poiché la visita consiste in un singolo hit.

## Totale secondi trascorsi

Il tempo totale in secondi per cui tutti i visitatori hanno interagito con un valore di dimensione.

## Tempo trascorso per visita (secondi)

Il tempo medio di interazione dei visitatori con un valore di dimensione in una visita. Il suo calcolo approssimativo è `Total seconds spent / (Visits - Bounces)`.

## Tempo trascorso per visitatore (secondi)

La quantità media di tempo che i visitatori interagiscono con un valore di dimensione per tutta la durata del visitatore. Il suo calcolo approssimativo è `Total seconds spent / (Unique Visitors - Bounces)`.

## Tempo medio trascorso sul sito (secondi)

Il tempo medio trascorso sul sito con il valore di dimensione specificato. Questa metrica è in genere associata a una dimensione data per mostrare il tempo trascorso nel tempo. Il suo calcolo approssimativo è `Total seconds spent / (Sequences - Bounces)`. Le sequenze sono una serie di hit in cui il valore della dimensione non è stato modificato. Nella maggior parte dei casi, utilizza il tempo trascorso per visita.

## Tempo medio trascorso sulla pagina

Disponibile solo in Generatore di report. Nella maggior parte dei casi, utilizza il tempo trascorso per visita.
