---
description: Scopri come definire intervalli di date personalizzati in Analysis Workspace.
keywords: Analysis Workspace
title: Esempio di intervalli di date personalizzati
feature: Date Ranges
role: User, Admin
exl-id: 586bb120-3f20-452c-9867-0b93d2e794bc
TQID: https://experienceleague.adobe.com/aE8L1czTiBKQG3MR-9aCxkBgO2qLp17K-n7Qmnjj-YM
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 118
ht-degree: 3%

---

# Esempi di intervalli di date personalizzati

Questo articolo mostra ulteriori esempi di intervalli di date personalizzati.



## Ultimi due mesi fa

+++ Dettagli

Desideri definire un intervallo di date personalizzato che definisce due mesi fa. Utilizzate uno dei predefiniti.

![Ultimi 2 mesi fa](assets/date-range-example-simple.png)

+++


## In sequenza fino alla fine della settimana scorsa

+++ Dettagli

Definire un intervallo di date che definisca il periodo compreso tra il giorno corrente una settimana fa e la fine della stessa settimana precedente. Ad esempio, se oggi è mercoledì 11 settembre 2024. Desideri un intervallo di date da mercoledì 4 settembre 2024 a sabato 7 settembre 2024.

![Esempio di intervallo di date](assets/date-range-example.png)

+++ 

<!--

# Create custom date ranges

You can create custom date ranges in Analysis Workspace and save them as Time components. 

For information about adding existing date ranges to a project, see [Calendar and date ranges overview](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).

To create a custom date range:

 1. In Adobe Analytics, select **[!UICONTROL Components]** > **[!UICONTROL Date ranges]**.

    ![date range page](assets/date-ranges.png)
 
 1. Select [!UICONTROL **Create new date range**].

 1. In the Date range builder, specify the following information:
    
    |Option | Description |
    |---------|----------|
    | [!UICONTROL **Title**] | The title of the date range as it will appear when users select it in Analysis Workspace. |
    | [!UICONTROL **Description**] | A description for the date range. |
    | [!UICONTROL **Tags**] | Any tags you want to apply to the date range. |
    | [!UICONTROL **Date Range**] | Lets you pick a custom date range. By default, the last 30 days are selected. |
    | [!UICONTROL **Preset**] | Choose from a list of preset date ranges, such as [!UICONTROL **Yesterday**], [!UICONTROL **Last 7 days**], [!UICONTROL **Last 30 days**], and so forth. |
    | [!UICONTROL **Start time**] | The time of day that the date range begins. |
    | [!UICONTROL **End time**] | The time of day that the date range ends. |
    | [!UICONTROL **Use rolling dates**] | Rolling dates allow you to generate a dynamic report that looks forward or backward for a set period of time based on when you ran the report. For example, if you want to report on all Orders placed "Last Month" (based on the Created Date field) and ran that report in December, you'd see orders placed in November. If you ran that same report in January, you'd see orders placed in December.<ul><li>**[!UICONTROL Date Preview]**: Indicates what time period the rolling calendar encompasses.</li><li>**[!UICONTROL Start]**: You can choose among current day, current week, current month, current quarter, current year.</li><li>**[!UICONTROL End]**: You can choose among current day, current week, current month, current quarter, current year.</li></ul><br>Selected by default. |

 1. Select [!UICONTROL **Save**]. 

## Example: Date range for "two months ago" {#section_C4109C57CB444BB2A79CC8082BD67294}

The following custom date range shows a date range for "two months ago," with a Summary Change visualization showing directional change.

![](assets/date-range-two-months-ago.png)

The custom date range is displayed at the top of the [!UICONTROL Date Range] component panel in your project:

![](assets/date-range-panel-two-months-ago.png)

You can drag this custom date range into a column alongside a custom, monthly rolling date range using the Last Month preset for a comparison. Add a Summary Change visualization and select the totals from each column to show directional change:

![](assets/date-range-two-months-table.png)

## Example: Use a 7-day rolling date range {#section_7EF63B2E9FF54D2E9144C4F76956A8DD}

You can create a date range that specifies a 7-day rolling window that ends one week ago:

![](assets/create_date_range.png)

Use *`rolling daily`*.

* The Start settings would be *`current day minus 6 days`*.

* The End settings would be *`current day minus 7 days`*.

This date range can be a component that you drag onto any freeform table.

-->