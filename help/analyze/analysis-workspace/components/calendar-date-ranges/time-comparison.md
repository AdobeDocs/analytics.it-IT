---
description: Scopri come utilizzare il confronto delle date in Analysis Workspace, che consente di prendere una qualsiasi colonna contenente un intervallo di date e creare un confronto tra date comune.
title: Confronto delle date
feature: Date Ranges
role: User, Admin
exl-id: ea7a42ef-89de-4f70-b468-8a5cf69fea05
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 11%

---

# Confronto delle date

Il confronto delle date in Analysis Workspace consente di prendere una qualsiasi colonna contenente un intervallo di date e di creare un confronto tra date comune, ad esempio: anno su anno, trimestre su trimestre, mese su mese, ecc.

## Confronto tra periodi temporali

L’analisi richiede contesto e spesso tale contesto viene fornito da un periodo di tempo precedente. Ad esempio, la domanda *Quanto stai facendo meglio o peggio rispetto a questo periodo dell&#39;anno scorso?* è fondamentale per comprendere la tua attività. Il confronto delle date include automaticamente una colonna *differenza* che mostra la variazione percentuale rispetto a un periodo di tempo specificato.

1. Crea una [tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md), con tutte le dimensioni e le metriche che desideri confrontare in un periodo di tempo.
1. Imposta il periodo di tempo sul pannello o sulla colonna per determinare l’intervallo di tempo del confronto e se si tratta di un confronto in tempo continuo o fisso.

   Per creare un confronto continuo dei tempi, impostare l&#39;intervallo di date del pannello o della colonna su un intervallo di date continuo, ad esempio **[!UICONTROL Last 7 days]**, **[!UICONTROL Last 30 days]** e così via.

   Per creare un confronto a tempo fisso, imposta il pannello o l’intervallo di date della colonna su un intervallo di date personalizzato.
1. Aprire il menu di scelta rapida per una riga di tabella e selezionare **[!UICONTROL Compare time periods]**.

   ![Riga di tabella con periodi di tempo di confronto selezionati](assets/compare-time.png)

   >[!NOTE]
   >
   >Questa opzione del menu di scelta rapida è disabilitata per le righe di metrica, di intervallo di date e di dimensione temporale.

1. A seconda di come è stato impostato l’intervallo di date della tabella, sono disponibili le seguenti opzioni per il confronto:

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Prior *x *settimane/mesi/trimestri/anni a questo intervallo di date]** | Confronta con l’intervallo di date selezionato immediatamente prima di questo intervallo di date. |
   | **[!UICONTROL These x weeks / months / quarters / years last year to this date range]** | Confronta con lo stesso intervallo di date di un anno fa. |
   | **[!UICONTROL Custom date range to this date range]** | Consente di definire un intervallo di date personalizzato. |

   >[!NOTE]
   >
   >Quando selezioni un numero di giorni personalizzato, ad esempio 7 ottobre - 20 ottobre (un intervallo di 14 giorni) avrai a disposizione solo 2 opzioni: **[!UICONTROL Prior 14 days before this date range]** (14 giorni precedenti a questo intervallo di dati) e **[!UICONTROL Custom date range to this date range]** (Seleziona intervallo).

1. Il confronto risultante sarà simile al seguente:

   ![Tabella a forma libera che mostra un confronto tra intervalli di date e variazioni percentuali.](assets/compare-time-result.png)

   Le righe della colonna Variazione percentuale vengono visualizzate in rosso per i valori negativi e in verde per i valori positivi.

## Aggiungere una colonna Periodo di tempo per il confronto

È ora possibile aggiungere a ogni colonna di una tabella un periodo di tempo diverso da quello impostato nel calendario.

1. Fare clic con il pulsante destro del mouse su una colonna della tabella e selezionare **[!UICONTROL Add time period column]**.

   ![](assets/add-time-period-column.png)

1. A seconda di come è stato impostato l’intervallo di date della tabella, sono disponibili le seguenti opzioni per il confronto:

   | Opzione | Descrizione |
   |---|---|
   | **[!UICONTROL Prior *x *settimane/mesi/trimestri/anni a questo intervallo di date]** | Aggiungi una colonna con settimana/mese/ecc. immediatamente prima di questo intervallo di date. |
   | **[!UICONTROL These *x *settimane/mesi/trimestri/anni ultimo anno a questo intervallo di date]** | Aggiungi lo stesso intervallo di date un anno fa. |
   | **[!UICONTROL Custom date range to this date range]** | Consentono di creare un intervallo di date personalizzato. |

   >[!NOTE]
   >
   >Quando selezioni un numero di giorni personalizzato, ad esempio 7 ottobre - 20 ottobre (un intervallo di 14 giorni) avrai a disposizione solo 2 opzioni: **[!UICONTROL Prior 14 days before this date range]** (14 giorni precedenti a questo intervallo di dati) e **[!UICONTROL Custom date range to this date range]** (Seleziona intervallo).

1. Il periodo di tempo viene inserito sopra la colonna selezionata:

   ![Tabella a forma libera che mostra le occorrenze per il periodo di calendario corrente e il mese di calendario precedente.](assets/add-time-period-column2.png)

1. Puoi aggiungere tutte le colonne di tempo desiderate, nonché combinare e abbinare diversi intervalli di date:

