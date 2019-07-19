---
description: Adobe utilizza un cookie per tenere traccia di browser/dispositivi univoci.
keywords: Implementazione di Analytics
seo-description: Adobe utilizza un cookie per tenere traccia di browser/dispositivi univoci.
seo-title: Identificare visitatori univoci
solution: Analytics
subtopic: Visitatori
title: Identificare visitatori univoci
topic: Sviluppatore e implementazione
uuid: ed 4 dee 75-ecfb -4715-8122-461983 c 7 dd 8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Identificare visitatori univoci

Adobe utilizza un cookie per tenere traccia di browser/dispositivi univoci.

## Ordine di identificazione degli ID visitatore in Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics offre diversi meccanismi per identificare i visitatori. Nella tabella seguente sono elencati i diversi modi in cui un visitatore può essere identificato in Analytics (in ordine di preferenza):

| Ordine | Parametro query (metodo di raccolta) | Presente se |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](../../../implement/js-implementation/c-unique-visitors/visid-custom.md#concept_4A2000F4B6ED41E99CA6118A6D74ECE8) | s.visitorID è impostato |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](../../../implement/js-implementation/c-unique-visitors/visid-analytics.md#concept_74F6B4B9B2FA415AB5D029A1F8F099BC) | Il visitatore aveva un cookie s_ vi esistente prima dell'implementazione del servizio Visitor ID, oppure hai configurato un periodo di tolleranza per ID visitatore. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ impostato dal servizio ID visitatore Experience Cloud)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | Il browser del visitatore accetta i cookie (prime parti) |
| ![](assets/step4_icon.png) | [fid (cookie di fallback in H.25.3 o successivo, o in AppMeasurement per JavaScript)](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#concept_EBCBF9EB390E45A2BA20DB6BE931C505) | Il browser del visitatore accetta i cookie (prime parti) |
| ![](assets/step5_icon.png) | [Indirizzo IP, agente utente, indirizzo IP gateway](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | Il browser del visitatore non accetta i cookie. |

In molti scenari potrebbero essere presenti 2 o 3 ID diversi su una chiamata, ma Analytics utilizzerà il primo ID presente nella tabella precedente come ID visitatore ufficiale. Ad esempio, se imposti un ID visitatore personalizzato (incluso nel parametro di query “vid”), questo ID verrà usato prima degli altri ID visualizzati per lo stesso hit.

>[!NOTE]
>
>Ogni ID visitatore di Analytics è associato a un profilo visitatore sui server Adobe. I profili dei visitatori vengono eliminati dopo almeno 13 mesi di inattività, a prescindere dalla scadenza del cookie ID visitatore.
