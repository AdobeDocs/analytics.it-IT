---
description: Abilita le dimensioni in modo che Activity Map possa raccogliere dati.
title: Rapporti di Activity Map
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
TQID: https://experienceleague.adobe.com/GiBhdUMAX5P9zxxDAVUZPcaeKpnezKvDn3MB0g95DH0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 142
ht-degree: 2%

---

# Rapporti di Activity Map

Consente di abilitare le dimensioni da utilizzare con [Activity Map](/help/analyze/activity-map/overview.md).

**[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Seleziona suite di rapporti > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]**

Questa sezione della documentazione si concentra sull’abilitazione delle dimensioni utilizzate da Activity Map. Per ulteriori informazioni sulla sovrapposizione, sulle variabili di implementazione e sulle dimensioni, consulta [Panoramica di Activity Map](/help/analyze/activity-map/overview.md).

Quando si seleziona il pulsante **[!UICONTROL Enable Activity Map Reports]**, vengono create le dimensioni seguenti:

* [[!UICONTROL Activity Map Link]](/help/components/dimensions/activity-map-link.md): nome del collegamento su cui è stato fatto clic.
* [[!UICONTROL Activity Map Region]](/help/components/dimensions/activity-map-region.md): nome dell&#39;area su cui è stato fatto clic.
* [[!UICONTROL Activity Map Page]](/help/components/dimensions/activity-map-page.md): nome della pagina al momento del clic sul collegamento.
* [[!UICONTROL Activity Map Link By Region]](/help/components/dimensions/activity-map-link-by-region.md): valore concatenato di Activity Map Link e Activity Map Region.

Una volta abilitata, la tua implementazione può iniziare a inviare dati a queste dimensioni per l&#39;utilizzo in [Analysis Workspace](/help/analyze/analysis-workspace/home.md) e nella [sovrapposizione estensione browser](/help/analyze/activity-map/overlay/overview.md).

>[!NOTE]
>
>Quando abiliti Activity Map per una suite di rapporti, questa viene abilitata in modo permanente senza alcun modo per essere disabilitata in futuro.
