---
description: Passaggi per creare una richiesta di base di dati di Report Builder.
title: Create a Data Request (Creare una richiesta di archivio dati)
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: d2e4a6eed54fa8b3e080b162a5e841fc2f5a0e59
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 2%

---

# Creazione di una richiesta di dati di Report Builder

Passaggi per creare una richiesta di dati di base.

1. In Excel, fai clic su **[!UICONTROL Create]**.
1. In [!UICONTROL Request Wizard: Step 1] finestra, seleziona un [suite di rapporti](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Facoltativo) Seleziona un segmento da applicare alla richiesta. Dopo aver selezionato uno o più segmenti, questi si sposteranno all’inizio dell’elenco.

   Il Report Builder utilizza i segmenti nello stesso modo in cui Adobe Analytics li utilizza. Consulta la [Guida alla segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html).
1. Seleziona un [tipo di rapporto](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Specifica un [intervallo date](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) rapporto e [granularità](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Fai clic su **[!UICONTROL Next]** (Usa modello di attribuzione non predefinito).
1. In [Layout: Creazione guidata richieste passaggio 2](/help/analyze/report-builder/layout/layout.md) , specificare un layout:

   | Elemento | Descrizione |
   |---|---|
   | Layout pivot | Fornisce una griglia di righe, colonne e metriche per il layout, simile alle tabelle standard di Excel. Utilizzando questo layout, puoi aggiungere richieste di suddivisioni all’interno di una richiesta originale. |
   | Layout personalizzato | Fornisce la maggior parte delle funzionalità di [!UICONTROL Pivot Layout] ma consente di scegliere dove posizionare ogni elemento nella griglia nel foglio di calcolo. Questo layout offre la flessibilità disponibile nelle versioni precedenti. |

1. Il giorno [!UICONTROL Metrics] , fare doppio clic (o trascinare) sulle metriche nella struttura ad albero per aggiungerle al [!UICONTROL Metrics] griglia.
1. Il giorno [!UICONTROL Dimensions] , fare doppio clic (o trascinare) le dimensioni nella [!UICONTROL Row Labels] griglia.

   Il [dimensioni](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) disponibili nel passaggio 2 dipendono dal rapporto di base selezionato nel passaggio 1 e dalla configurazione della suite di rapporti. Le dimensioni sono elementi correlati, sub-correlati o sono una classificazione della metrica del tipo di rapporto originale selezionata nel [!UICONTROL Request Wizard: Step 1] finestra. L’aggiunta di più dimensioni nel passaggio 2 spiega come creare un raggruppamento nella richiesta di dati.

   Consulta [Aggiungere metriche e Dimension](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) per ulteriori informazioni.
