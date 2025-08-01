---
title: timestamp
description: Imposta manualmente la marca temporale dell’hit.
feature: Appmeasurement Implementation
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '267'
ht-degree: 9%

---

# timestamp

La variabile `timestamp` imposta manualmente la marca temporale dell&#39;hit per le suite di rapporti abilitate per la marca temporale.

>[!WARNING]
>
>Non utilizzare questa variabile se la suite di rapporti non è configurata in modo esplicito per accettare hit con marca temporale. AppMeasurement imposta automaticamente l’ora di un hit per le suite di rapporti che non supportano gli hit con marca temporale. Se invii un hit con questa variabile a una suite di rapporti che non supporta i timestamp, tali dati vengono persi definitivamente.

## Marca temporale tramite Web SDK

La marca temporale è [mappata per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/xdm-var-mapping.html?lang=it) nel campo XDM `xdm.timestamp`. Questo campo supporta solo il tempo Unix.

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
