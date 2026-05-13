---
description: Passaggi amministrativi per la configurazione di rapporti in tempo reale.
title: Configurare rapporti in tempo reale
feature: Real-time
exl-id: 9e7fc67c-71d5-465a-9553-5bb7e02a9bfd
TQID: https://experienceleague.adobe.com/wmZj-F8P4ectiMUnpy9yYT-pviys2m2aBGAVtP5kNNI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 266
ht-degree: 3%

---

# Configurare rapporti in tempo reale

Le informazioni seguenti contengono passaggi amministrativi per la configurazione di rapporti in tempo reale.

Questa consiste nel selezionare la suite di rapporti e configurarne fino a 3 per essa.

1. Seleziona la suite di rapporti per la quale desideri abilitare i rapporti in tempo reale.

   1. In Analysis Workspace, seleziona la scheda [!UICONTROL **Workspace**], quindi seleziona [!UICONTROL **Rapporti**] > [!UICONTROL **Coinvolgimento**] > **[!UICONTROL Real-Time]**.

   1. Seleziona la suite di rapporti dal menu a discesa in alto:

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report_suite_selector.png)

      Se tenti di visualizzare rapporti in tempo reale per una suite di rapporti che non è stata impostata per il reporting in tempo reale, viene visualizzato un messaggio che ti consente di impostare la suite di rapporti.

      ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/rep_suite_not_set_up.png)

1. Selezionare **[!UICONTROL Configure]** per eseguire [!UICONTROL Report Suite Manager].

   (Disponibile anche in **[!UICONTROL Analytics]** > **[!UICONTROL Admin > Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Real-Time]**.)

1. Attiva l&#39;impostazione **[!UICONTROL Enable Real-Time]**.
1. Imposta la raccolta dati in tempo reale per un massimo di tre rapporti, con una metrica e tre dimensioni o classificazioni per rapporto.

   ![](assets/real_time_admin.png)

   Per informazioni sulle metriche e dimensioni in tempo reale supportate, vedere [Metriche e dimensioni supportate](/help/admin/tools/manage-rs/edit-settings/realtime/realtime-metrics.md).

   Se hai creato delle classificazioni, queste vengono visualizzate rientrate sotto la dimensione per la quale sono definite:

   ![](assets/classifications.png)

   >[!NOTE]
   >
   >Per un singolo rapporto in tempo reale, al momento non è supportata l’abilitazione di dimensioni duplicate, anche se per ogni dimensione è selezionata una classificazione diversa.

   >[!NOTE]
   >
   >Alcune dimensioni, come &quot;Parola chiave di ricerca&quot; o &quot;Prodotto&quot;, non persistono in tempo reale come altrove in Adobe Analytics. Quando selezioni una metrica non persistente, viene visualizzato questo avviso:

   ![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/warning_dimensions.png)

1. Seleziona **[!UICONTROL Save]** (Mostra origine dati) o **[!UICONTROL Save and View Report]** (Blocca selezione).

   Dopo questa configurazione iniziale del rapporto, l’inizio dello streaming dei dati può richiedere fino a 20 minuti. Da quel momento in poi, i dati sono immediatamente disponibili.

1. Per impostazione predefinita, tutti gli utenti hanno accesso ai rapporti in tempo reale.
