---
description: Passaggi per creare una richiesta di dati di Report Builder di base.
title: Create a Data Request (Creare una richiesta di archivio dati)
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
source-git-commit: d2e4a6eed54fa8b3e080b162a5e841fc2f5a0e59
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 2%

---

# Creare una richiesta di dati di Report Builder

Passaggi per creare una richiesta di dati di base.

1. In Excel, fai clic su **[!UICONTROL Create]**.
1. In [!UICONTROL Request Wizard: Step 1] finestra, selezionare una [suite di rapporti](/help/analyze/report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Facoltativo) Seleziona un segmento da applicare alla richiesta. Dopo aver selezionato uno o più segmenti, questi si sposteranno in alto nell’elenco.

   Report Builder utilizza i segmenti nello stesso modo in cui vengono utilizzati da Adobe Analytics. Consulta la sezione [Guida alla segmentazione di Analytics](https://experienceleague.adobe.com/docs/analytics/components/segmentation/seg-home.html).
1. Seleziona una [tipo di rapporto](/help/analyze/report-builder/data-requests/c-report-types/select-report-types.md).
1. Specifica una [intervallo date](/help/analyze/report-builder/data-requests/configuring-report-dates/custom-calendar.md) e la relazione [granularità](/help/analyze/report-builder/data-requests/configuring-report-dates/granularity.md).
1. Fai clic su **[!UICONTROL Next]**.
1. In [Layout: Creazione guidata richieste passaggio 2](/help/analyze/report-builder/layout/layout.md) finestra, specificare un layout:

   | Elemento | Descrizione |
   |---|---|
   | Layout pivot | Fornisce una griglia di righe, colonne e metriche per il layout, simile alle tabelle Excel standard. Utilizzando questo layout, puoi aggiungere richieste di suddivisione all’interno di una richiesta originale. |
   | Layout personalizzato | Fornisce la maggior parte delle funzionalità del [!UICONTROL Pivot Layout] ma consente di scegliere dove collocare ogni elemento della griglia nel foglio di calcolo. Questo layout offre la flessibilità disponibile nelle versioni precedenti. |

1. Sulla [!UICONTROL Metrics] fare doppio clic (o trascinare) sulle metriche nella struttura per aggiungerle alla [!UICONTROL Metrics] griglia.
1. Sulla [!UICONTROL Dimensions] fare doppio clic (o trascinare) sulle dimensioni [!UICONTROL Row Labels] griglia.

   La [dimensioni](https://experienceleague.adobe.com/docs/analytics/analyze/report-builder/layout/filter-dimenson/filter-dimensions.html) disponibile nel passaggio 2 dipende dal rapporto di base selezionato nel passaggio 1 e dalla configurazione della suite di rapporti. Le dimensioni sono elementi che correlano, si riferiscono o sono una classificazione della metrica del tipo di rapporto originale selezionata nella [!UICONTROL Request Wizard: Step 1] finestra. Aggiungi più di una dimensione al passaggio 2 per creare un raggruppamento nella richiesta di dati.

   Vedi [Aggiungere metriche e Dimension](/help/analyze/report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md) per ulteriori informazioni.
