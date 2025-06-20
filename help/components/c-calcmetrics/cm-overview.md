---
description: Le metriche calcolate e le metriche calcolate avanzate sono metriche personalizzate che puoi creare dalle metriche esistenti.
keywords: Metriche calcolate;Metriche calcolate avanzate
title: Metriche calcolate e metriche calcolate avanzate
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 9714863374052e257e1d6349c442fc74182a0a2f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 37%

---

# Metriche calcolate e metriche calcolate avanzate

Le metriche calcolate e le metriche calcolate avanzate sono metriche personalizzate che puoi creare dalle metriche esistenti.

I nostri strumenti di metriche calcolate offrono un modo altamente flessibile di generare, gestire e curare le metriche. Consentono ad addetti al marketing, product manager e analisti di porre domande sui dati senza dover modificare l&#39;implementazione di [!DNL Analytics]. Le metriche personalizzate disponibili in ciascun pacchetto [!DNL Analytics] sono:

* Adobe [!DNL Analytics] Foundation: calcolato
* [Selezione Adobe Analytics](https://www.adobe.com/it/data-analytics-cloud/analytics/select.html): Calcolato + Avanzato Calcolato
* [Adobe Analytics Prime](https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html): calcolato + Avanzato calcolato
* [Adobe Analytics Ultimate](https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html): calcolato + Avanzato calcolato

Ecco un confronto tra le metriche calcolate e le funzionalità avanzate delle metriche calcolate:

| Opzioni di generazione | Metriche calcolate | Metriche calcolate avanzate |
|---|---|---|
| [Tipi di formato (decimale, ora, percentuale, valuta)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md) | Sì | Sì |
| [Modifiche all&#39;attribuzione (predefinita, lineare, partecipazione, ecc.)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sì | Sì |
| [Tipi di metrica (standard, totale)](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/m-metric-type-alloc.md) | Sì | Sì |
| Operatori di base (sommare, sottrarre, moltiplicare, dividere) | Sì | Sì |
| [Applica segmenti](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md) | No | Sì |
| [Funzioni di base (conteggio, valore assoluto, media, ecc.)](/help/components/c-calcmetrics/cm-reference/cm-functions.md) | No | Sì |
| [Funzioni avanzate (regressione, if/then, t-score, ecc.)](/help/components/c-calcmetrics/cm-reference/cm-adv-functions.md) | No | Sì |

## Funzionalità {#section_A0A5C275B68A4D628950BBB0B1EE631F}

È possibile eseguire le seguenti azioni:

* Creare metriche in [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection] e [!UICONTROL Contribution Analysis].
* Creare metriche segmentate derivate in fase di esecuzione dei rapporti, senza dover modificare l’implementazione. Questi possono essere visualizzati storicamente perché sono basati su segmenti.

>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Metriche calcolate](https://video.tv.adobe.com/v/41662?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

* Condividere le metriche tra le suite di rapporti. Ciò significa che tutte le metriche create di recente si applicano a tutte le suite di rapporti nella stessa società di accesso.
* (Solo per metriche calcolate avanzate) Segmento sulle metriche. Ad esempio, puoi creare una metrica per “Nuovi visitatori”, conteggiando le persone per cui questa è la prima sessione.

* Incorpora funzioni statistiche per descrivere meglio i tuoi dati (solo per metriche calcolate avanzate). Ad esempio, puoi contare il numero di elementi in un rapporto o aggiungere il numero di deviazioni standard per ogni elemento.


## Limitazioni

Alcune funzionalità di [!DNL Analytics] consentono di utilizzare eventi ma non metriche calcolate:

* [!UICONTROL Fallout] in [!UICONTROL Analysis Workspace]
* [!UICONTROL Cohort Analysis] in Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] per [!DNL Target]


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Metriche calcolate](https://video.tv.adobe.com/v/41662?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Per un video dimostrativo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentazione delle metriche calcolate nei segmenti](https://video.tv.adobe.com/v/41661?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](c-workflow/cm-workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->