---
title: Implementare Adobe Analytics con Adobe Experience Platform Edge
description: Panoramica dell’utilizzo di dati XDM da Experience Platform in Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 8e701a3da6f04ccf2d7ac3abd10c6df86feb00a7
workflow-type: tm+mt
source-wordcount: '395'
ht-degree: 73%

---

# Implementare Adobe Analytics con la rete Edge di Adobe Experience Platform

La rete Edge di Adobe Experience Platform consente di inviare dati destinati a più prodotti a una posizione centralizzata. La rete Edge inoltra le informazioni appropriate ai prodotti desiderati. Questo concetto consente di consolidare le attività di implementazione, in particolare per quanto riguarda più soluzioni di dati.

Adobe offre tre modi principali per inviare dati alla rete Edge:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: utilizza l’estensione Web SDK in raccolta dati Adobe Experience Platform per inviare dati a Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: utilizza l’estensione Mobile SDK in raccolta dati Adobe Experience Platform per inviare dati a Edge.
* **[API Adobe Experience Platform Edge Network](api/overview.md)**: invia i dati direttamente all&#39;Edge Network utilizzando un&#39;API.

## Gestione dei dati della rete Edge in Adobe Analytics

I dati inviati alla rete Edge di Adobe Experience Platform possono essere in due formati:

* Oggetto XDM: conforme agli schemi basati su [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it). XDM offre flessibilità nei campi definiti come parte degli eventi. Quando gli eventi raggiungono Adobe Analytics, vengono tradotti in un formato che Adobe Analytics è in grado di gestire.
* Oggetto dati: invia dati alla rete Edge utilizzando campi specifici mappati ad Adobe Analytics. La rete Edge rileva la presenza di questi campi e li inoltra ad Adobe Analytics senza la necessità di conformarsi a uno schema.

Edge Network utilizza la seguente logica per determinare le visualizzazioni di pagina e gli eventi di collegamento di Adobe Analytics:

| Il payload XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL` e non `xdm.web.webInteraction.type` | considera il payload una **visualizzazione di pagina** |
| `xdm.eventType = web.webPageDetails.pageViews` | considera il payload una **visualizzazione di pagina** |
| `xdm.web.webInteraction.type` e (`xdm.web.webInteraction.name` o `xdm.web.webInteraction.url`) | considera il payload un **evento collegamento** |
| `xdm.web.webInteraction.type` e (`xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.url`) | considera il payload un **evento collegamento** <br/>Imposta anche `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` su `null` |
| non `xdm.web.webInteraction.type` e (non `xdm.webPageDetails.name` e non `xdm.web.webPageDetails.URL`) | elimina il payload e ignora i dati |

{style="table-layout:auto"}

Oltre a differenziare le visualizzazioni di pagina e i clic sui collegamenti, è presente la logica seguente che determina se alcuni eventi sono classificati come A4T o vengono scartati.

| Il payload XDM contiene... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` o <br/>`xdm.eventType = decisioning.propositionDisplay` o <br/>`xdm.eventType = personalization.request` o <br/>`xdm.eventType = decisioning.propositionFetch` e `xdm._experience.decisioning` | considera il payload una chiamata **A4T**. |
| `xdm.eventType = display` o <br/>`xdm.eventType = decisioning.propositionDisplay` o <br/>`xdm.eventType = personalization.request` o <br/>`xdm.eventType = decisioning.propositionFetch` e nessun `xdm._experience.decisioning` | elimina il payload e ignora i dati |
| `xdm.eventType = click` o `xdm.eventType = decisioning.propositionInteract` e `xdm._experience.decisioning` e nessun `web.webInteraction.type` | considera il payload una chiamata **A4T**. |
| `xdm.eventType = click` o `xdm.eventType = decisioning.propositionInteract` e nessun `xdm._experience.decisioning` e nessun `web.webInteraction.type` | rilascia il payload e ignora i dati. |

{style="table-layout:auto"}

Per ulteriori informazioni, consulta [Gruppo di campi schema di estensione completo di Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=it).
