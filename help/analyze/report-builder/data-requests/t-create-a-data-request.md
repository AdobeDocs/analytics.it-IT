---
description: Passaggi per creare una richiesta di dati di Report Builder di base.
title: Create a Data Request (Creare una richiesta di archivio dati)
uuid: 5d0151f1-e23d-43eb-84a4-96ae06c3a564
feature: Report Builder
role: Business Practitioner, Administrator
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 6%

---


# Creare una richiesta di dati di Report Builder

Passaggi per creare una richiesta di dati di base.

1. In Excel, fai clic su **[!UICONTROL Create]**.
1. Nella finestra [!UICONTROL Request Wizard: Step 1], seleziona una [suite di rapporti](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Facoltativo) Seleziona un segmento da applicare alla richiesta. Dopo aver selezionato uno o più segmenti, questi si sposteranno in alto nell’elenco.

   Report Builder utilizza i segmenti nello stesso modo in cui vengono utilizzati da Adobe Analytics. Consulta la [Guida alla segmentazione di Analytics](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html). 1. (Facoltativo) Selezionare una [lista di pubblicazione](/help/analyze/report-builder/data-requests/allow-publishing-list-overrides.md) da utilizzare per la distribuzione.
1. Seleziona un [tipo di report](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Specifica un [intervallo di date](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) e un rapporto [granularità](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Fai clic su **[!UICONTROL Next]**.
1. Nella finestra [Layout - Richiesta guidata Passaggio 2](/help/analyze/report-builder/layout/layout.md), specificare un layout:

   | Elemento | Descrizione |
   |---|---|
   | Layout pivot | Fornisce una griglia di righe, colonne e metriche per il layout, simile alle tabelle Excel standard. Utilizzando questo layout, puoi aggiungere richieste di suddivisione all’interno di una richiesta originale. |
   | Layout personalizzato | Fornisce la maggior parte delle funzionalità di [!UICONTROL Pivot Layout], ma consente di scegliere dove collocare ogni elemento della griglia nel foglio di calcolo. Questo layout offre la flessibilità disponibile nelle versioni precedenti. |

1. Nella scheda [!UICONTROL Metrics] , fai doppio clic (o trascina) sulle metriche nella struttura per aggiungerle alla griglia [!UICONTROL Metrics].
1. Nella scheda [!UICONTROL Dimensions] , fai doppio clic (o trascina) sulle dimensioni nella griglia [!UICONTROL Row Labels].

   Le [dimensioni](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) disponibili nel passaggio 2 dipendono dal rapporto di base selezionato al passaggio 1 e dalla configurazione della suite di rapporti. Le dimensioni sono elementi correlati, correlati o sono una classificazione della metrica del tipo di rapporto originale selezionata nella finestra [!UICONTROL Request Wizard: Step 1]. Aggiungi più di una dimensione al passaggio 2 per creare un raggruppamento nella richiesta di dati.

   Per ulteriori informazioni, consulta [Aggiungere metriche e Dimension](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) .
