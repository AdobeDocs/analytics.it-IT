---
description: nulle
keywords: Feed dati; processo; visitatori; Experience Cloud ID; ID visitatore di analisi; identificare
seo-description: nulle
seo-title: Identificare i visitatori
solution: Analytics
title: Identificare i visitatori
topic: Reports & Analytics
uuid: 2490 b 67 e-a 333-422 d -82 fa-cb 0670 ef 2 e 0 c
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Identificare i visitatori

Analytics provides several mechanisms by which visitors can be identified (listed in [Identifying Visitors](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)). Regardless of the method used to identify a visitor, in data feeds the final visitor ID used by Analytics is split across the `post_visid_high` and `post_visid_low` columns, even when using the Identity Service.

**Per identificare visitatori univoci:**

1. Exclude all rows where `exclude_hit > 0`.
1. Exclude all rows with `hit_source = 5,7,8,9`. 5, 8 e 9 sono righe di riepilogo caricate utilizzando le origini dati. 7 rappresenta i caricamenti delle origini dati ID transazione che non devono essere inclusi nei conteggi dei visitatori e delle visite. See [Hit Source Lookup](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42)
1. Combine `post_visid_high` with `post_visid_low`. All hits across all dates that contain this combination of `post_visid_high` and `post_visid_low` can be considered as coming from same visitor.

If you would like to determine which mechanism was used to determine the visitor ID value (for example, to calculate cookie acceptance), the `post_visid_type` contains a lookup key that indicates which ID method was used. The lookup keys are listed along with the visitor ID mechanisms in the [table below](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A).

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

The Experience Cloud ID is reported in a separate column, `mcvisid`. Dato che l'ID è riportato in una colonna specifica, può non essere chiaro se Analytics utilizza questo ID o un ID diverso per identificare un visitatore.

If the Experience Cloud ID was used to identify the visitor, the ID will be contained in the `post_visid_high` and `post_visid_low` columns and the `post_visid_type` will be set to 5. When calculating metrics, you should use the value from the `post_visid_high` and `post_visid_low` columns since these columns will always contain the final visitor ID.

>[!TIP]
>
> When using the Adobe Analytics visitor ID as a key for other systems, always use `post_visid_high` and `post_visid_low`. Questi campi sono gli unici campi ID visitatore che garantiscono un valore con ogni riga del feed di dati.

## Analytics Visitor IDs {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

In Analytics, un visitatore può essere identificato in diversi modi (elencato nella tabella seguente in ordine di preferenza):

| Ordine | Parametro query (metodo di raccolta) | post_ visid_ type, valore colonna | Presente se |
|---|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) | 0 | s.visitorID è impostato. |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_analytics) | 3 | Visitor had an existing s_vi cookie before you deployed the Visitor ID service, or you have a Visitor ID [grace period](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_grace_period) configured. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ impostato da Servizio identità)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 5 | Il browser del visitatore accetta i cookie (prime parti) e il servizio Identità viene distribuito. |
| ![](assets/step4_icon.png) | [fid (cookie di fallback in H.25.3 o successivo, o in AppMeasurement per JavaScript)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_fallback) | 4 | Il browser del visitatore accetta i cookie (prime parti). |
| ![](assets/step5_icon.png) | [Intestazione utente HTTP Mobile](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_mobile) | 2 | Il dispositivo viene riconosciuto come dispositivo mobile. |
| ![](assets/step6_icon.png) | [Indirizzo IP, agente utente, indirizzo IP gateway](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_fallback) | 1 | Il browser del visitatore non accetta i cookie. |

In many scenarios you might see 2 or 3 different IDs on a call, but Analytics will use the first ID present from that list as the official visitor ID, and split that value across the `post_visid_high` and `post_visid_low` columns. Ad esempio, se imposti un ID visitatore personalizzato (incluso nel parametro di query “vid”), questo ID verrà usato prima degli altri ID visualizzati per lo stesso hit.
