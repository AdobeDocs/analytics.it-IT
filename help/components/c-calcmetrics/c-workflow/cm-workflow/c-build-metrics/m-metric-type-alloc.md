---
description: Scopri
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 7722a2f01ff77dfec8ce110fd04fe977f6c627c6
workflow-type: tm+mt
source-wordcount: '466'
ht-degree: 4%

---

# Tipo di metrica e attribuzione

Quando [creazione di una metrica calcolata](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), puoi specificare il tipo di metrica e il modello di attribuzione.

## Tipo di metrica

Per specificare il tipo di metrica durante la creazione di una metrica calcolata:

1. Seleziona l’icona a forma di ingranaggio accanto alla metrica di cui desideri selezionare il tipo.

   ![](assets/cm_type_alloc.png)

1. Scegli tra le seguenti opzioni:

   | Tipi di metriche | Definizione |
   |---|---|
   | Standard | Queste metriche sono le stesse utilizzate in Standard [!DNL Analytics] reportistica. Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singola riga. Ad esempio: [Ordini] / [Visite] prende ordini per quella voce specifica e lo divide per il numero di visite per quella voce specifica. |
   | Totale complessivo | Utilizza il totale complessivo per il periodo di reporting in ogni voce di riga. Se una formula è costituita da una singola metrica Totale complessivo, visualizza lo stesso numero totale su ogni riga. Le metriche del totale complessivo sono utili per creare metriche calcolate che si confrontano con i dati totali del sito. Ad esempio: [Ordini] / [Visite totali] mostra la proporzione di ordini rispetto a TUTTE le visite al sito, non solo le visite alla voce specifica. |

## Come funziona l’allocazione lineare

[Attribution IQ](/help/analyze/analysis-workspace/attribution/overview.md) è la modalità di valutazione dei modelli di allocazione nelle metriche calcolate.

Per un elenco completo dei modelli di attribuzione e degli intervalli di lookback non predefiniti supportati, consulta [Modelli di attribuzione e intervalli di lookback](/help/analyze/analysis-workspace/attribution/models.md).

L’esempio seguente illustra il funzionamento delle metriche calcolate con allocazioni lineari nel reporting:

|  | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Dati inviati in | PROMOZIONE A | - | PROMOZIONE A | PROMOZIONE B | - | PROMOZIONE C | $10 |
| EVar ultimo contatto | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE B | PROMOZIONE B | PROMOZIONE C | $10 |
| EVar primo contatto | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | $10 |
| Esempio di prop | PROMOZIONE A | - | PROMOZIONE A | PROMOZIONE B | - | PROMOZIONE C | $10 |

In questo esempio, i valori A, B e C sono stati inviati in una variabile negli hit 1, 3, 4 e 6 prima che fosse effettuato un acquisto da 10 $ nell’hit 7. Nella seconda riga, tali valori persistono tra gli hit in base alla visita di ultimo contatto. La terza riga illustra la persistenza di una visita di primo contatto. Infine, l’ultima riga illustra come verranno registrati i dati per una proprietà che non ha persistenza.

## Differenze nel funzionamento dell’allocazione lineare in Reports &amp; Analytics rispetto a Workspace

Esistono alcune differenze nel funzionamento dell’attribuzione lineare tra questi due strumenti:

* In Reports &amp; Analytics, l’attribuzione lineare (elaborata) è sempre basata sulle visite, mentre in Workspace può essere basata sulle visite o sui visitatori.
* In Reports &amp; Analytics, se non veniva passato alcun valore al primo hit di una visita, il valore (iniziale) persisteva dalla visita precedente. Questo NON avviene in Workspace (Attribution IQ). Se non viene passato alcun valore al primo hit di una visita, allora &quot;Nessuno&quot; è il valore iniziale.
