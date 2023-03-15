---
title: Totali delle metriche calcolate
description: Scopri le differenze tra i totali delle metriche calcolate negli strumenti di Analytics
feature: Calculated Metrics
exl-id: 3e4429de-3e0c-49a5-b32c-3a4d24a29816
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 2%

---

# Totali delle metriche calcolate

La modalità di visualizzazione dei totali delle metriche calcolate differisce tra [!DNL Reports & Analytics] e [!DNL Analysis Workspace]. Questa sezione spiega le differenze.

## Totali delle metriche calcolate in [!DNL Reports & Analytics]

Quando visualizzi i rapporti in [!DNL Reports & Analytics], le metriche calcolate vengono sempre visualizzate `n/a` sotto il totale. Poiché tutte le metriche calcolate sono definite dall’utente, ci sono molte circostanze in cui questo totale non ha senso. Prendi in considerazione l’esempio seguente:

La tua organizzazione ha creato la metrica calcolata `orders` / `visits` per determinare la percentuale di visite che hanno acquistato qualcosa sul sito. Se hai inserito questa metrica in un rapporto prodotti, diversi prodotti vengono attribuiti a un singolo ordine. Inoltre, diversi prodotti sono attribuiti a una singola visita. Se un totale metrico calcolato è stato incluso in questo rapporto, si pongono le seguenti domande:

| Domanda | Risposta |
|---|---|
| La somma degli elementi della riga ha senso? | Non è così, poiché è possibile includere più prodotti in un singolo ordine e più prodotti in una singola visita. Se le voci di riga sono state aggregate, gli ordini totali e le visite totali non corrisponderebbero agli ordini totali effettivi e alle visite totali. |
| Ha senso prendere ordini totali e visite totali? | Non lo fa, in quanto il totale non corrisponde alla somma dei singoli elementi. Inoltre, gli ordini totali e le visite totali sono metriche calcolate separatamente. |

Poiché non esiste un metodo logico e concreto per determinare se una metrica calcolata abbia senso nel reporting, il totale della metrica viene completamente omesso. Se si desidera ottenere un totale complessivo, è possibile effettuare una delle seguenti operazioni:

* Crea una metrica calcolata che includa le versioni totali delle metriche che desideri includere.
* Crea un rapporto di estrazione dati che può essere pianificato.
* Creare una richiesta di dati in [!DNL ReportBuilder].
* Utilizzare [!DNL Analysis Workspace] (vedi sotto).

## Totali delle metriche calcolate in [!DNL Analysis Workspace]

Nella maggior parte dei casi, quando visualizzi i dati in Analysis Workspace, vengono visualizzati i totali delle metriche calcolate. In alcuni casi non è possibile fornire un totale, ad esempio quando le righe del rapporto sono in formato misto (ad esempio decimale e valuta).

Quando vengono visualizzati i totali, questi vengono spesso calcolati lato server, il che significa che il totale deduplica metriche quali visite o visitatori. In alcune circostanze, le metriche calcolate vengono generate lato client sommando tra le righe della tabella, il che significa che il totale non deduplica metriche quali visite o visitatori. Ciò si verifica:

* Quando [righe statiche](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md) sono utilizzati nelle tabelle a forma libera e **[!UICONTROL Show as sum of current rows]** (impostazione predefinita) è selezionata.
* In [Visualizzazione ad anello](/help/analyze/analysis-workspace/visualizations/donut.md), in modo che i numeri arrivino al 100%.

Per ulteriori informazioni sui totali in Analysis Workspace, visita [Totali in Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.html#static-row-total).
