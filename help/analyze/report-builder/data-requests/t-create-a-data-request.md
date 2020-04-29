---
description: Procedura per creare una richiesta di dati Generatore di report di base.
title: Create a Data Request (Creare una richiesta di archivio dati)
topic: Report builder
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Creare una richiesta di dati Generatore di report

Procedura per creare una richiesta di dati di base.

1. In Excel, fare clic su **[!UICONTROL Create]**.
1. Nella [!UICONTROL Request Wizard: Step 1] finestra, seleziona una suite [di](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md)rapporti.
1. (Facoltativo) Selezionate un segmento da applicare alla richiesta. Dopo aver selezionato uno o più segmenti, questi si sposteranno in cima all’elenco.

   Generatore di report utilizza i segmenti nello stesso modo in cui vengono utilizzati da Adobe Analytics. Consulta la Guida alla segmentazione di [Analytics](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html). 1. (Facoltativo) Selezionate un elenco [di](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) pubblicazione da usare per la distribuzione.
1. Select a [report type](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Specifica un intervallo [di](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) date e una [granularità](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md)del report.
1. Fai clic su **[!UICONTROL Next]**.
1. Nella finestra [Layout - Richiesta guidata Passaggio 2](/help/analyze/report-builder/layout/layout.md) , specificare un layout:

   | Elemento | Descrizione |
   |---|---|
   | Layout pivot | Fornisce una griglia di righe, colonne e metriche per il layout, simile alle tabelle Excel standard. Utilizzando questo layout, potete aggiungere richieste di suddivisione all&#39;interno di una richiesta originale. |
   | Layout personalizzato | Offre la maggior parte delle funzionalità del [!UICONTROL Pivot Layout] foglio di calcolo, ma consente di scegliere dove posizionare ogni elemento della griglia nel foglio di calcolo. Questo layout offre la flessibilità disponibile nelle versioni precedenti. |

1. Nella [!UICONTROL Metrics] scheda, fai doppio clic (o trascina) sulle metriche nella struttura ad albero per aggiungerle alla [!UICONTROL Metrics] griglia.
1. Nella [!UICONTROL Dimensions] scheda, fate doppio clic (o trascinate) sulle dimensioni della [!UICONTROL Row Labels] griglia.

   Le [dimensioni](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) disponibili nel Passaggio 2 dipendono dal rapporto di base selezionato al Passaggio 1 e dalla configurazione della suite di rapporti. Le dimensioni sono elementi che corrispondono, si riferiscono o sono una classificazione della metrica del tipo di rapporto originale selezionata nella [!UICONTROL Request Wizard: Step 1] finestra. Il passo 2 prevede l’aggiunta di più dimensioni per la creazione di una suddivisione nella richiesta di dati.

   Per ulteriori informazioni, consulta [Aggiungere metriche e dimensioni](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) .
