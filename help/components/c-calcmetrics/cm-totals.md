---
title: Totali delle metriche calcolate
description: Scopri le differenze tra i totali delle metriche calcolate negli strumenti di Analytics.
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 2%

---

# Totali delle metriche calcolate

Differenza tra la visualizzazione dei totali delle metriche calcolate [!DNL Reports & Analytics] e [!DNL Analysis Workspace]. Questa sezione spiega le differenze.

## Totali delle metriche calcolate in [!DNL Reports & Analytics]

Quando visualizzi i rapporti in [!DNL Reports & Analytics], le metriche calcolate vengono sempre visualizzate `n/a` sotto il totale. Poiché tutte le metriche calcolate sono definite dall’utente, in molte circostanze questo totale non ha senso. Prendi in considerazione l’esempio seguente:

La tua organizzazione ha creato la metrica calcolata `orders` / `visits` per determinare la percentuale di visite che hanno acquistato qualcosa sul sito. Se hai introdotto questa metrica in un rapporto sui prodotti, diversi prodotti vengono attribuiti a un unico ordine. E, diversi prodotti sono attribuiti a una singola visita. Se in questo rapporto è stato incluso un totale di metriche calcolate, si pongono le seguenti domande:

| Domanda | Risposta |
|---|---|
| La somma degli elementi della riga ha senso? | Non lo fa, poiché più prodotti possono essere inclusi in un unico ordine e più prodotti possono essere inclusi in una singola visita. Se le voci sono state aggregate, gli ordini totali e le visite totali non corrisponderebbero agli ordini totali effettivi e alle visite totali. |
| È sensato prendere ordini totali e visite totali? | Non lo fa, in quanto il totale non corrisponde alla somma dei singoli elementi della riga. Inoltre, gli ordini totali e le visite totali sono metriche calcolate separatamente. |

Poiché non esiste un metodo logico e concreto per determinare se una metrica calcolata ha senso nel reporting, il totale della metrica viene omesso completamente. Se si desidera ottenere un totale complessivo, è possibile effettuare una delle seguenti operazioni:

* Crea una metrica calcolata che include le versioni totali delle metriche che desideri includere.
* Crea un rapporto di estrazione dati, che può essere pianificato.
* Crea una richiesta di dati in [!DNL ReportBuilder].
* Utilizzo [!DNL Analysis Workspace] (vedi sotto).

## Totali delle metriche calcolate in [!DNL Analysis Workspace]

Quando visualizzi i dati in Analysis Workspace, nella maggior parte dei casi vengono visualizzati i totali delle metriche calcolate. In alcuni casi, non è possibile fornire un totale, ad esempio quando le righe del rapporto sono in formato misto (ad esempio decimale e valuta).

Quando i totali vengono visualizzati, vengono spesso calcolati lato server, il che significa che il totale deduplica le metriche quali visite o visitatori. In determinate circostanze, le metriche calcolate vengono generate lato client sommando tra le righe della tabella, il che significa che il totale non deduplica metriche quali visite o visitatori. Ciò si verifica:

* Quando [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) sono utilizzati nelle tabelle a forma libera e nelle **[!UICONTROL Show as sum of current rows]** (impostazione predefinita) è selezionata.
* In [Visualizzazione Anello](/help/analyze/analysis-workspace/visualizations/donut.md), in modo che i numeri sommino fino al 100%.

Per ulteriori informazioni sui totali in Analysis Workspace, visita [Totali in Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html#static-row-total).
