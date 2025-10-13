---
description: Scopri come creare una richiesta di rilevamento delle anomalie in Report Builder.
title: Come configurare una richiesta di rilevamento delle anomalie
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 3%

---

# Configurare una richiesta di rilevamento delle anomalie

{{legacy-arb}}

Per creare una richiesta di rilevamento delle anomalie in Report Builder:

1. Selezionare un report con tendenze, ad esempio **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]**.
1. Nel menu [!UICONTROL Apply Granularity], selezionare **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >Il menu [!UICONTROL Anomaly Detection] è disponibile solo quando si seleziona Granularità giorno. I dati dei 30 giorni precedenti vengono utilizzati come periodo di formazione dei dati statistici, indipendentemente dall’intervallo di date selezionato.

1. Dopo aver configurato gli intervalli di date, fare clic su **[!UICONTROL Next]**.

   Nella Creazione guidata richieste: passaggio 2 di 2, aggiungere una metrica, ad esempio **[!UICONTROL Visits]**.

   Per la metrica aggiunta, fare clic sul collegamento **[!UICONTROL None]**.

   ![Schermata che mostra il rilevamento delle anomalie, quindi Inserisci e inserisci le opzioni per Limite inferiore e superiore e previsto.](assets/anomaly_select.png)

1. Seleziona **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Schermata che mostra il passaggio 2 della Creazione guidata richieste - Rapporto traffico.](assets/anomaly_visit.png)

   Quando selezionate una di queste opzioni, il sistema crea copie della metrica originale con Rilevamento anomalie. Ad esempio, per la metrica Visita, al gruppo [!UICONTROL Metric] viene aggiunta una metrica Visita con limite inferiore.
1. Fare clic su **[!UICONTROL Finish]** e selezionare la cella per l&#39;output in Excel.

   Per le definizioni, vedere [Rilevamento anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md).