1. Inoltre, è possibile ordinare in base a ciascuna colonna, cambiando l&#39;ordine dei giorni a seconda della colonna in cui si esegue l&#39;ordinamento.

## Allineare le date della colonna affinché inizino sulla stessa riga

Puoi allineare le date di ogni colonna affinché inizino tutte sulla stessa riga.

Ad esempio, effettui un confronto giorno dopo giorno per l’ultima settimana (che termina il 5 ottobre 2024) e la settimana precedente. Per impostazione predefinita, la colonna a sinistra inizia il 22 settembre e la colonna a destra il 29 settembre.

![Date non allineate](assets/not-align-dates.png)

È possibile abilitare **[!UICONTROL Align dates from each column to all start on the same row]** in [Impostazioni](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md#settings-1) affinché la visualizzazione a forma libera allinei le date delle colonne affinché inizino sulla stessa riga.

![](assets/align-dates.png)

Quando utilizzi questa opzione, tieni presente quanto segue:

* Questa impostazione è attivata per impostazione predefinita per tutti i nuovi progetti.

* Questa impostazione si applica all&#39;intera tabella. Ad esempio, se modifichi questa impostazione per un raggruppamento all’interno della tabella, l’impostazione viene applicata all’intera tabella.


<!--
# Date comparison

Date comparison in Analysis Workspace lets you take any column containing a date range and create a common date comparison, such as: year-over-year, quarter-over-quarter, month-over-month, etc.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Date comparison](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-date-ranges-and-comparisons-in-analysis-workspace){target="_blank"} for a demo video.

>[!ENDSHADEBOX]



## Compare time periods {#section_C4E36BFE0F5C4378A74E705747C9DEE4}

>[!NOTE]
>[!UICONTROL Compare Time Periods] leverages advanced Calculated Metrics. As a result, it is available only to customers with Analytics Select, Prime, and Ultimate SKUs. 

Analysis requires context, and often that context is provided by a previous time period. For example, the question "How much better or worse are we doing than at this time last year?" is fundamental to understanding your business. Date Comparison automatically include a "difference" column, which shows the percentage change compared to a specified time period.

1. Create a Freeform table, with any dimensions and metrics you want to compare over a time period.
1. Right-click a table row and select **[!UICONTROL Compare time periods]**.

   ![](assets/compare-time.png)

   >[!NOTE]
   >
   >This right-click option is disabled for metric rows, date range rows, and time dimension rows.

1. Depending on how you have set the table's date range, you have these options for comparison: 

   |  Option  | Description  |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Compares to the week/month/etc. immediately before this date range.  |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Compares to the same date range a year ago.  |
   | **[!UICONTROL Custom date range to this date range]** | Lets you select a custom date range.  |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Custom date range to this date range]**.

1. The resulting comparison looks like this:

   ![](assets/compare-time-result.png)

   Rows in the Percent Change column appear red for negative values and green for positive values.

1. (Optional) As in any other Workspace projects, you can create visualizations based on these time comparisons. For example, here is a Bar graph:

   ![](assets/compare-time-barchart.png)

   Note that in order to show the percentage change in the bar chart, you have to have the [!UICONTROL Percentages] setting checked in the [!UICONTROL Visualization Settings].

## Add a time period column for comparison {#section_93CC2B4F48504125BEC104046A32EB93}

You can now add a time period to each column in a table, enabling you to add a time period that is different from the one your calendar is set to. This is another way you can compare dates.

1. Right-click a column in the table and select **[!UICONTROL Add time period column]**. 

   ![](assets/add-time-period-column.png)

1. Depending on how you have set the table's date range, you have these options for comparison: 

   |  Option  | Description  |
   |---|---|
   | **[!UICONTROL Prior week/month/quarter/year to this date range]** | Adds a column with the week/month/etc. immediately before this date range.  |
   | **[!UICONTROL This week/month/quarter/year last year to this date range]** | Adds the same date range a year ago.  |
   | **[!UICONTROL Custom date range to this date range]** | Lets you select a custom date range.  |

   >[!NOTE]
   >
   >When you select a custom number of days, for example October 7 - October 20 (a 14-day range), you will get only 2 options: **[!UICONTROL Prior 14 days before this date range]**, and **[!UICONTROL Custom date range to this date range]**.

1. The time period will be inserted on top of the column you selected:

   ![](assets/add-time-period-column2.png)

1. You can add as many time columns as you want, as well as mix and match different date ranges:

   ![](assets/add-time-period-column4.png)

1. In addition, you can sort on each column, which will change the order of days depending on the column you are sorting on.

## Align column dates to start on the same row {#section_5085E200082048CB899C3F355062A733}

You can align the dates from each column to all start on the same row. 

For example, when you choose to align the dates, if you do a month-over-month comparison between October and September 2016, the left column will start with October 1 and the right column will start with September 1:

![](assets/add-time-period-column3.png)

>[!NOTE]
>
>Consider the following when using this option:
>
>* This setting is enabled by default for all new projects.
>
>* This setting applies to the entire table. For example, if you change this setting for a breakdown within the table, it will change the setting for the entire table.
>

To enable this setting, if it is not already enabled:

1. In the table where you want to align column dates, select the **Settings** icon in the table header.

1. On the [!UICONTROL **Settings**] tab, select **[!UICONTROL Align Dates from each column to all start on the same row (applies to entire table)]**.

![](assets/date-comparison-setting.png)


-->