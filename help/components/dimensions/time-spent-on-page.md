---
title: Tempo trascorso sulla pagina
description: La quantità di tempo trascorso da un visitatore sulla pagina.
feature: Dimensions
exl-id: 55af7286-7c37-48d2-925e-8b7ecb390e7f
TQID: https://experienceleague.adobe.com/2WS7gBdkpaYUvVqgoR5QTrPes2T2GJT5AEFyj9POcHA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 289
ht-degree: 13%

---

# Tempo trascorso sulla pagina

La dimensione &#39;Tempo trascorso sulla pagina&#39; [dimension](overview.md) registra il tempo trascorso da un visitatore sulla pagina. Per misurare il calcolo, utilizza i passaggi seguenti:

1. Per un dato hit, controlla la marca temporale.
2. Confronta questo hit con la marca temporale dell’hit successivo nella visita. Sono conteggiati sia gli hit di visualizzazione pagina che quelli di tracciamento dei collegamenti.
3. Il tempo trascorso tra questi due hit contribuisce al tempo trascorso.

Questa dimensione è utile quando desideri comprendere per quanto tempo i visitatori interagiscono con una determinata metrica sul sito.

>[!TIP]
>
>Il tempo trascorso non viene misurato per l’ultimo hit della visita, in quanto non esiste una successiva richiesta di immagine per misurare il tempo trascorso. Questo concetto si applica anche alle visite consistenti in un singolo hit (un mancato recapito).

Questa dimensione è basata sugli hit, il che significa che il valore è diverso per ogni hit. Confronta questa dimensione con [Tempo trascorso per visita](time-spent-per-visit.md), che è una dimensione basata sulle visite. Maggiore è il tempo trascorso, più un visitatore è rimasto a lungo su una pagina (hit).

![Tempo trascorso sulla pagina](../metrics/assets/time-spent2.png)

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Esistono più dimensioni per il tempo trascorso sulla pagina:

* **Tempo trascorso sulla pagina - a blocchi**: la quantità di tempo è a blocchi. Gli elementi di Dimension sono compresi tra `"Less than 15 seconds"` e `"More than 30 minutes"`. Il tempo tra gli hit in genere non dura più di 30 minuti; tuttavia, il tempo tra gli hit può superare i 30 minuti se si utilizzano hit con marca temporale o origini dati.
* **Tempo trascorso sulla pagina - granulare**: ogni numero di secondi è un elemento dimensione univoco.

Consulta [Panoramica sul tempo trascorso](../metrics/time-spent.md) per informazioni più generali sul tempo trascorso.
