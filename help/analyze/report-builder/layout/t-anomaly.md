---
description: Procedura che descrive come creare una richiesta di rilevamento delle anomalie nel generatore di report.
seo-description: Procedura che descrive come creare una richiesta di rilevamento delle anomalie nel generatore di report.
seo-title: Configurare una richiesta di rilevamento delle anomalie
solution: Analytics
title: Configurare una richiesta di rilevamento delle anomalie
topic: Generatore di report
uuid: 1e504ff9-df88-4fa7-95ea-1ca05a6f9c0d
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Configurare una richiesta di rilevamento delle anomalie

Procedura che descrive come creare una richiesta di rilevamento delle anomalie nel generatore di report.

1. Selezionate un rapporto con tendenze, ad esempio un rapporto **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Traffic]** .
1. Nel [!UICONTROL Apply Granularity] menu selezionare **[!UICONTROL Day]**.

   >[!NOTE]
   >
   >Il [!UICONTROL Anomaly Detection] menu è disponibile solo quando si seleziona la granularità Giorno. I precedenti 30 giorni di dati vengono utilizzati come periodo di formazione per i dati statistici, indipendentemente dall'intervallo di date selezionato.

1. Dopo aver configurato gli intervalli di date, fai clic su **[!UICONTROL Next]**.

   Passaggio 1. Nella Richiesta guidata: Passaggio 2 di 2, aggiungi una metrica, ad esempio **[!UICONTROL Visits]**.

   Passaggio 1. Per la metrica aggiunta, fai clic sul **[!UICONTROL None]** collegamento.

   ![Risultato passaggio](assets/anomaly_select.png)

1. Seleziona **[!UICONTROL Anomaly Detection]** &gt; **[!UICONTROL `<selection>`]**.

   ![Informazioni sul passaggio](assets/anomaly_visit.png)

   Quando si seleziona una di queste opzioni, il sistema crea copie del rilevamento delle anomalie della metrica originale. Ad esempio, per la metrica Visita, al [!UICONTROL Metric] gruppo viene aggiunta una metrica Visita Bound inferiore.
1. Fate clic su **[!UICONTROL Finish]** e selezionate la cella da restituire in Excel.

   Consulta Rilevamento delle [anomalie](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) per le definizioni.
