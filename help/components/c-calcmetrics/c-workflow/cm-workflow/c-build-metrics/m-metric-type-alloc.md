---
description: Scopri
title: Tipo di metrica e attribuzione
feature: Calculated Metrics
exl-id: 3fb98227-e2ef-4829-ae84-812f845470ee
source-git-commit: 21c4d1b591daf7229bd36845e42e2dec473e792f
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 43%

---

# Tipo di metrica e attribuzione {#metric-type-attribution}

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attributionmodel"
>title="Modello"
>abstract="Seleziona un modello di attribuzione per la metrica."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lasttouch"
>title="Ultimo contatto"
>abstract="Il 100% del credito va all’ultimo valore di dimensione visualizzato da un visitatore."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_firsttouch"
>title="Primo contatto"
>abstract="Il 100% del credito va al primo valore di dimensione visualizzato da un visitatore."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_linear"
>title="Lineare"
>abstract="Il credito è distribuito in modo uniforme tra tutti i valori di dimensione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_participation"
>title="Partecipazione"
>abstract="Il 100% del credito va a ogni valore di dimensione visualizzato da un visitatore.<br/>I totali delle colonne sono sovrastimati."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_sametouch"
>title="Stesso contatto"
>abstract="Il credito viene assegnato solo ai valori di dimensione che si verificano nello stesso evento come la conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_instance"
>title="Stesso contatto"
>abstract="Il credito viene assegnato solo ai valori di dimensione che si verificano nello stesso evento come la conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_ushaped"
>title="A forma di U"
>abstract="Il 40% del credito va al primo valore di dimensione, il 40% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jcurve"
>title="Curva J"
>abstract="Il 60% del credito va all’ultimo valore di dimensione, il 20% al primo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_jshaped"
>title="Curva J"
>abstract="Il 60% del credito va all’ultimo valore di dimensione, il 20% al primo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_inversej"
>title="J inversa"
>abstract="Il 60% del credito va al primo valore di dimensione, il 20% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_reversejshaped"
>title="J inversa"
>abstract="Il 60% del credito va al primo valore di dimensione, il 20% all’ultimo, il 20% condiviso dal centro."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_timedecay"
>title="Decadimento nel tempo"
>abstract="Il merito maggiore viene attribuito ai valori di dimensione più vicini nel tempo a una conversione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_custom"
>title="Personalizzato"
>abstract="Definisci una ponderazione di attribuzione basata sulla posizione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_positionbased"
>title="Personalizzato"
>abstract="Definisci una ponderazione di attribuzione basata sulla posizione."

>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_algorithmic"
>title="Algoritmico"
>abstract="Il credito è determinato dinamicamente su un algoritmo statistico."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_container"
>title="Contenitore"
>abstract="Seleziona un contenitore per impostare l’ambito desiderato per l’attribuzione."


>[!CONTEXTUALHELP]
>id="components_calculatedmetrics_attribution_lookbackwindow"
>title="Intervallo di lookback"
>abstract="Questa impostazione determina la finestra di attribuzione dei dati che verrà applicata a per ogni conversione."

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
| EVar di primo contatto | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | PROMOZIONE A | $ 10 |
| Esempio di prop | PROMOZIONE A | - | PROMOZIONE A | PROMOZIONE B | - | PROMOZIONE C | $ 10 |

In questo esempio, i valori A, B e C sono stati inviati in una variabile negli hit 1, 3, 4 e 6 prima che fosse effettuato un acquisto da 10 $ nell’hit 7. Nella seconda riga, tali valori persistono tra gli hit in base alla visita di ultimo contatto. La terza riga illustra la persistenza di una visita di primo contatto. Infine, l’ultima riga illustra come verranno registrati i dati per una proprietà che non ha persistenza.

