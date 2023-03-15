---
description: Descrive come impostare le autorizzazioni e quali dimensioni sono disponibili in Analytics.
title: Generazione di rapporti Activity Map in Analytics
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 8%

---

# Generazione di rapporti Activity Map in Analytics

Descrive come impostare le autorizzazioni e quali dimensioni sono disponibili in Analytics.

## Impostare le autorizzazioni {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Prima che gli utenti possano creare rapporti sulle dimensioni Activity Map, è necessario che l’amministratore

* [Aggiungere utenti al gruppo di accesso per Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* Aggiungi le suite di rapporti per le quali vuoi avere accesso a questo gruppo. Passa a **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** > **[!UICONTROL Groups]** > **[!UICONTROL Activity Map Access]** > **[!UICONTROL Edit]**.
* Personalizzare l’accesso degli utenti alle dimensioni. Consulta la sezione successiva.

## Dimensioni di Analytics Activity Map {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

È possibile [personalizzare l’accesso degli utenti alle dimensioni](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) a livello granulare. Di seguito sono elencate le dimensioni Activity Map disponibili in Analytics:

| Dimensione | Descrizione |
|---|---|
| Pagina della Activity Map | Elenca le pagine in cui è stato fatto clic su un collegamento. |
| Regione Activity Map | Elenca tutte le aree di collegamento raccolte in tutto il sito Web. Tieni presente che se un’area viene visualizzata su più pagine, la metrica verrà aggregata su tutte le sue pagine. |
| Collegamenti Activity Map | Elenca tutti i collegamenti raccolti nell&#39;intero sito Web. |
| Collegamenti Activity Map e area geografica | Elenca tutti i collegamenti raccolti con la rispettiva area geografica nell&#39;intero sito Web. |
| XY ACTIVITY MAP | Non utilizzato |

* Queste dimensioni devono essere disponibili in Analysis Workspace, Reports &amp; Analytics e Report Builder, purché l’implementazione di Analytics sia [abilitato per l’Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics, vai a **[!UICONTROL View All Reports]** > **[!UICONTROL Activity Map]**.

* Per cercare un collegamento e un’area geografica per una pagina specifica, è sufficiente creare un raggruppamento dalla pagina Activity Map desiderata a quella Activity Map.
