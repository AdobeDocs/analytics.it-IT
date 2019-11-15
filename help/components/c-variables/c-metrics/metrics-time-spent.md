---
description: Adobe Analytics offre diverse metriche e dimensioni Time Spent. Scopri cosa sono e come vengono calcolati.
solution: Analytics
title: Durata
topic: Metrics
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

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

Il tempo medio trascorso sul sito, generalmente associato a una dimensione data. Anche se questa metrica mostra solitamente il tempo trascorso con tendenze nel tempo, può essere utilizzata anche con dimensioni come calcolo alternativo al tempo trascorso per visita. Il suo calcolo approssimativo è `Total seconds spent / (Sequences - Bounces)`. Le sequenze sono una serie di hit in cui il valore della dimensione non è stato modificato.

> [!NOTE] Il tempo trascorso per visita e il tempo medio trascorso sul sito sono metriche simili. La differenza tra queste due metriche è il loro denominatore; il tempo trascorso per visita utilizza `visits - bounces`, mentre il tempo medio trascorso sul sito utilizza `sequences - bounces`. A livello di visita, queste metriche appaiono simili, ma possono presentare alcune differenze a livello di hit.

## Tempo medio trascorso sulla pagina

Disponibile solo in Generatore di report. Nella maggior parte dei casi, utilizza il tempo trascorso per visita.
