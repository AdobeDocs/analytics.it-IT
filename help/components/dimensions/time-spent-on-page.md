---
title: Tempo trascorso sulla pagina
description: Il tempo trascorso da un visitatore sulla pagina.
feature: Dimensions
exl-id: 55af7286-7c37-48d2-925e-8b7ecb390e7f
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '286'
ht-degree: 4%

---

# Tempo trascorso sulla pagina

La dimensione &quot;Tempo trascorso sulla pagina&quot; registra la quantità di tempo trascorso da un visitatore sulla pagina. Per misurare il calcolo, utilizza i seguenti passaggi:

1. Per un dato hit, osserva la marca temporale.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita. Conteggio degli hit di tracciamento delle visualizzazioni di pagina e dei collegamenti.
3. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso.

Questa dimensione è utile quando desideri capire per quanto tempo i visitatori interagiscono con una data metrica sul tuo sito.

>[!TIP]
>
>Il tempo trascorso non viene misurato per l’ultimo hit della visita, in quanto non esiste una richiesta di immagine successiva per misurare il tempo trascorso. Questo concetto si applica anche alle visite costituite da un singolo hit (un rimbalzo).

Questa dimensione è basata su hit, il che significa che il valore è diverso per ogni hit. Confronta questa dimensione con [Tempo trascorso per visita](time-spent-per-visit.md), che è una dimensione basata sulle visite. Un tempo più lungo trascorso significa che un visitatore è rimasto più a lungo su una pagina (hit).

![Tempo trascorso sulla pagina](../metrics/assets/time-spent2.png)

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Esistono più dimensioni per il tempo trascorso sulla pagina:

* **Tempo trascorso sulla pagina - a blocchi**: Il tempo viene intasato. Intervallo di elementi Dimension `"Less than 15 seconds"` a `"More than 30 minutes"`. Il tempo tra le visualizzazioni di pagina generalmente non dura più di 30 minuti; tuttavia, il tempo tra le visualizzazioni di pagina può superare i 30 minuti se si utilizzano hit con marca temporale o origini dati.
* **Tempo trascorso sulla pagina - granulare**: Ogni numero di secondi è un elemento di dimensione univoco.

Vedi [Panoramica del tempo trascorso](../metrics/time-spent.md) informazioni più generali sul tempo trascorso.
