---
description: Scopri come creare una richiesta di rilevamento delle anomalie in Report Builder.
title: Come configurare una richiesta di rilevamento delle anomalie
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: 2eff7656741bdba3d5d7d1f33e9261b59f8e6083
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 3%

---

# Configurare una richiesta di rilevamento delle anomalie

Per creare una richiesta di rilevamento delle anomalie nel Report Builder:

1. Seleziona un rapporto con tendenze, ad esempio **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]** rapporto.
1. In [!UICONTROL Apply Granularity] menu, seleziona **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >Il [!UICONTROL Anomaly Detection] è disponibile solo quando selezioni Granularità giorno. I dati dei 30 giorni precedenti vengono utilizzati come periodo di formazione dei dati statistici, indipendentemente dall’intervallo di date selezionato.

1. Dopo aver configurato gli intervalli di date, fai clic su **[!UICONTROL Next]**.

   Nella Creazione guidata richieste: passaggio 2 di 2, aggiungi una metrica, ad esempio **[!UICONTROL Visits]**.

   Per la metrica aggiunta, fai clic su **[!UICONTROL None]** collegamento.

   ![Schermata che mostra il rilevamento delle anomalie, quindi Inserisci e inserire le opzioni per Limite inferiore e superiore e previsto.](assets/anomaly_select.png)

1. Seleziona **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Schermata che mostra il Passaggio 2 della Creazione guidata richieste - Rapporto traffico.](assets/anomaly_visit.png)

   Quando selezionate una di queste opzioni, il sistema crea copie della metrica originale con Rilevamento anomalie. Ad esempio, per la metrica Visita, una metrica Visita con limite inferiore viene aggiunta al [!UICONTROL Metric] gruppo.
1. Clic **[!UICONTROL Finish]** e selezionare la cella per l&#39;output in Excel.

   Consulta [Rilevamento delle anomalie](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) definizioni.
