---
description: Scopri come creare una richiesta di rilevamento delle anomalie in Report Builder.
title: Come configurare una richiesta di rilevamento delle anomalie
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
TQID: https://experienceleague.adobe.com/9qyfB3mtj7QKDNLL1PRrQ2-3lzrb19-7gL4rnfxbph4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: c67272a6-888e-425e-9e97-a87304637eed
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 173
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
