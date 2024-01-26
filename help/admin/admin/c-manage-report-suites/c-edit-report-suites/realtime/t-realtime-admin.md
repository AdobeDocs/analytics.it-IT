---
description: Passaggi amministrativi per la configurazione di rapporti in tempo reale.
title: Configurazione rapporti in tempo reale
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: b8efacacf7fca792b4a4fa41dd3f9d6ac1448578
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 2%

---

# Configurazione rapporti in tempo reale

Passaggi amministrativi per la configurazione di rapporti in tempo reale.

L’impostazione di rapporti in tempo reale in Adobe Analytics consiste nel selezionare la suite di rapporti e configurarne fino a 3. Per impostazione predefinita, tutti gli utenti hanno accesso ai rapporti in tempo reale.

1. Seleziona la suite di rapporti per la quale desideri abilitare i rapporti in tempo reale.

   Accedi a **[!UICONTROL Analytics]** > **[!UICONTROL Reports]** > **[!UICONTROL View All Reports > Site Metrics]** > **[!UICONTROL Real-Time]** e seleziona la suite di rapporti dal menu a discesa in alto:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/report_suite_selector.png)

   Se tenti di visualizzare rapporti in tempo reale per una suite di rapporti che non è stata impostata per il reporting in tempo reale, viene visualizzato un messaggio che ti consente di impostare la suite di rapporti.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/rep_suite_not_set_up.png)

1. Clic **[!UICONTROL Configure]** (icona ingranaggio) per eseguire [!UICONTROL Report Suite Manager].

   (disponibile anche in **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.)

1. Attiva **[!UICONTROL Enable Real-Time]** impostazione.
1. Imposta la raccolta dati in tempo reale per un massimo di tre rapporti, con una metrica e tre dimensioni o classificazioni per rapporto.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   Per informazioni sulle metriche e sulle dimensioni in tempo reale supportate, consulta [Metriche e Dimension supportati](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Se hai creato delle classificazioni, queste vengono visualizzate rientrate sotto la dimensione per la quale sono definite:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >Per un singolo rapporto in tempo reale, al momento non è supportata l’abilitazione di dimensioni duplicate, anche se per ogni dimensione è selezionata una classificazione diversa.

   Per ulteriori informazioni sulle classificazioni, consulta [Informazioni sulle classificazioni](/help/components/classifications/c-classifications.md).

   >[!NOTE]
   >
   >Alcune dimensioni, come &quot;Parola chiave di ricerca&quot; o &quot;Prodotto&quot;, non persistono in tempo reale come altrove in Adobe Analytics. Quando selezioni una metrica non persistente, viene visualizzato questo avviso:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

   Dopo questa configurazione iniziale del rapporto, l’inizio dello streaming dei dati può richiedere fino a 20 minuti. Da quel momento in poi, i dati sono immediatamente disponibili.

1. Per visualizzare il rapporto in tempo reale, vai a:

   **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Real-Time]**.

