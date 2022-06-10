---
title: timestamp
description: Imposta manualmente la marca temporale dell'hit.
feature: Variables
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# timestamp

La `timestamp` imposta manualmente la marca temporale dell’hit per le suite di rapporti abilitate per le marche temporali.

>[!WARNING]
>
>Non utilizzare questa variabile se la suite di rapporti non è configurata in modo esplicito per accettare hit con marca temporale. AppMeasurement imposta automaticamente l&#39;ora di un hit per le suite di rapporti che non supportano gli hit con marca temporale. Se invii un hit con questa variabile a una suite di rapporti che non supporta le marche temporali, tali dati andranno perduti definitivamente.

## Timestamp tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.timestamp in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.timestamp` è una stringa contenente la data e l&#39;ora dell&#39;hit. I formati timestamp validi includono [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) e [Tempo Unix](https://en.wikipedia.org/wiki/Unix_time).

```js
// Timestamp using ISO 8601
s.timestamp = "2020-01-01T00:00:00Z";

// Timestamp using Unix timestamp
s.timestamp = "1577836800";

// Automatically get the current Unix timestamp
s.timestamp = Math.round(new Date().getTime()/1000);

// Automatically get the current ISO 8601 timestamp
s.timestamp = new Date().toISOString();
```

## Valori ISO 8601

Date e ore espresse in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) può assumere diverse forme. Adobe non supporta tutte le funzioni della norma ISO 8601.

* Devono essere fornite sia la data che l&#39;ora, separate da `T`.
* Sono richiesti ore e minuti; i secondi sono facoltativi ma consigliati.
* Le date della settimana e le date ordinali non sono supportate.
* La data può essere in formato standard o esteso. Ad esempio: `2020-01-01T00:00:00Z` e `20200101T000000Z` sono entrambi validi.
* I minuti e i secondi frazionari sono tecnicamente validi, ma le frazioni vengono ignorate per Adobe.
* I fusi orari sono supportati nei formati standard ed esteso.

Di seguito è riportato un esempio valido di valori ISO 8601 nel `timestamp` variabile:

```text
2020-01-01T00:00:00+00:00
2020-01-01T00:00:00Z
2020-01-01T00:00:00
2020-01-01T00:00
20200101T000000+0000
20200101T000000Z
20200101T000000
20200101T0000
```
