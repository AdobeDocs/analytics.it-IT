---
title: Implementare Adobe Analytics con Adobe Experience Platform Edge
description: Panoramica dell’utilizzo di dati XDM da Experience Platform in Adobe Analytics
exl-id: 7d8de761-86e3-499a-932c-eb27edd5f1a3
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 9d9212313f54e4b44c5341754942ac0e0c78b84c
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 35%

---

# Implementare Adobe Analytics con Adobe Experience Platform Edge

Adobe Experience Platform Edge consente di inviare dati destinati a più prodotti a una posizione centralizzata. Experience Edge inoltra le informazioni appropriate ai prodotti desiderati. Questo concetto consente di consolidare le attività di implementazione, in particolare per quanto riguarda più soluzioni di dati.

Adobe offre tre modi principali per inviare dati a Experience Edge:

* **[Adobe Experience Platform Web SDK](web-sdk/overview.md)**: utilizza l’estensione Web SDK in raccolta dati Adobe Experience Platform per inviare dati a Edge.
* **[Adobe Experience Platform Mobile SDK](mobile-sdk/overview.md)**: utilizza l’estensione Mobile SDK in raccolta dati Adobe Experience Platform per inviare dati a Edge.
* **[API server di rete Edge di Adobe Experience Platform](server-api/overview.md)**: invia i dati direttamente a Edge tramite un’API.



## Gestione dei dati Experience Edge in Adobe Analytics

I dati inviati a Experience Edge devono essere conformi agli schemi basati su [XDM (Experience Data Model)](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=it). XDM offre flessibilità nei campi definiti come parte degli eventi. Nel momento in cui gli eventi raggiungono Adobe Analytics, vengono tradotti in dati più strutturati che Adobe Analytics può gestire: visualizzazioni di pagina o eventi di collegamento.

XDM stesso non prescrive come definire le visualizzazioni di pagina o gli eventi di collegamento, né indica ad Adobe Analytics come trattare il suo payload. Ad esempio, alcuni campi XDM predefiniti che sembrano correlati alle visualizzazioni di pagina o agli eventi di collegamento, come `eventType`, `web.webPageDetails.pageViews`, o `web.webInteraction.linkEvents` sono completamente indipendenti dall’implementazione e non hanno alcuna rilevanza per Adobe Analytics.

Per gestire correttamente le visualizzazioni di pagina e gli eventi di collegamento, la logica seguente viene applicata ai dati inviati alla rete Adobe Experience Edge e inoltrati ad Adobe Analytics.

| Il payload XDM contiene... | Adobe Analytics: |
|---|---|
| `web.webPageDetails.name` o `web.webPageDetails.URL` e no `web.webInteraction.type` | considera payload a **visualizzazione pagina** |
| `web.webInteraction.type` e (`web.webInteraction.name` o `web.webInteraction.url`) | considera payload a **evento collegamento** |
| `web.webInteraction.type` e (`web.webPageDetails.name` o `web.webPageDetails.url`) | considera payload a **evento collegamento** <br/>`web.webPageDetails.name` e `web.webPageDetails.URL` sono impostati su `null` |
| no `web.webInteraction.type` e (no `webPageDetails.name` e no `web.webPageDetails.URL`) | elimina il payload e ignora i dati |

{style="table-layout:auto"}

Consulta la [Gruppo di campi schema Estensione completa Adobe Analytics ExperienceEvent](https://experienceleague.adobe.com/docs/experience-platform/xdm/field-groups/event/analytics-full-extension.html?lang=en) per ulteriori informazioni.
