---
description: Passaggi amministrativi per l’impostazione di rapporti in tempo reale.
seo-description: Passaggi amministrativi per l’impostazione di rapporti in tempo reale.
seo-title: Configurare rapporti in tempo reale
solution: Analytics
title: Configurare rapporti in tempo reale
topic: Strumenti di amministrazione
uuid: a2c3c515-55f2-4c64-ac92-a86d75e78a86
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Configurare rapporti in tempo reale

Passaggi amministrativi per l’impostazione di rapporti in tempo reale.

L'impostazione di rapporti in tempo reale all'interno [!UICONTROL Reports & Analytics] consiste nella selezione della suite di rapporti e nella configurazione di 3 rapporti per essa.

1. Selezionate la suite di rapporti per la quale desiderate abilitare i rapporti in tempo reale.

   Andate a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Reports]** &gt; **[!UICONTROL View All Reports > Site Metrics]** &gt; **[!UICONTROL Real-Time]** e selezionate la suite di rapporti dall'elenco a discesa in alto:

   ![](assets/report_suite_selector.png)

   Se provate a visualizzare i rapporti in tempo reale per una suite di rapporti che non è stata configurata per il reporting in tempo reale, viene visualizzato un messaggio che consente di impostare la suite di rapporti.

   ![](assets/rep_suite_not_set_up.png)

1. Fate clic **[!UICONTROL Configure]** (icona a forma di ingranaggio) per eseguire il [!UICONTROL Report Suite Manager].

   (Disponibile anche in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin > Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Real-Time]**.)

1. Accendere l' **[!UICONTROL Enable Real-Time]** impostazione.
1. Configurate la raccolta dati in tempo reale per un massimo di tre report, con una metrica e tre dimensioni o classificazioni per report.

   ![](assets/real_time_admin.png)

   Per informazioni sulle metriche e dimensioni in tempo reale supportate, consultate Metriche e dimensioni [](/help/components/c-real-time-reporting/realtime-metrics.md)supportate.

   Se avete creato delle classificazioni, queste appaiono rientrate sotto la dimensione per la quale sono definite:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Per un singolo rapporto in tempo reale, al momento non siamo in grado di abilitare dimensioni duplicate, anche se per ogni dimensione è selezionata una classificazione diversa.

   Per ulteriori informazioni sulle classificazioni, vedere [Informazioni sulle classificazioni](/help/components/c-classifications2/c-classifications.md).

   >[!NOTE]
   >
   >Alcune dimensioni, come "Search Keyword" o "Product", non persistono in tempo reale come accade in altre aree di Adobe Analytics. Quando selezionate una metrica non persistente, viene visualizzato questo avviso:

   ![](assets/warning_dimensions.png)

1. Fai clic su **[!UICONTROL Save]** o **[!UICONTROL Save and View Report]**.

   Dopo questa configurazione iniziale del report, potrebbero essere necessari fino a 20 minuti per iniziare lo streaming dei dati. Da quel momento in poi, i dati saranno immediatamente disponibili. Per informazioni sulla visualizzazione di rapporti in tempo reale, consultate [Eseguire un rapporto](https://marketing.adobe.com/resources/help/en_US/sc/user/reports_realtime.html)in tempo reale.

1. Per impostazione predefinita, tutti gli utenti hanno accesso ai report in tempo reale.
