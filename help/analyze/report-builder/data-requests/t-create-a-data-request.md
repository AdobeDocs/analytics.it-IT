---
description: Passaggi per creare una richiesta di base di dati di Report Builder.
title: Create a Data Request (Creare una richiesta di archivio dati)
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: d2e4a6eed54fa8b3e080b162a5e841fc2f5a0e59
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 3%

---

# Creazione di una richiesta di dati di Report Builder

Passaggi per creare una richiesta di dati di base.

1. In Excel, fare clic su **[!UICONTROL Create]**.
1. Nella finestra [!UICONTROL Request Wizard: Step 1], seleziona una [suite di rapporti](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Facoltativo) Seleziona un segmento da applicare alla richiesta. Dopo aver selezionato uno o più segmenti, questi si sposteranno all’inizio dell’elenco.

   Il Report Builder utilizza i segmenti nello stesso modo in cui Adobe Analytics li utilizza. Consulta la [Guida alla segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html?lang=it).
1. Selezionare un tipo di report [](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Specifica un [intervallo di date](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) e report [granularità](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Fai clic su **[!UICONTROL Next]**.
1. Nella finestra [Layout - Creazione guidata richieste passaggio 2](/help/analyze/report-builder/layout/layout.md), specificare un layout:

   | Elemento | Descrizione |
   |---|---|
   | Layout pivot | Fornisce una griglia di righe, colonne e metriche per il layout, simile alle tabelle standard di Excel. Utilizzando questo layout, puoi aggiungere richieste di suddivisioni all’interno di una richiesta originale. |
   | Layout personalizzato | Fornisce la maggior parte delle funzionalità di [!UICONTROL Pivot Layout], ma consente di scegliere dove collocare ogni elemento nella griglia nel foglio di calcolo. Questo layout offre la flessibilità disponibile nelle versioni precedenti. |

1. Nella scheda [!UICONTROL Metrics] fare doppio clic (o trascinare) sulle metriche nella struttura per aggiungerle alla griglia [!UICONTROL Metrics].
1. Nella scheda [!UICONTROL Dimensions] fare doppio clic (o trascinare) sulle dimensioni nella griglia [!UICONTROL Row Labels].

   Le [dimensioni](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) disponibili nel passaggio 2 dipendono dal report di base selezionato nel passaggio 1 e dalla configurazione della suite di rapporti. Le dimensioni sono elementi correlati, sub-correlati o sono una classificazione della metrica del tipo di report originale selezionata nella finestra [!UICONTROL Request Wizard: Step 1]. L’aggiunta di più dimensioni nel passaggio 2 spiega come creare un raggruppamento nella richiesta di dati.

   Per ulteriori informazioni, vedere [Aggiungere metriche e Dimension](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md).
