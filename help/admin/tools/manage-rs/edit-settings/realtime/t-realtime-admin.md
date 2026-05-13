---
description: Passaggi amministrativi per la configurazione di rapporti in tempo reale.
title: Configurazione rapporti in tempo reale
feature: Real-time
exl-id: e039ed67-3694-40fc-a4d9-3cb576e0535c
TQID: https://experienceleague.adobe.com/HTu1UvUUIGK0SzAQWEFBclV-P1JaPCJUp6j5MiYC3A0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 212
ht-degree: 5%

---

# Configurazione rapporti in tempo reale

Passaggi amministrativi per la configurazione di rapporti in tempo reale.

L’impostazione di rapporti in tempo reale in Adobe Analytics consiste nel selezionare la suite di rapporti e configurarne fino a 3. Per impostazione predefinita, tutti gli utenti hanno accesso ai rapporti in tempo reale.

1. Seleziona la suite di rapporti per la quale desideri abilitare i rapporti in tempo reale.

   Passa a **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]**.

1. Fai clic su **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.

1. Imposta la raccolta dati in tempo reale per un massimo di tre rapporti, con una metrica e tre dimensioni o classificazioni per rapporto.

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/real_time_admin.png)

   Per informazioni sulle metriche e dimensioni in tempo reale supportate, vedere [Metriche e dimensioni supportate](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   Se hai creato delle classificazioni, queste vengono visualizzate rientrate sotto la dimensione per la quale sono definite:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/classifications.png)

   >[!NOTE]
   >
   >Per un singolo rapporto in tempo reale, al momento non è supportata l’abilitazione di dimensioni duplicate, anche se per ogni dimensione è selezionata una classificazione diversa.

   >[!NOTE]
   >
   >Alcune dimensioni, come &quot;Parola chiave di ricerca&quot; o &quot;Prodotto&quot;, non persistono in tempo reale come altrove in Adobe Analytics. Quando selezioni una metrica non persistente, viene visualizzato questo avviso:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Fai clic su **[!UICONTROL Save]**.

   Dopo questa configurazione iniziale del rapporto, l’inizio dello streaming dei dati può richiedere fino a 20 minuti. Da quel momento in poi, i dati sono immediatamente disponibili.

1. Per visualizzare il rapporto in tempo reale, vai a:

   **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Real-Time]**.

