---
description: Informazioni sulle metriche calcolate che puoi creare da metriche esistenti.
keywords: Metriche calcolate
title: Panoramica sulle metriche calcolate
feature: Calculated Metrics
exl-id: 9bf8239f-cf74-4feb-85e5-d47805e90afb
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 40%

---

# Panoramica delle metriche calcolate

I calcoli sono metriche personalizzate che puoi creare dalle metriche esistenti.

Le metriche calcolate sono metriche personalizzate che puoi creare dalle metriche esistenti. Le metriche calcolate offrono un modo flessibile di generare, gestire e curare metriche personalizzate che consentono di analizzare i dati senza dover modificare l’implementazione.

Le metriche calcolate sono disponibili in ciascun pacchetto [!DNL Analytics], tuttavia Adobe Analytics Foundation Pack per Experience Cloud è limitato alle metriche calcolate di base che includono [tipi di formato (decimale, ora, percentuale, valuta)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md), [modifiche di allocazione (predefinita, lineare, partecipazione, ecc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md), [tipi di metrica (standard, totale)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md) e [operatori di base](workflow/c-build-metrics/cm-build-metrics.md#operators) (aggiungere, sottrarre, moltiplicare e dividere).


Per ulteriori informazioni, vedere [Descrizione del prodotto Adobe Analytics](https://helpx.adobe.com/it/legal/product-descriptions/adobe-analytics.html).

<!--
Here is a comparison of calculated metrics and advanced calculated metrics capabilities: 

| [Format types (decimal, time, percent, currency)](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Attribution changes (default, linear, participation, etc.)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Metric types (standard, total)](/help/components/calculated-metrics/workflow/c-build-metrics/m-metric-type-alloc.md)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
|  Basic operators (add, subtract, multiply, divide)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  | ![CheckmarkCircle](/help/assets/icons/CheckmarkCircle.svg)  |
| [Apply segments](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md)  | ![StopCircle](/help/assets/icons/StopCircle.svg)  | Yes  |
| [Basic functions (count, abs value, mean, etc)](/help/components/calculated-metrics/cm-reference/cm-functions.md)  | No  | Yes  |
| [Advanced functions (regression, if/then, t-score, etc)](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md)  | No  | Yes  |

-->

## Funzionalità {#section_A0A5C275B68A4D628950BBB0B1EE631F}

È possibile eseguire le seguenti azioni:

* [Crea metriche](/help/components/calculated-metrics/workflow/cm-workflow.md) in [!UICONTROL Analysis Workspace], [!UICONTROL Report Builder], [!UICONTROL Anomaly Detection] e [!UICONTROL Contribution Analysis].
* [Creare metriche segmentate](/help/components/calculated-metrics/workflow/c-build-metrics/metrics-with-segments.md) derivate in fase di esecuzione dei report, senza dover modificare l&#39;implementazione. Ad esempio, puoi creare una metrica per *Nuovi visitatori*, conteggiando le persone per le quali questa è la prima sessione.

* [Condividere le metriche](/help/components/calculated-metrics/workflow/cm-sharing.md) tra le suite di rapporti. Ciò significa che tutte le metriche create di recente si applicano a tutte le suite di rapporti nella stessa società di accesso.

* [Incorpora funzioni statistiche](/help/components/calculated-metrics/cm-reference/cm-adv-functions.md) per descrivere meglio i tuoi dati. Ad esempio, puoi contare il numero di elementi in un rapporto o aggiungere il numero di deviazioni standard per ogni elemento.

## Limitazioni

Alcune funzionalità di [!DNL Analytics] non consentono l&#39;utilizzo di metriche calcolate:

* [!UICONTROL Fallout] in [!UICONTROL Analysis Workspace]
* [!UICONTROL Cohort Analysis] in Analysis Workspace
* [!UICONTROL Data Warehouse]
* [!UICONTROL Segments]
* [!DNL Analytics] per [!DNL Target]


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Metriche calcolate](https://video.tv.adobe.com/v/25407?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Per un video dimostrativo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Segmentazione delle metriche calcolate nei segmenti](https://video.tv.adobe.com/v/25409?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]

<!--

Here is a short overview of the [!UICONTROL Calculated metrics] tools: 

|Tool|Capabilities|
|--- |--- |
| [Calculated metric builder](workflow/c-build-metrics/cm-build-metrics.md)| The capabilities are: <ul><li>Create calculated and advanced calculated metrics using advancmd allocation models.</li><li>Add segments inline to metric formulas</li><li>Compare segments in the same report. For example, compare local visitors vs. international visitors.</li><li>Use statistical functions</li><li>Provide detailed metric descriptions (show what it does, where to use it, where NOT to use it)</li><li>Copy definitions into new metrics</li><li>Provide an inline metric preview</li><li>Set metric polarity, which indicates whether it's good or bad if a given custom event (metric) goes up</li><li>Tag metrics</li></ul>|
|Calculated Metric Manager|<ul><li>Share metrics with others</li<li>Approve and curate metrics</li><li>Organize (tag) your metrics so people can find them</li><li>Delete metrics</li><li>Rename metrics</li></ul>|
|Metric Selector rail|Lets you search for and add/apply metrics to the report. You can also change the  sort order (options are: alphabetical, recommended, frequently used, recently used.) In addition, you can filter on Report Suites to show only metrics created in a specific report suite.  To access this Metric Selector, click the Metrics icon  to the left of a report. |
|API for Calculated Metrics|Part of the Adobe Analytics 2.0 API set.|

-->

>[!MORELIKETHIS]
>
>[Crea metriche](/help/components/calculated-metrics/workflow/cm-workflow.md)
>>[Genera metriche](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md)
>>[Usa funzioni](/help/components/calculated-metrics/workflow/c-build-metrics/cm-using-functions.md)
>
