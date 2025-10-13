---
description: Utilizza il calendario e gli intervalli di dati per specificarli in Analysis Workspace.
title: Panoramica sugli intervalli di date
feature: Date Ranges
role: User, Admin
exl-id: fbf4bc18-65ba-4e39-96c1-4c41a8e3baa9
source-git-commit: ff38740116ac6f12033ebdc17cffa3250a30f3f7
workflow-type: tm+mt
source-wordcount: '513'
ht-degree: 100%

---


# Panoramica sugli intervalli di date

In un progetto Workspace, in genere si utilizza il [calendario in un pannello](/help/analyze/analysis-workspace/c-panels/panels.md#calendar) per specificare l’intervallo di date per le visualizzazioni in tale pannello.

I componenti intervallo di date consentono di definire e sovrascrivere le impostazioni del calendario per il pannello.


## Utilizzare intervalli di date

Puoi utilizzare un componente intervallo di date per ridefinire il calendario del pannello.

In alternativa, in una tabella a forma libera puoi utilizzare un intervallo di date come metrica o dimensione.

![Utilizzo di intervalli di date](assets/date-ranges-usage.png)

- **Metrica**. Ad esempio, per confrontare una dimensione per due mesi diversi per una metrica specifica.
- **Dimensione**. Per confrontare una metrica su diversi elementi dimensionali per la dimensione Intervallo date.

>[!NOTE]
>
>Quando si utilizzano intervalli di date in una tabella a forma libera, gli intervalli di date sovrascrivono il calendario specificato per il pannello a cui appartiene la tabella a forma libera.
>

Utilizza l’intervallo di date come [useresti qualsiasi componente](/help/analyze/analysis-workspace/components/analysis-workspace-components.md#analysis-workspace-components). Trascina l’intervallo di date dal ![Calendario](/help/assets/icons/Calendar.svg) **[!UICONTROL Date ranges]** del pannello dei componenti in:

- **[!UICONTROL Calendar]**: ![scambia](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** la configurazione del calendario corrente con l’intervallo di date.
- **Intestazione colonna Metrica**: ![sostituisci](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** la metrica, ![aggiungi ](/help/assets/icons/Add.svg)**[!UICONTROL Add]**l’intervallo di date come metrica o ![filtra](/help/assets/icons/Filter.svg)**[!UICONTROL Filter]**la metrica utilizzando il componente intervallo di date.
- **Intestazione colonna Dimensione**: ![sostituisci](/help/assets/icons/Switch.svg) **[!UICONTROL Replace]** le dimensioni correnti. La nuova dimensione è ora **[!UICONTROL Date ranges]**. Una volta che la dimensione è Intervalli di date, puoi ![aggiungere ](/help/assets/icons/Add.svg)**[!UICONTROL Add]**ulteriori intervalli di date come elementi dimensione.
- **Elemento dimensione**: ![raggruppa](/help/assets/icons/Breakdown.svg) **[!UICONTROL Breakdown]** l’elemento dimensione specifico in base all’intervallo di date.

Puoi anche aggiungere una colonna di intervalli di date direttamente in una visualizzazione tabella a forma libera:

1. In una colonna di metrica, seleziona dal menu di scelta rapida:

   - **[!UICONTROL Add time period column]**. Puoi scegliere tra le opzioni suggerite basate sul calendario corrente o creare un [intervallo di date personalizzato](#custom-date-ranges).
   - **[!UICONTROL Compare time periods]**. Puoi scegliere tra un’opzione suggerita basata sul calendario corrente o creare un [intervallo di date personalizzato](#custom-date-ranges).

1. In base alla selezione, alla tabella a forma libera vengono aggiunte altre colonne di intervalli di date.

## Intervalli di date predefiniti

Analysis Workspace fornisce una serie di intervalli di date predefiniti.


| Giorno | Settimana | Mese | Trimestre | Anno |
|---|---|---|---|---|
| Oggi | Questa settimana | Questo mese | Questo trimestre | Quest’anno |
| Ieri | Questa settimana (escluso oggi) | Questo mese (escluso oggi) | Questo trimestre (escluso oggi) | Quest’anno (escluso oggi) |
| 2 giorni fa | 2 settimane fa | 2 mesi fa |   |  |
| 3 giorni fa | 3 settimane fa | 3 mesi fa |  | |
| Ultimi 7 giorni | Ultima settimana | Ultimo mese | Ultimo trimestre | L’anno scorso |
| Ultimi 14 giorni | Ultime 2 settimane intere | Ultimi 2 mesi interi | Ultimi 4 trimestri interi | |
| Ultimi 30 giorni | Ultime 3 settimane intere | Ultimi 3 mesi interi | | |
| Ultimi 60 giorni | Ultime 4 settimane intere | Ultimi 6 mesi interi | | |
| Ultimi 90 giorni | Ultime 12 settimane intere | Ultimi 12 mesi interi | | |
| Ultimi 7 giorni interi | Ultime 52 settimane intere | Ultimi 13 mesi interi | | |
| Ultimi 14 giorni interi | | | | |
| Ultimi 30 giorni interi | | | | |
| Ultimi 90 giorni interi | | | | |

<table style="table-layout:fixed">

## Intervalli di date personalizzati

Puoi creare intervalli di date personalizzati. Consulta [Crea intervallo di date](create.md) per le varie opzioni disponibili per la creazione di intervalli di date. Puoi quindi creare, modificare e salvare intervalli di date nel [Generatore di intervalli di date](create.md#date-range-builder).

Utilizza [Gestione intervallo di date](manage.md) per gestire gli intervalli di date.



<!--
# Calendar and date ranges overview {#date-range}

>[!CONTEXTUALHELP]
>id="components_dateranges_endtime"
>title="End time"
>abstract="End times always include 59 seconds."



In the calendar, you can specify dates and date ranges, or select a preset.


>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Calendar and date ranges overview](https://video.tv.adobe.com/v/23973?quality=12&learn=on){target="_blank"} for a demo video.

>[!ENDSHADEBOX]


Calendar selections apply at the panel level, but you have the option to apply them to all panels. When you click a date range in Workspace, the interface displays the current calendar month and the previous calendar month. You can adjust these two calendars by clicking the right and left arrows in each respective upper corner.

![Calendar](assets/aw_calendar2.png){width="60%"} 

## Select and apply date ranges {#select-apply}

The first click on a calendar starts a date range selection. The second click completes a date range selection, which becomes highlighted. If the `Shift` key is held down (or right-click is used), it appends to the currently selected range.

You can also drag dates (and time dimensions) into a Workspace project. You can select specific days, weeks, months, years, or a rolling date.

[Using Date Ranges and Calendar in Analysis Workspace](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/calendar-and-date-ranges/using-dates-in-analysis-workspace.html?lang=it) (4:07)

| Setting | Description |
|--- |--- |
|Selected Days|Selected days/weeks/months/years.|
|Make date range components relative to panel calendar| If disabled, any date range components used within a table, visualization, or panel drop zone override the panel calendar. <p>If enabled, any date range components used within a table, visualization, or panel drop zone are in relation to the panel date range. For example, if the panel date range is set to November 1 through November 30, and a Last Week date range component is used in a freeform table, the information in the freeform table refers to the last week in October. |
|Use rolling dates| Rolling dates allow you to generate a dynamic report that looks forward or backward for a set period of time based on when you ran the report. For example, if you want to report on all Orders placed "Last Month" (based on the Created Date field) and ran that report in December, you'd see orders placed in November. If you ran that same report in January, you'd see orders placed in December.<ul><li>**[!UICONTROL Date Preview]**: Indicates what time period the rolling calendar encompasses.</li><li>**[!UICONTROL Start]**: You can choose among current day, current week, current month, current quarter, current year.</li><li>**[!UICONTROL End]**: You can choose among current day, current week, current month, current quarter, current year.</li></ul>To view an example, see [Custom date ranges](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md). <br>Selected by default.|
|Date Range|Lets you pick a preset date range. Last 30 days is the default. **[!UICONTROL This week/month/quarter/year (excluding today)]** lets you choose from date ranges that do not include partial-day data from today.|
|Apply to All Panels|Lets you not only change the selected date range for the current panel, but also for all other panels within the project.|
|Apply|Applies the date range to this panel only.|

## About relative panel date ranges {#relative-panel-dates}

If you're working in Workspace, you can make the date range components relative to the panel calendar. 
Three common use cases where you'll see relative panel dates take effect are Combo charts, Key metrics summary, and Freeform table date ranges.

To use relative panel date ranges

1. Select the **Workspace** tab.
1. Select **Blank project**.
1. Add dimensions, metrics, and segments from the left rail. 
1. Click the panel date range field to toggle the relative panel date range setting.
1. Select **Make date range components relative to panel calendar**.
    * Select the option to make the date range components relative to the panel calendar.
        If relative dates are selected, then rolling dates will be based on the start date of the panel calendar and not today's date.
    * If this option isn't selected, then rolling dates will be based on today's date.

    ![relative panel dates](assets/relative-date-selected.png){width="60%"} 

1. Click **Apply**.
    The relative dates are shown in the upper-right.

    ![relative dates in freeform ](assets/relative-date-range1.png)

## Guidelines for relative panel date ranges {#guidelines}

Keep in mind the following guidelines when using relative panel date ranges.

### Formulas and relative date ranges {#formula-relative-dates}

If you have relative dates selected, all date formulas will use the panel's start date as the starting point.

### Custom calendars and relative date ranges {#custom-calendar-formulas}

When you use a week-based custom calendar and you add months or years, the formula calculates the offset of the day in the given period. The actual date may be different because of the offset. The formula chooses the day landing in the same place in the custom calendar. For example, the third Friday of the third week in a custom calendar.

### About segments that use rolling dates and relative panel date ranges {#segments-relative-dates}

If you build a segment or use a segment with a rolling date, for example, the Last 7 Days or the Last 2 Weeks, and you click on the segment preview, it will start the rolling date from *Today* instead of the panel start date. As a result the preview for the segment will not match when you actually use the segment in the table. The preview is impacted, not the segment itself. 

## Guidelines for panel date ranges and previews {#guidelines-panel-dates}

* Starting with the February release, component and data previews will be based on the panel date range and not the last 90 days. 
* All components listed in the left rail will be available based on the panel date range. 
* All date previews in the segment and calculated metric builders will be based on the panel date range (unless accessed from the component managers, which do not have an associated panel, they will still be based on the last 90 days). 
* Any data previews will display data or components based on the panel date range.

-->