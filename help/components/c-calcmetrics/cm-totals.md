---
title: Totali delle metriche calcolate
description: Scopri le differenze tra i totali delle metriche calcolate negli strumenti di Analytics
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Totali delle metriche calcolate

La modalità di visualizzazione dei totali delle metriche calcolate è diversa tra [!DNL Reports & Analytics] e [!DNL Analysis Workspace]. Questa sezione spiega le differenze.

## Totali delle metriche calcolate in [!DNL Reports & Analytics]

Quando visualizzate i rapporti in [!DNL Reports & Analytics], le metriche calcolate vengono sempre visualizzate `n/a` sotto il totale. Poiché tutte le metriche calcolate sono definite dall'utente, in molti casi questo totale non ha senso. Prendi in considerazione l'esempio seguente:

L'organizzazione ha creato la metrica calcolata `orders` / `visits` per determinare la percentuale di visite che hanno acquistato un elemento sul sito. Se hai inserito questa metrica in un rapporto sui prodotti, diversi prodotti vengono attribuiti a un unico ordine. E, diversi prodotti sono attribuiti a una singola visita. Se in questo rapporto è stato incluso un totale di metriche calcolate, si pongono le seguenti domande:

| Domanda | Risposta |
|---|---|
| Riassumere gli elementi della riga ha senso? | Non è così, poiché più prodotti possono essere inclusi in un unico ordine e più prodotti possono essere inclusi in una singola visita. Se le voci sono state aggregate, gli ordini totali e le visite totali non corrisponderebbero agli ordini totali effettivi e alle visite totali. |
| Assumere ordini totali e visite totali ha senso? | Non è così, poiché il totale non corrisponde alla somma dei singoli elementi di riga. Inoltre, gli ordini totali e le visite totali sono metriche calcolate separatamente. |

Poiché non esiste un metodo logico e concreto per determinare se una metrica calcolata ha senso nel reporting, il totale della metrica viene omesso completamente. Per ottenere un totale complessivo, potete effettuare una delle seguenti operazioni:

* Crea una metrica calcolata che include le versioni totali delle metriche da includere.
* Crea un rapporto di estrazione dati, che può essere pianificato.
* Create a data request within [!DNL ReportBuilder].
* Usa [!DNL Analysis Workspace] (vedi sotto).

## Totali delle metriche calcolate in [!DNL Analysis Workspace]

Quando visualizzate i dati in Analysis Workspace, nella maggior parte dei casi vengono visualizzati i totali delle metriche calcolate. In alcuni casi, non è possibile specificare un totale, ad esempio quando le righe del rapporto sono in un formato misto (ad esempio, decimale e valuta).

Quando i totali vengono visualizzati, sono spesso calcolati sul lato server, il che significa che il totale deduplica le metriche come visite o visitatori. In alcune circostanze, le metriche calcolate vengono generate sul lato client, sommando le righe della tabella, il che significa che il totale non deduplica le metriche come visite o visitatori. Ciò si verifica:

* Quando si utilizzano righe [](/help/analyze/analysis-workspace/build-workspace-project/column-row-settings/manual-vs-dynamic-rows.md) statiche nelle tabelle a forma libera e l' **[!UICONTROL Show as sum of current rows]** opzione (predefinita) è selezionata.
* Nella visualizzazione [Anello](/help/analyze/analysis-workspace/visualizations/donut.md), i numeri possono raggiungere il 100%.
