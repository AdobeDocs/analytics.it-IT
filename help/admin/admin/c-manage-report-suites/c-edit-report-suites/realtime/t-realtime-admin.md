---
description: Passaggi amministrativi per la configurazione di rapporti in tempo reale.
title: Configurazione rapporti in tempo reale
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
source-git-commit: f1dde3a475fe1276fd9abbe1bdafd6723701f2cb
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 4%

---

# Configurazione rapporti in tempo reale

Passaggi amministrativi per la configurazione di rapporti in tempo reale.

L’impostazione di rapporti in tempo reale in Adobe Analytics consiste nel selezionare la suite di rapporti e configurarne fino a 3. Per impostazione predefinita, tutti gli utenti hanno accesso ai rapporti in tempo reale.

1. Seleziona la suite di rapporti per la quale desideri abilitare i rapporti in tempo reale.

   Passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]**.

1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.

1. Imposta la raccolta dati in tempo reale per un massimo di tre rapporti, con una metrica e tre dimensioni o classificazioni per rapporto.

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/real_time_admin.png)

   Per informazioni sulle metriche e dimensioni in tempo reale supportate, vedere [Metriche e Dimension supportati](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/realtime-metrics.md).

   Se hai creato delle classificazioni, queste vengono visualizzate rientrate sotto la dimensione per la quale sono definite:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >Per un singolo rapporto in tempo reale, al momento non è supportata l’abilitazione di dimensioni duplicate, anche se per ogni dimensione è selezionata una classificazione diversa.

   Per ulteriori informazioni sulle classificazioni, vedere [Informazioni sulle classificazioni](/help/components/classifications/c-classifications.md).

   >[!NOTE]
   >
   >Alcune dimensioni, come &quot;Parola chiave di ricerca&quot; o &quot;Prodotto&quot;, non persistono in tempo reale come altrove in Adobe Analytics. Quando selezioni una metrica non persistente, viene visualizzato questo avviso:

   ![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/realtime/assets/warning_dimensions.png)

1. Fai clic su **[!UICONTROL Save]**.

   Dopo questa configurazione iniziale del rapporto, l’inizio dello streaming dei dati può richiedere fino a 20 minuti. Da quel momento in poi, i dati sono immediatamente disponibili.

1. Per visualizzare il rapporto in tempo reale, vai a:

   **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Real-Time]**.

