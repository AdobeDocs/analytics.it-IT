---
title: timestamp
description: Imposta manualmente la marca temporale dell'hit.
exl-id: 9d5ce5ef-2d84-4f65-b2e3-7aa3e219bc34
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 0%

---

# timestamp

La variabile `timestamp` imposta manualmente il timestamp dell’hit per le suite di rapporti abilitate per le marche temporali.

>[!WARNING]
>
>Non utilizzare questa variabile se la suite di rapporti non è configurata in modo esplicito per accettare hit con marca temporale. AppMeasurement imposta automaticamente l&#39;ora di un hit per le suite di rapporti che non supportano gli hit con marca temporale. Se invii un hit con questa variabile a una suite di rapporti che non supporta le marche temporali, tali dati andranno perduti definitivamente.

## Timestamp tramite tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.timestamp in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.timestamp` è una stringa contenente la data e l’ora dell’hit. I formati di marca temporale validi includono [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) e [Tempo Unix](https://en.wikipedia.org/wiki/Unix_time).

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

* È necessario specificare sia la data che l’ora, separati da `T`.
* Sono richiesti ore e minuti; i secondi sono facoltativi ma consigliati.
* Le date della settimana e le date ordinali non sono supportate.
* La data può essere in formato standard o esteso. Ad esempio, `2020-01-01T00:00:00Z` e `20200101T000000Z` sono entrambi validi.
* I minuti e i secondi frazionari sono tecnicamente validi, ma le frazioni vengono ignorate per Adobe.
* I fusi orari sono supportati nei formati standard ed esteso.

Di seguito è riportato un esempio valido di valori ISO 8601 nella variabile `timestamp` :

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
