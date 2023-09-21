---
title: Tempo trascorso sulla pagina
description: La quantità di tempo trascorso da un visitatore sulla pagina.
feature: Dimensions
exl-id: 55af7286-7c37-48d2-925e-8b7ecb390e7f
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 4%

---

# Tempo trascorso sulla pagina

Il &#39;Tempo trascorso sulla pagina&#39; [dimensione](overview.md) registra la quantità di tempo trascorso un visitatore sulla pagina. Per misurare il calcolo, utilizza i passaggi seguenti:

1. Per un dato hit, controlla la marca temporale.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita. Sono conteggiati sia gli hit di visualizzazione pagina che quelli di tracciamento dei collegamenti.
3. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso.

Questa dimensione è utile quando desideri comprendere per quanto tempo i visitatori interagiscono con una determinata metrica sul sito.

>[!TIP]
>
>Il tempo trascorso non viene misurato per l’ultimo hit della visita, in quanto non esiste una successiva richiesta di immagine per misurare il tempo trascorso. Questo concetto si applica anche alle visite consistenti in un singolo hit (un mancato recapito).

Questa dimensione è basata sugli hit, il che significa che il valore è diverso per ogni hit. Confronta questa dimensione con [Tempo trascorso per visita](time-spent-per-visit.md), che è una dimensione basata sulle visite. Maggiore è il tempo trascorso, più un visitatore è rimasto a lungo su una pagina (hit).

![Tempo trascorso sulla pagina](../metrics/assets/time-spent2.png)

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Esistono più dimensioni per il tempo trascorso sulla pagina:

* **Tempo trascorso sulla pagina - a blocchi**: la quantità di tempo è inserita nel bucket. L&#39;intervallo di elementi Dimension è compreso tra `"Less than 15 seconds"` a `"More than 30 minutes"`. Il tempo tra gli hit in genere non dura più di 30 minuti; tuttavia, il tempo tra gli hit può superare i 30 minuti se si utilizzano hit con marca temporale o origini dati.
* **Tempo trascorso sulla pagina - granulare**: ogni numero di secondi è un elemento dimensione univoco.

Consulta [Panoramica sul tempo trascorso](../metrics/time-spent.md) per informazioni più generali sul tempo trascorso.
