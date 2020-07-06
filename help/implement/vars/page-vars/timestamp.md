---
title: timestamp
description: Imposta manualmente il timestamp dell’hit.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 0%

---


# timestamp

La `timestamp` variabile imposta manualmente il timestamp dell’hit per le suite di rapporti abilitate per le marche temporali.

>[!WARNING]
>
>Non utilizzate questa variabile se la suite di rapporti non è configurata in modo esplicito per accettare gli hit con marca temporale. AppMeasurement imposta automaticamente l’ora di un hit per le suite di rapporti che non supportano gli hit con marca temporale. Se invii un hit con questa variabile a una suite di rapporti che non supporta le marche temporali, quei dati andranno persi definitivamente.

## Timestamp nel lancio  Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.timestamp nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.timestamp` variabile è una stringa contenente la data e l’ora dell’hit. I formati di marca temporale validi includono l&#39;ora [](https://en.wikipedia.org/wiki/ISO_8601) ISO 8601 [e](https://en.wikipedia.org/wiki/Unix_time)Unix.

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

Le date e le ore espresse in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) possono assumere diverse forme. Adobe non supporta tutte le funzioni della norma ISO 8601.

* È necessario specificare sia la data che l&#39;ora, separati da `T`.
* Sono necessari ore e minuti; i secondi sono facoltativi, ma consigliati.
* Le date della settimana e quelle ordinali non sono supportate.
* La data può essere in formato standard o esteso. Ad esempio, `2020-01-01T00:00:00Z` e `20200101T000000Z` sono entrambi validi.
* I minuti e i secondi frazionari sono tecnicamente validi, ma le frazioni vengono ignorate da Adobe.
* I fusi orari sono supportati nei formati standard ed esteso.

Di seguito sono riportati valori ISO 8601 validi per la `timestamp` variabile:

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
