---
description: Procedura per creare una richiesta di dati Generatore di report di base.
seo-description: Procedura per creare una richiesta di dati Generatore di report di base.
seo-title: Creare una richiesta di dati Generatore di report
solution: Analytics
title: Create a Data Request (Creare una richiesta di archivio dati)
topic: Generatore di report
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Creare una richiesta di dati Generatore di report

Procedura per creare una richiesta di dati di base.

1. In Excel, fare clic su **[!UICONTROL Create]**.
1. Nella [!UICONTROL Request Wizard: Step 1] finestra, seleziona una suite [di](../../../analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md#task_59444416F6F042D1998217AE91580913)rapporti.
1. (Facoltativo) Selezionate un segmento da applicare alla richiesta. Dopo aver selezionato uno o più segmenti, questi si sposteranno in cima all’elenco.

   Generatore di report utilizza i segmenti nello stesso modo in cui vengono utilizzati da Adobe Analytics. Consulta la Guida alla segmentazione di [Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/segment/). 1. (Facoltativo) Selezionate un elenco [di](../../../analyze/report-builder/data-requests/allow-publishing-list-overrides.md#concept_BCB19A20DC4B4B8D984F9670EE018D8C) pubblicazione da usare per la distribuzione.
1. Select a [report type](../../../analyze/report-builder/data-requests/c-report-types/select-report-types.md#concept_C711B27E6FB64C18AC564EE142FC7EFC).
1. Specifica un intervallo [di](../../../analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) date e una [granularità](../../../analyze/report-builder/data-requests/configuring-report-dates/granularity.md#concept_A13CBA2962E24FF882456135431B7ADB)del report.
1. Fai clic su **[!UICONTROL Next]**.
1. Nella finestra [Layout - Richiesta guidata Passaggio 2](../../../analyze/report-builder/layout/layout.md#concept_D66E1C2217E24E1F837AC064C61919DB) , specificare un layout:

   | Elemento | Descrizione |
   |---|---|
   | Layout pivot | Fornisce una griglia di righe, colonne e metriche per il layout, simile alle tabelle Excel standard. Utilizzando questo layout, potete aggiungere richieste di suddivisione all'interno di una richiesta originale. |
   | Layout personalizzato | Offre la maggior parte delle funzionalità del [!UICONTROL Pivot Layout] foglio di calcolo, ma consente di scegliere dove posizionare ogni elemento della griglia nel foglio di calcolo. Questo layout offre la flessibilità disponibile nelle versioni precedenti. |

1. Nella [!UICONTROL Metrics] scheda, fai doppio clic (o trascina) sulle metriche nella struttura ad albero per aggiungerle alla [!UICONTROL Metrics] griglia.
1. Nella [!UICONTROL Dimensions] scheda, fate doppio clic (o trascinate) sulle dimensioni della [!UICONTROL Row Labels] griglia.

   Le [dimensioni](https://marketing.adobe.com/resources/help/en_US/reference/dimensions.html) disponibili nel Passaggio 2 dipendono dal rapporto di base selezionato al Passaggio 1 e dalla configurazione della suite di rapporti. Le dimensioni sono elementi che corrispondono, si riferiscono o sono una classificazione della metrica del tipo di rapporto originale selezionata nella [!UICONTROL Request Wizard: Step 1] finestra. Il passo 2 prevede l’aggiunta di più dimensioni per la creazione di una suddivisione nella richiesta di dati.

   Per ulteriori informazioni, consulta [Aggiungere metriche e dimensioni](../../../analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md#task_E3F520C020F64C5A96DC5C96FEF71FC4) .