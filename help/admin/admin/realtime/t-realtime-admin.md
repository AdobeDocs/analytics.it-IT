---
description: Passaggi amministrativi per l’impostazione di rapporti in tempo reale.
seo-description: Passaggi amministrativi per l’impostazione di rapporti in tempo reale.
seo-title: Configurazione rapporti in tempo reale
solution: Analytics
title: Configurazione rapporti in tempo reale
topic: Strumenti di amministrazione
uuid: f48692a0-77c0-4ee4-b3ec-eaa842d06ac8
translation-type: tm+mt
source-git-commit: 45e3330adb562ec795d287ae1c1fa6b03a2b2a31

---


# Configurazione rapporti in tempo reale

Passaggi amministrativi per l’impostazione di rapporti in tempo reale.

L'impostazione di report in tempo reale in Reporting e analisi consiste nella selezione della suite di report e nella configurazione di 3 report per essa.

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

   Per informazioni sulle metriche e dimensioni in tempo reale supportate, consultate Metriche e dimensioni [](/help/admin/admin/realtime/realtime-metrics.md)supportate.

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
