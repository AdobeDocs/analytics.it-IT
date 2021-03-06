---
description: Descrive come impostare le autorizzazioni e quali dimensioni sono disponibili in Analytics.
title: Generazione di rapporti Activity Map in Analytics
uuid: 057c6ab2-aa06-4779-ac16-f9b367d9ea43
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 9%

---

# Generazione di rapporti Activity Map in Analytics

Descrive come impostare le autorizzazioni e quali dimensioni sono disponibili in Analytics.

## Impostare le autorizzazioni {#section_BDCD9914B31A4066A50D23DDDF1ABB37}

Prima che gli utenti possano creare rapporti sulle dimensioni di Activity Map, in qualità di amministratore devi

* [Aggiungi utenti al gruppo](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md) di accesso di Activity Map.
* Aggiungi suite di rapporti a cui desideri accedere per questo gruppo. Passa a **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL User management]** > **[!UICONTROL Groups]** > **[!UICONTROL Activity Map Access]** > **[!UICONTROL Edit]**.
* Personalizza l’accesso dell’utente alle dimensioni. Consulta la sezione successiva.

## Dimensioni di Analytics Activity Map {#section_9395A7A5585F4ABE9F7C6CD0124B02A5}

Puoi [personalizzare l’accesso utente alle dimensioni](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) a livello granulare. Di seguito sono elencate le dimensioni di Activity Map disponibili in Analytics:

| Dimensione | Descrizione |
|---|---|
| Activity Map Pagina | Elenca le pagine su cui è stato fatto clic su un collegamento. |
| Area geografica di Activity Map | Elenca tutte le aree di collegamento raccolte nell’intero sito web. Se una regione viene visualizzata su più pagine, la metrica viene aggregata in tutte le relative pagine. |
| Collegamenti Activity Map | Elenca tutti i collegamenti raccolti nell&#39;intero sito web. |
| Collegamenti e area geografica di Activity Map | Elenca tutti i collegamenti raccolti con la relativa area geografica nell’intero sito web. |
| Activity Map XY | Non utilizzato |

* Queste dimensioni devono essere disponibili in Analysis Workspace, Reports &amp; Analytics e nel Report Builder, purché l’implementazione di Analytics sia [abilitata per Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-getting-started-admins/activitymap-enable.md).
* In Reports &amp; Analytics passa a **[!UICONTROL View All Reports]** > **[!UICONTROL Activity Map]**.

* Per cercare un collegamento e un’area geografica per una pagina specifica, è sufficiente creare un raggruppamento dalla pagina Activity Map desiderata in Collegamenti e area geografica di Activity Map.
