---
description: Passaggi per creare una richiesta di base di dati di Report Builder.
title: Create a Data Request (Creare una richiesta di archivio dati)
feature: Report Builder
role: User, Admin
exl-id: 21d552a0-7a58-4217-ba8a-7c87eb4757f6
TQID: https://experienceleague.adobe.com/w-oiIfs1qFMoQbaN8YrNIn1TRNHeN97lQOlkLeXdLb0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 267
ht-degree: 2%

---

# Creare una richiesta di dati Report Builder

{{legacy-arb}}

Passaggi per creare una richiesta di dati di base.

1. In Excel, fare clic su **[!UICONTROL Create]**.
1. Nella finestra [!UICONTROL Request Wizard: Step 1], seleziona una [suite di rapporti](/help/analyze/legacy-report-builder/data-requests/selecting-report-suites/t-select-report-suites.md).
1. (Facoltativo) Seleziona un segmento da applicare alla richiesta. Dopo aver selezionato uno o più segmenti, questi si sposteranno all’inizio dell’elenco.

   Report Builder utilizza i segmenti nello stesso modo in cui Adobe Analytics li utilizza. Consulta la [Guida alla segmentazione di Analytics](/help/components/segmentation/seg-home.md).
1. Selezionare un tipo di report [&#128279;](/help/analyze/legacy-report-builder/data-requests/c-report-types/select-report-types.md).
1. Specifica un [intervallo di date](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/custom-calendar.md) e report [granularità](/help/analyze/legacy-report-builder/data-requests/configuring-report-dates/granularity.md).
1. Fai clic su **[!UICONTROL Next]**.
1. Nella finestra [Layout - Creazione guidata richieste passaggio 2](/help/analyze/legacy-report-builder/layout/layout.md), specificare un layout:

   | Elemento | Descrizione |
   |---|---|
   | Layout pivot | Fornisce una griglia di righe, colonne e metriche per il layout, simile alle tabelle standard di Excel. Utilizzando questo layout, puoi aggiungere richieste di suddivisioni all’interno di una richiesta originale. |
   | Layout personalizzato | Fornisce la maggior parte delle funzionalità di [!UICONTROL Pivot Layout], ma consente di scegliere dove collocare ogni elemento nella griglia nel foglio di calcolo. Questo layout offre la flessibilità disponibile nelle versioni precedenti. |

1. Nella scheda [!UICONTROL Metrics] fare doppio clic (o trascinare) sulle metriche nella struttura per aggiungerle alla griglia [!UICONTROL Metrics].
1. Nella scheda [!UICONTROL Dimensions] fare doppio clic (o trascinare) sulle dimensioni nella griglia [!UICONTROL Row Labels].

   Le [dimensioni](/help/analyze/report-builder/filter-dimensions.md) disponibili nel passaggio 2 dipendono dal report di base selezionato nel passaggio 1 e dalla configurazione della suite di rapporti. Le dimensioni sono elementi correlati, sub-correlati o sono una classificazione della metrica del tipo di report originale selezionata nella finestra [!UICONTROL Request Wizard: Step 1]. L’aggiunta di più dimensioni nel passaggio 2 spiega come creare un raggruppamento nella richiesta di dati.

   Per ulteriori informazioni, vedere [Aggiungere metriche e dimensioni](/help/analyze/legacy-report-builder/layout/c-metrics-dimensions/t-add-metrics-and-dimensions.md).
