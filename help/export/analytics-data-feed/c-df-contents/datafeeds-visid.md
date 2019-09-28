---
description: nulle
keywords: Feed dati;processo;visitatori;Experience Cloud ID;analytics visitor id;identificare
seo-description: nulle
seo-title: Identificare i visitatori
solution: Analytics
title: Identificare i visitatori
topic: Reports and Analytics
uuid: 2490b67e-a333-422d-82fa-cb0670ef2e0c
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Identificare i visitatori

Analytics offre diversi metodi per identificare i visitatori (elencati in [Identificazione dei visitatori](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)). Indipendentemente dal metodo utilizzato per identificare un visitatore, nei feed di dati l’ID visitatore finale utilizzato da Analytics viene suddiviso tra le `post_visid_high` e `post_visid_low` le colonne, anche quando si utilizza il servizio identità.

**Per identificare visitatori univoci:**

1. Escludere tutte le righe in cui `exclude_hit > 0`.
1. Escludi tutte le righe con `hit_source = 5,7,8,9`. 5, 8 e 9 sono righe di riepilogo caricate utilizzando le origini dati. 7 rappresenta i caricamenti dell'origine dati ID transazione che non devono essere inclusi nei conteggi delle visite e dei visitatori. See [Hit Source Lookup](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42)
1. Combinate `post_visid_high` con `post_visid_low`. Tutti gli hit in tutte le date che contengono questa combinazione di `post_visid_high` e `post_visid_low` possono essere considerati come provenienti dallo stesso visitatore.

Se desiderate determinare quale meccanismo è stato utilizzato per determinare il valore ID visitatore (ad esempio, per calcolare l’accettazione dei cookie), il `post_visid_type` contiene una chiave di ricerca che indica quale metodo ID è stato utilizzato. Le chiavi di ricerca sono elencate insieme ai meccanismi ID visitatore nella [tabella seguente](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A).

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

L’Experience Cloud ID viene riportato in una colonna separata, `mcvisid`. Poiché questo ID è riportato nella propria colonna, può non essere chiaro se Analytics utilizza questo ID o un ID diverso per identificare un visitatore.

Se l’ID Experience Cloud è stato utilizzato per identificare il visitatore, l’ID sarà contenuto nelle `post_visid_high` colonne e `post_visid_low` e l’ID `post_visid_type` sarà impostato su 5. Nel calcolo delle metriche, devi usare il valore delle `post_visid_high` `post_visid_low` colonne e delle colonne, poiché queste colonne conterranno sempre l’ID visitatore finale.

>[!TIP]
>
> Quando utilizzi l’ID visitatore di Adobe Analytics come chiave per altri sistemi, usa sempre `post_visid_high` e `post_visid_low`. Questi campi sono gli unici campi ID visitatore cui è garantito un valore per ogni riga nel feed di dati.

## ID visitatore di Analytics {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Esistono diversi modi in cui un visitatore può essere identificato in Analytics (elencati nella tabella seguente in ordine di preferenza):

| Ordine | Parametro query (metodo di raccolta) | post_visid_type valore colonna | Presente se |
|---|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) | 0 | s.visitorID è impostato. |
| ![](assets/step2_icon.png) | [aid (cookie s_vi)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_analytics.html) | 3 | Visitor had an existing s_vi cookie before you deployed the Visitor ID service, or you have a Visitor ID [grace period](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid_grace_period.html) configured. |
| ![](assets/step3_icon.png) | [mid (cookie AMCV_ impostato da Servizio identità)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 5 | Il browser del visitatore accetta i cookie (di prime parti) e il servizio identità è distribuito. |
| ![](assets/step4_icon.png) | [fid (cookie di fallback in H.25.3 o successivo, o in AppMeasurement per JavaScript)](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html) | 4 | Il browser del visitatore accetta i cookie (first-party). |
| ![](assets/step5_icon.png) | [Intestazione del sottoscrittore HTTP Mobile](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_mobile.html) | 2 | Il dispositivo è riconosciuto come dispositivo mobile. |
| ![](assets/step6_icon.png) | [Indirizzo IP, agente utente, indirizzo IP gateway](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_fallback.html) | 1 | Il browser del visitatore non accetta i cookie. |

In molti scenari potrebbero essere presenti due o tre ID diversi in una chiamata, ma Analytics utilizzerà il primo ID presente nell’elenco come ID visitatore ufficiale e lo suddividerà tra le `post_visid_high` e `post_visid_low` le colonne. Ad esempio, se imposti un ID visitatore personalizzato (incluso nel parametro di query “vid”), questo ID verrà usato prima degli altri ID visualizzati per lo stesso hit.
