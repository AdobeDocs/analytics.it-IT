---
description: Passaggi che descrivono come creare una richiesta di rilevamento delle anomalie in Report Builder.
title: Configurare una richiesta di rilevamento delle anomalie
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
feature: Report Builder
role: User, Admin
exl-id: 0a8b1971-8d32-424a-9d41-d7ab2af54d1e
source-git-commit: ce7f953b8f7f1f7d0616074454e4401937fcc0c7
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 9%

---

# Configurare una richiesta di rilevamento delle anomalie

Per creare una richiesta di rilevamento delle anomalie in Report Builder:

1. Seleziona un rapporto con tendenze, ad esempio un **[!UICONTROL Site Metrics]** > **[!UICONTROL Traffic]** rapporto.
1. In [!UICONTROL Apply Granularity] menu, seleziona **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >La [!UICONTROL Anomaly Detection] Il menu è disponibile solo quando si seleziona Granularità giorno . I 30 giorni precedenti di dati vengono utilizzati come periodo di formazione per i dati statistici, indipendentemente dall’intervallo di date selezionato.

1. Dopo aver configurato gli intervalli di date, fai clic su **[!UICONTROL Next]**.

   Passaggio 1: Nella Creazione guidata richieste: Passaggio 2 di 2, aggiungi una metrica, ad esempio **[!UICONTROL Visits]**.

   Passaggio 1: Per la metrica aggiunta, fai clic sul pulsante **[!UICONTROL None]** link.

   ![Risultato del passaggio](assets/anomaly_select.png)

1. Seleziona **[!UICONTROL Anomaly Detection]** > **[!UICONTROL `<selection>`]**.

   ![Informazioni sul passaggio](assets/anomaly_visit.png)

   Quando selezioni una di queste opzioni, il sistema crea copie di Rilevamento anomalie della metrica originale. Ad esempio, per la metrica Visita, viene aggiunta una metrica Visita con limite inferiore alla [!UICONTROL Metric] gruppo.
1. Fai clic su **[!UICONTROL Finish]** e selezionare la cella per l&#39;output in Excel.

   Vedi [Rilevamento delle anomalie](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) per le definizioni.
