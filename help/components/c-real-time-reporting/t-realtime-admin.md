---
description: Passaggi amministrativi per la configurazione di rapporti in tempo reale.
title: Configurare rapporti in tempo reale
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 3%

---

# Configurare rapporti in tempo reale

Le informazioni seguenti contengono passaggi amministrativi per la configurazione di rapporti in tempo reale.

Questa consiste nel selezionare la suite di rapporti e configurarne fino a 3 per essa.

1. Seleziona la suite di rapporti per la quale desideri abilitare i rapporti in tempo reale.

   1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**], quindi seleziona [!UICONTROL **Rapporti**] > [!UICONTROL **Coinvolgimento**] > **[!UICONTROL Real-Time]**.

   1. Seleziona la suite di rapporti dal menu a discesa in alto:

      ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/report_suite_selector.png)

      Se tenti di visualizzare rapporti in tempo reale per una suite di rapporti che non è stata impostata per il reporting in tempo reale, viene visualizzato un messaggio che ti consente di impostare la suite di rapporti.

      ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/rep_suite_not_set_up.png)

1. Selezionare **[!UICONTROL Configure]** per eseguire [!UICONTROL Report Suite Manager].

   (Disponibile anche in **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.)

1. Attiva l&#39;impostazione **[!UICONTROL Enable Real-Time]**.
1. Imposta la raccolta dati in tempo reale per un massimo di tre rapporti, con una metrica e tre dimensioni o classificazioni per rapporto.

   ![](assets/real_time_admin.png)

   Per informazioni sulle metriche e dimensioni in tempo reale supportate, vedere [Metriche e dimensioni supportate](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Se hai creato delle classificazioni, queste vengono visualizzate rientrate sotto la dimensione per la quale sono definite:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Per un singolo rapporto in tempo reale, al momento non è supportata l’abilitazione di dimensioni duplicate, anche se per ogni dimensione è selezionata una classificazione diversa.

   >[!NOTE]
   >
   >Alcune dimensioni, come &quot;Parola chiave di ricerca&quot; o &quot;Prodotto&quot;, non persistono in tempo reale come altrove in Adobe Analytics. Quando selezioni una metrica non persistente, viene visualizzato questo avviso:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Seleziona **[!UICONTROL Save]** (Mostra origine dati) o **[!UICONTROL Save and View Report]** (Blocca selezione).

   Dopo questa configurazione iniziale del rapporto, l’inizio dello streaming dei dati può richiedere fino a 20 minuti. Da quel momento in poi, i dati sono immediatamente disponibili. Per informazioni sulla visualizzazione dei report in tempo reale, vedere [Eseguire un report in tempo reale](https://experienceleague.adobe.com/docs/analytics/analyze/reports-analytics/t-running-report-types.html?lang=it).

1. Per impostazione predefinita, tutti gli utenti hanno accesso ai rapporti in tempo reale.
