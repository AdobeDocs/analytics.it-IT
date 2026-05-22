---
title: timestamp
description: Imposta manualmente la marca temporale dell’hit.
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/f2r9jWtF5HgCP6jUKg3YnLFxNwx1DiUBI-2Nquy5-K0'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 276
ht-degree: 9%

---

# timestamp

La variabile `timestamp` imposta manualmente la marca temporale dell&#39;hit per le suite di rapporti abilitate per la marca temporale.

>[!WARNING]
>
>Non utilizzare questa variabile se la suite di rapporti non è configurata in modo esplicito per accettare hit con marca temporale. AppMeasurement imposta automaticamente l’ora di un hit per le suite di rapporti che non supportano gli hit con marca temporale. Se invii un hit con questa variabile a una suite di rapporti che non supporta i timestamp, tali dati vengono persi definitivamente.

## Marca temporale tramite Web SDK

La marca temporale è [mappata per Adobe Analytics](/help/implement/aep-edge/xdm-var-mapping.md) nel campo XDM `xdm.timestamp`. Questo campo supporta solo il tempo Unix.

## Marca temporale tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.timestamp in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.timestamp` è una stringa contenente la data e l&#39;ora dell&#39;hit. I formati di marca temporale validi includono [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) e [Tempo Unix](https://en.wikipedia.org/wiki/Unix_time) in secondi.

```js
// Timestamp using ISO 8601
s.timestamp = "2024-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## Valori ISO 8601

Le date e le ore espresse in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) possono assumere diverse forme. Adobe non supporta tutte le funzioni di ISO 8601.

* È necessario specificare sia la data che l&#39;ora, separate da `T`.
* Sono necessari ore e minuti; i secondi sono facoltativi ma consigliati.
* Le date settimanali e le date ordinali non sono supportate.
* La data può essere in formato standard o esteso. Ad esempio, `2024-01-01T00:00:00Z` e `20240101T000000Z` sono entrambi validi.
* I minuti e i secondi frazionari sono tecnicamente validi, ma le frazioni vengono ignorate da Adobe.
* I fusi orari sono supportati nei formati standard ed estesi.

Di seguito sono riportati esempi validi di valori ISO 8601 nella variabile `timestamp`:

```text
2024-01-01T00:00:00+00:00
2024-01-01T00:00:00Z
2024-01-01T00:00:00
2024-01-01T00:00
20240101T000000+0000
20240101T000000Z
20240101T000000
20240101T0000
```
