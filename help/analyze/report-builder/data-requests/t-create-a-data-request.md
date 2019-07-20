---
description: Passaggi per creare una richiesta dati di Generatore di report di base.
seo-description: Passaggi per creare una richiesta dati di Generatore di report di base.
seo-title: Creare una richiesta dati di Generatore di report
solution: Analytics
title: Creazione di una richiesta dati
topic: Generatore di report
uuid: 5 d 0151 f 1-e 23 d -43 eb -84 a 4-96 ae 06 c 3 a 564
translation-type: tm+mt
source-git-commit: 65b3c25288060b1b6d0b9590a8fdca4087f416a0

---


# Creare una richiesta dati di Generatore di report

Passaggi per creare una richiesta dati di base.

1. In Excel, click **[!UICONTROL Create]**.
1. In the [!UICONTROL Request Wizard: Step 1] window, select a [report suite](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913).
1. (Facoltativo) Selezionate un segmento da applicare alla richiesta. Dopo aver selezionato uno o più segmenti, questi si sposteranno in cima all'elenco.

   Generatore di report utilizza segmenti nello stesso modo in cui Adobe Analytics li usa. See the [Analytics Segmentation Guide](https://marketing.adobe.com/resources/help/en_US/analytics/segment/). 1. (Optional) Select a [publishing list](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C) to use for distribution.
1. Select a [report type](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC).
1. Specify a [date range](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) and report [granularity](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB).
1. Fai clic su **[!UICONTROL Next]**.
1. In the [Layout - Request Wizard Step 2](../../../analyze/report-builder/layout/layout.md#concept_D66E1C2217E24E1F837AC064C61919DB) window, specify a layout:

   | Elemento | Descrizione |
   |---|---|
   | Layout pivot | Fornisce una griglia, una colonna e una griglia di metrica per il layout, in modo simile alle tabelle standard di Excel. Utilizzando questo layout, puoi aggiungere richieste di suddivisione all'interno di una richiesta originale. |
   | Layout personalizzato | Provides most of the functionality of the [!UICONTROL Pivot Layout] but lets you choose where each item in the grid should be located in the spreadsheet. Questo layout fornisce la flessibilità disponibile nelle versioni precedenti. |

1. On the [!UICONTROL Metrics] tab, double-click (or drag) metrics in the tree to add them to the [!UICONTROL Metrics] grid.
1. On the [!UICONTROL Dimensions] tab, double-click (or drag) dimensions to the [!UICONTROL Row Labels] grid.

   The [dimensions](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=dimensions) available in Step 2 depend on the base report you selected in Step 1, and on the configuration of your report suite. The dimensions are items that correlate, sub-relate, or are a classification of the original report type metric you selected on the [!UICONTROL Request Wizard: Step 1] window. L'aggiunta di più dimensioni al passaggio 2 è la modalità di creazione di una suddivisione nella richiesta dati.

   See [Add Metrics and Dimensions](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) for more information.