---
description: Passaggi amministrativi per l’impostazione di rapporti in tempo reale.
title: Configurare rapporti in tempo reale
topic: Admin tools
uuid: a2c3c515-55f2-4c64-ac92-a86d75e78a86
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 2%

---


# Configurare rapporti in tempo reale

Passaggi amministrativi per l’impostazione di rapporti in tempo reale.

L&#39;impostazione di rapporti in tempo reale all&#39;interno [!UICONTROL Reports & Analytics] consiste nella selezione della suite di rapporti e nella configurazione di 3 rapporti per essa.

1. Selezionate la suite di rapporti per la quale desiderate abilitare i rapporti in tempo reale.

   Andate a **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** > **[!UICONTROL View All Reports > Site Metrics]** > **[!UICONTROL Real-Time]** e selezionate la suite di rapporti dall&#39;elenco a discesa in alto:

   ![](assets/report_suite_selector.png)

   Se provate a visualizzare i rapporti in tempo reale per una suite di rapporti che non è stata configurata per il reporting in tempo reale, viene visualizzato un messaggio che consente di impostare la suite di rapporti.

   ![](assets/rep_suite_not_set_up.png)

1. Fate clic **[!UICONTROL Configure]** (icona a forma di ingranaggio) per eseguire il [!UICONTROL Report Suite Manager].

   (Disponibile anche in **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.)

1. Accendere l&#39; **[!UICONTROL Enable Real-Time]** impostazione.
1. Configurate la raccolta dati in tempo reale per un massimo di tre report, con una metrica e tre dimensioni o classificazioni per report.

   ![](assets/real_time_admin.png)

   Per informazioni sulle metriche e dimensioni in tempo reale supportate, consultate Metriche e Dimension [](/help/components/c-real-time-reporting/realtime-metrics.md)supportati.

   Se avete creato delle classificazioni, queste appaiono rientrate sotto la dimensione per la quale sono definite:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Per un singolo rapporto in tempo reale, al momento non è supportato l&#39;abilitazione di dimensioni duplicate, anche se per ogni dimensione è selezionata una classificazione diversa.

   Per ulteriori informazioni sulle classificazioni, vedere [Informazioni sulle classificazioni](/help/components/classifications/c-classifications.md).

   >[!NOTE]
   >
   >Alcune dimensioni, come &quot;Search Keyword&quot; o &quot;Product&quot;, non persistono in tempo reale come accade in  Adobe Analytics. Quando selezionate una metrica non persistente, viene visualizzato questo avviso:

   ![](assets/warning_dimensions.png)

1. Click **[!UICONTROL Save]** or **[!UICONTROL Save and View Report]**.

   Dopo questa configurazione iniziale del report, potrebbero essere necessari fino a 20 minuti per iniziare lo streaming dei dati. Da quel momento in poi, i dati saranno immediatamente disponibili. Per informazioni sulla visualizzazione di rapporti in tempo reale, consultate [Eseguire un rapporto](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/t-running-report-types.html)in tempo reale.

1. Per impostazione predefinita, tutti gli utenti hanno accesso ai report in tempo reale.
