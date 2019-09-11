---
title: Totali delle metriche calcolate
seo-title: Totali delle metriche calcolate
description: Scopri come i totali delle metriche calcolate differiscono negli strumenti di Analytics
seo-description: Calcolo dei totali delle metriche calcolate
translation-type: tm+mt
source-git-commit: 658925799c530b46ff7b56d5d0685af6d9fef1b8

---


# Totali delle metriche calcolate

La modalità di visualizzazione dei totali delle metriche calcolate varia da [!DNL Reports & Analytics] e [!DNL Analysis Workspace]verso. In questa sezione vengono spiegate le differenze.

## Totali delle metriche calcolate in [!DNL Reports & Analytics]

Quando visualizzate i rapporti in [!DNL Reports & Analytics], le metriche calcolate vengono sempre visualizzate `n/a` sotto il totale. Poiché tutte le metriche calcolate sono definite dall'utente, il totale non ha alcun senso. Prendi in considerazione l'esempio seguente:

L'organizzazione ha creato la metrica `orders` calcolata/ `visits` per determinare la percentuale di visite acquistate sul sito. Se hai portato questa metrica in un rapporto sui prodotti, diversi prodotti vengono attribuiti a un singolo ordine. Inoltre, diversi prodotti vengono attribuiti a una singola visita. Se in questo rapporto è stato incluso un totale della metrica calcolata, si verificano le seguenti domande:

| Domanda | Risposta |
|---|---|
| La descrizione degli elementi della linea ha senso? | In quanto più prodotti possono essere inclusi in un unico ordine e più prodotti possono essere inclusi in una singola visita. Se gli elementi della linea erano aggregati, gli ordini totali e le visite totali non corrispondevano agli ordini totali effettivi e alle visite totali. |
| Prendere ordini totali e visite totali ha senso? | Non in quanto il totale non corrisponde alla somma delle singole righe. Inoltre, ordini totali e visite totali sono metriche calcolate separatamente. |

Poiché non c'è alcun metodo logico e concreto per determinare se una metrica calcolata ha senso nei report, il totale della metrica viene omesso. Se desiderate ottenere un totale complessivo, potete effettuare una delle seguenti operazioni:

* Crea una metrica calcolata che includa le versioni totali delle metriche che desideri includere.
* Creare un rapporto Estrazione dati, che può essere pianificato.
* Create a data request within [!DNL ReportBuilder].
* Uso [!DNL Analysis Workspace] (vedere di seguito).

## Totali delle metriche calcolate in [!DNL Analysis Workspace]

Quando visualizzate i dati in Analysis Workspace, nella maggior parte dei casi vengono visualizzati i totali delle metriche calcolate. In alcuni casi, non è possibile fornire un totale, ad esempio quando le righe del rapporto sono di formato misto (ad es. decimale e valuta).

Quando vengono visualizzati i totali, questi sono spesso calcolati su lato server, il che significa che il totale duplica metriche come visite o visitatori. In determinate circostanze, le metriche calcolate vengono generate sul lato client, sommando tra le righe della tabella, il che significa che il totale non duplica metriche come visite o visitatori. Ciò si verifica:

* Quando [sono utilizzate righe](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) statiche nelle tabelle a forma libera e l' **[!UICONTROL Show as sum of current rows]** opzione (impostazione predefinita) è selezionata.
* Nella visualizzazione [Anello](/help/analyze/analysis-workspace/visualizations/donut.md), in modo che i numeri superino il 100%.
