---
title: Implementare Adobe Analytics con Adobe Experience Platform Edge
description: Panoramica dell’utilizzo di dati XDM da Experience Platform in Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 914b822aae659d1d0f0b8a98480090ead99e102a
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 100%

---

# Implementare Adobe Analytics con la rete Edge di Adobe Experience Platform

La rete Edge di Adobe Experience Platform consente di inviare dati destinati a più prodotti a una posizione centralizzata. La rete Edge inoltra le informazioni appropriate ai prodotti desiderati. Questo concetto consente di consolidare le attività di implementazione, in particolare per quanto riguarda più soluzioni di dati.

Adobe offre tre modi principali per inviare dati alla rete Edge:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: utilizza l’estensione Web SDK in raccolta dati Adobe Experience Platform per inviare dati a Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: utilizza l’estensione Mobile SDK in raccolta dati Adobe Experience Platform per inviare dati a Edge.
* **[API server della rete Edge di Adobe Experience Platform](server-api/overview.md)**: invia i dati direttamente a Edge tramite un’API.



## Gestione dei dati della rete Edge in Adobe Analytics

I dati inviati alla rete Edge di Adobe Experience Platform possono essere in due formati:

* Oggetto XDM: conforme agli schemi basati su [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it). XDM offre flessibilità nei campi definiti come parte degli eventi. Quando gli eventi raggiungono Adobe Analytics, vengono tradotti in un formato che Adobe Analytics è in grado di gestire.
* Oggetto dati: invia dati alla rete Edge utilizzando campi specifici mappati ad Adobe Analytics. La rete Edge rileva la presenza di questi campi e li inoltra ad Adobe Analytics senza la necessità di conformarsi a uno schema.


La rete Edge utilizza la seguente logica per determinare le visualizzazioni di pagina e gli eventi di collegamento di Adobe Analytics

| Il payload XDM contiene... | Adobe Analytics... |
|---|---|
| `web.webPageDetails.name` o `web.webPageDetails.URL` e non `web.webInteraction.type` | considera il payload una **visualizzazione di pagina** |
| `web.webInteraction.type` e (`web.webInteraction.name` o `web.webInteraction.url`) | considera il payload un **evento collegamento** |
| `web.webInteraction.type` e (`web.webPageDetails.name` o `web.webPageDetails.url`) | considera il payload un **evento collegamento** <br/>`web.webPageDetails.name` e `web.webPageDetails.URL` impostato su `null` |
| non `web.webInteraction.type` e (non `webPageDetails.name` e non `web.webPageDetails.URL`) | elimina il payload e ignora i dati |

{style="table-layout:auto"}

Per ulteriori informazioni, consulta [Gruppo di campi schema di estensione completo di Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=it).
