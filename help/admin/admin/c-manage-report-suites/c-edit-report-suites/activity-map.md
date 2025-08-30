---
description: Abilita le dimensioni in modo che Activity Map possa raccogliere dati.
title: Rapporti di Activity Map
feature: Admin Tools
exl-id: 9300c12e-3ade-4850-8a22-cba61b35ca67
source-git-commit: 24101efe2b860734c9d176ba8be8f17e26429442
workflow-type: tm+mt
source-wordcount: '142'
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
