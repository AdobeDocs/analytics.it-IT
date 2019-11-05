---
description: Adobe utilizza un cookie per tenere traccia di browser/dispositivi univoci.
keywords: Implementazione di Analytics
seo-description: Adobe utilizza un cookie per tenere traccia di browser/dispositivi univoci.
seo-title: Identificare visitatori unici
solution: Analytics
subtopic: Visitatori
title: Identificare visitatori unici
topic: Sviluppatore e implementazione
uuid: ed4dee75-ecfb-4715-8122-461983c7dd8f
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Identificare visitatori unici

Adobe utilizza un cookie per tenere traccia di browser/dispositivi univoci.

## Ordine di identificazione degli ID visitatore in Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics offre diversi metodi per identificare i visitatori. Nella tabella seguente sono elencati i diversi modi in cui un visitatore può essere identificato in Analytics (in ordine di preferenza):

| Ordine | Parametro query (metodo di raccolta) | Presente se |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](/help/implement/js-implementation/c-unique-visitors/visid-custom.md) | s.visitorID è impostato |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](/help/implement/js-implementation/c-unique-visitors/visid-analytics.md) | Il visitatore aveva un cookie s_vi esistente prima dell’implementazione del servizio ID visitatore, oppure era configurato un periodo di tolleranza ID visitatore. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ impostato dal servizio ID visitatori di Experience Cloud)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | Il browser del visitatore accetta i cookie (di prime parti) |
| ![](assets/step4_icon.png) | [fid (cookie di fallback in H.25.3 o successivo, o in AppMeasurement per JavaScript)](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md) | Il browser del visitatore accetta i cookie (di prime parti) |
| ![](assets/step5_icon.png) | [Indirizzo IP, agente utente, indirizzo IP gateway](/help/implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | Il browser del visitatore non accetta i cookie. |

In molti scenari potrebbero essere presenti due o tre ID diversi in una chiamata, ma Analytics utilizza il primo ID presente nella tabella precedente come ID visitatore ufficiale. Ad esempio, se imposti un ID visitatore personalizzato (incluso nel parametro di query “vid”), questo ID verrà usato prima degli altri ID visualizzati per lo stesso hit.

> [!NOTE] Ogni ID visitatore di Analytics è associato a un profilo visitatore sui server Adobe. I profili dei visitatori vengono eliminati dopo almeno 13 mesi di inattività, indipendentemente dalla scadenza dei cookie dell’ID visitatore.
