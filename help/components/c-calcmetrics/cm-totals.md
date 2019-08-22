---
title: Totali delle metriche calcolate
seo-title: Totali delle metriche calcolate
description: Scopri come i totali delle metriche calcolate differiscono negli strumenti di Analytics
seo-description: Calcolo dei totali delle metriche calcolate
translation-type: tm+mt
source-git-commit: ec3187f1548aa107f03d9abf7ceacb7a4a85abb3

---


# Totali delle metriche calcolate

La modalità di visualizzazione dei totali delle metriche calcolate varia da [!DNL Reports & Analytics] e [!DNL Analysis Workspace]verso. In questa sezione vengono spiegate le differenze.

## Totali delle metriche calcolate in [!DNL Reports & Analytics]

Quando visualizzate i rapporti in [!DNL Reports & Analytics], le metriche calcolate vengono sempre visualizzate `n/a` sotto il totale. Poiché tutte le metriche calcolate sono definite dall'utente, il totale non ha alcun senso. Prendi in considerazione l'esempio seguente:

L'organizzazione ha creato la metrica `orders` calcolata/ `visits` per determinare la percentuale di visite acquistate sul sito. Se hai portato questa metrica in un rapporto sui prodotti, diversi prodotti vengono attribuiti a un singolo ordine. Inoltre, diversi prodotti vengono attribuiti a una singola visita. Se in questo rapporto è stato incluso un totale della metrica calcolata, si verificano le seguenti domande:

| domande | Risposta |
|---|---|
| La descrizione degli elementi della linea ha senso? | In quanto più prodotti possono essere inclusi in un unico ordine e più prodotti possono essere inclusi in una singola visita. Se gli elementi della linea erano aggregati, gli ordini totali e le visite totali non corrispondevano agli ordini totali effettivi e alle visite totali. |
| Prendere ordini totali e visite totali ha senso? | Non in quanto il totale non corrisponde alla somma delle singole righe. Inoltre, ordini totali e visite totali sono metriche calcolate separatamente. |

Poiché non c'è alcun metodo logico e concreto per determinare se una metrica calcolata ha senso nei report, il totale della metrica viene omesso. Se desiderate ottenere un totale complessivo, potete effettuare una delle seguenti operazioni:

* Crea una metrica calcolata che includa le versioni totali delle metriche che desideri includere.
* Creare un rapporto Estrazione dati, che può essere pianificato.
* Creare una richiesta dati all'interno di reportbuilder.
* Usa Analysis Workspace (vedi di seguito).

## Totali delle metriche calcolate in [!DNL Analysis Workspace]

In Analysis Workspace, in alcune circostanze, le metriche calcolate vengono sommate per visualizzare un totale:

* Quando sono presenti righe [statiche](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) nelle tabelle a forma libera e l' *[!UICONTROL Calculate totals by summing the values currently in each column]* opzione (impostazione predefinita) è selezionata.
* Nella visualizzazione [Anello](/help/analyze/analysis-workspace/visualizations/donut.md).
* Nella visualizzazione Modifica [riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md).
