---
description: Scopri
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 8%

---

# Tipo di metrica e attribuzione

Quando [si crea una metrica calcolata](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md), è possibile specificare il tipo di metrica e il modello di attribuzione.

## Tipo di metrica

Per specificare il tipo di metrica durante la creazione di una metrica calcolata:

1. Seleziona l’icona a forma di ingranaggio accanto alla metrica di cui desideri selezionare il tipo.

   ![](assets/cm_type_alloc.png)

1. Scegli tra le seguenti opzioni:

   | Tipi di metriche | Definizione |
   |---|---|
   | Standard | Queste metriche sono le stesse utilizzate nel reporting standard di [!DNL Analytics]. Se una formula è costituita da una singola metrica standard, visualizza dati identici alla sua controparte metrica non calcolata. Le metriche standard sono utili per creare metriche calcolate specifiche per ogni singola riga. Ad esempio, [Ordini] / [Visite] prende ordini per quella riga specifica e lo divide per il numero di visite per quella riga specifica. |
   | Totale complessivo | Utilizza il totale complessivo per il periodo di reporting in ogni voce di riga. Se una formula è costituita da una singola metrica Totale complessivo, visualizza lo stesso numero totale su ogni riga. Le metriche del totale complessivo sono utili per creare metriche calcolate che si confrontano con i dati totali del sito. Ad esempio, [Ordini] / [Visite totali] mostra la proporzione di ordini rispetto a TUTTE le visite al sito, non solo le visite all&#39;elemento di riga specifico. |

## Come funziona l’allocazione lineare

[Attribuzione](/help/analyze/analysis-workspace/attribution/overview.md) è il modo in cui vengono valutati i modelli di allocazione nelle metriche calcolate.

Per un elenco completo dei modelli di attribuzione e degli intervalli di lookback non predefiniti supportati, consulta [Modelli di attribuzione e intervalli di lookback](/help/analyze/analysis-workspace/attribution/models.md).

L’esempio seguente illustra il funzionamento delle metriche calcolate con allocazioni lineari nel reporting:

| | Hit 1 | Hit 2 | Hit 3 | Hit 4 | Hit 5 | Hit 6 | Hit 7 |
|--- |--- |--- |--- |--- |--- |--- |--- |
| Dati inviati in | PROMOZIONE A | - | PROMOZIONE A | PROMOZIONE B | - | PROMOZIONE C | $ 10 |
| EVar ultimo contatto | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE B | PROMOZIONE B | PROMOZIONE C | $ 10 |
| EVar primo contatto | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | $ 10 |
| Esempio di prop | PROMOZIONE A | - | PROMOZIONE A | PROMOZIONE B | - | PROMOZIONE C | $ 10 |

In questo esempio, i valori A, B e C sono stati inviati in una variabile negli hit 1, 3, 4 e 6 prima che fosse effettuato un acquisto da 10 $ nell’hit 7. Nella seconda riga, tali valori persistono tra gli hit in base alla visita di ultimo contatto. La terza riga illustra la persistenza di una visita di primo contatto. Infine, l’ultima riga illustra come verranno registrati i dati per una proprietà che non ha persistenza.

