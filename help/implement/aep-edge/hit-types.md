---
title: Tipi di eventi di Edge Network in Adobe Analytics
description: Come Adobe Analytics interpreta gli eventi ricevuti da Edge Network.
feature: Implementation Basics
role: Admin, Developer
source-git-commit: 8d369bd3be3ae9c075e490e108666728a2cff5dc
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 28%

---

# Tipi di eventi di Edge Network in Adobe Analytics

Adobe Analytics tratta gli hit in modo diverso a seconda delle funzioni chiamate in AppMeasurement. Ad esempio, [`s.t`](/help/implement/vars/functions/t-method.md) e [`s.tl`](/help/implement/vars/functions/tl-method.md) includono o omettono determinate dimensioni e incrementano le visualizzazioni di pagina in modo diverso. Adobe Experience Platform contiene solo il comando `sendEvent`. Le proprietà specifiche all&#39;interno del payload `xdm` determinano il modo in cui tali dati vengono interpretati in Adobe Analytics.

Edge Network utilizza la seguente logica per determinare le visualizzazioni di pagina e gli eventi di collegamento di Adobe Analytics:

| Il payload XDM contiene... | Adobe Analytics... |
|---|---|
| `xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.URL` e non `xdm.web.webInteraction.type` | considera il payload una **visualizzazione di pagina** |
| `xdm.eventType = web.webPageDetails.pageViews` | considera il payload una **visualizzazione di pagina** |
| `xdm.web.webInteraction.type` e (`xdm.web.webInteraction.name` o `xdm.web.webInteraction.url`) | considera il payload un **evento collegamento** |
| `xdm.web.webInteraction.type` e (`xdm.web.webPageDetails.name` o `xdm.web.webPageDetails.url`) | considera il payload un **evento collegamento** <br/>Imposta anche `xdm.web.webPageDetails.name` e `xdm.web.webPageDetails.URL` su `null` |
| non `xdm.web.webInteraction.type` e (non `xdm.webPageDetails.name` e non `xdm.web.webPageDetails.URL`) | elimina il payload e ignora i dati |

Oltre a differenziare le visualizzazioni di pagina e i clic sui collegamenti, è presente la logica seguente che determina se alcuni eventi sono classificati come A4T o vengono scartati.

| Il payload XDM contiene... | Adobe Analytics... |
| --- | --- |
| `xdm.eventType = display` o <br/>`xdm.eventType = decisioning.propositionDisplay` o <br/>`xdm.eventType = personalization.request` o <br/>`xdm.eventType = decisioning.propositionFetch` e `xdm._experience.decisioning` | considera il payload una chiamata **A4T**. |
| `xdm.eventType = display` o <br/>`xdm.eventType = decisioning.propositionDisplay` o <br/>`xdm.eventType = personalization.request` o <br/>`xdm.eventType = decisioning.propositionFetch` e nessun `xdm._experience.decisioning` | elimina il payload e ignora i dati |
| `xdm.eventType = click` o `xdm.eventType = decisioning.propositionInteract` e `xdm._experience.decisioning` e nessun `web.webInteraction.type` | considera il payload una chiamata **A4T**. |
| `xdm.eventType = click` o `xdm.eventType = decisioning.propositionInteract` e nessun `xdm._experience.decisioning` e nessun `web.webInteraction.type` | rilascia il payload e ignora i dati. |

Per ulteriori informazioni, consulta [Gruppo di campi schema di estensione completo di Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/analytics-full-extension).
