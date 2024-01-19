---
description: Descrive come impostare le autorizzazioni e quali dimensioni sono disponibili in Analytics.
title: Generazione di rapporti Activity Map in Analytics
feature: Activity Map
role: User, Admin
exl-id: 8d7be302-bdfc-4370-b8f0-ab1af1e439ca
source-git-commit: a979fc8787fa96f8fa8317996ac66341a6f54354
workflow-type: tm+mt
source-wordcount: '233'
ht-degree: 8%

---

# Generazione di rapporti Activity Map in Analytics

Descrive come impostare le autorizzazioni e quali dimensioni sono disponibili in Analytics.

## Impostare le autorizzazioni {#permissions}

Prima che gli utenti possano creare rapporti sulle dimensioni Activity Map, è necessario che l’amministratore

* [Aggiungere utenti al profilo di prodotto Activity Map Access](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* Personalizzare l’accesso degli utenti alle dimensioni. Consulta la sezione successiva.

## Dimensioni di Analytics Activity Map {#dimensions}

È possibile [personalizzare l’accesso degli utenti alle dimensioni](https://experienceleague.adobe.com/docs/analytics/admin/user-product-management/customize-report-access/groups-dimensions.html) a livello granulare. Di seguito sono elencate le dimensioni Activity Map disponibili in Analytics:

| Dimensione | Descrizione |
|---|---|
| Pagina della Activity Map | Elenca le pagine in cui è stato fatto clic su un collegamento. |
| Regione Activity Map | Elenca tutte le aree di collegamento raccolte in tutto il sito Web. Tieni presente che se un’area viene visualizzata su più pagine, la metrica verrà aggregata su tutte le sue pagine. |
| Collegamenti Activity Map | Elenca tutti i collegamenti raccolti nell&#39;intero sito Web. |
| Collegamenti Activity Map e area geografica | Elenca tutti i collegamenti raccolti con la rispettiva area geografica nell&#39;intero sito Web. |
| XY ACTIVITY MAP | Non utilizzato |

* Queste dimensioni devono essere disponibili in Analysis Workspace e Report Builder, purché l’implementazione di Analytics sia [abilitato per l’Activity Map](/help/analyze/activity-map/activitymap-getting-started/activitymap-enable.md).
* In Analysis Workspace, richiama le dimensioni relative ad Activitymap in un rapporto.
* Per cercare un collegamento e un’area geografica per una pagina specifica, è sufficiente creare un raggruppamento dalla pagina Activity Map desiderata a quella Activity Map.
