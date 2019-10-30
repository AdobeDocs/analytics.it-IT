---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.cookieLifetime

La variabile viene utilizzata sia dai server JavaScript che dai server di raccolta dati per determinare la durata di vita di un cookie.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | cl | Traffico &gt; Tecnologia &gt; Cookie Tutti i rapporti relativi ai visitatori | "" |

Se *`cookieLifetime`* è impostato, sostituisce qualsiasi altra scadenza del cookie per i server JavaScript e di raccolta dati, con una delle eccezioni descritte di seguito. La *`cookieLifetime`* variabile può avere uno dei tre valori seguenti:

* [!DNL Analytics] Cookie
* Cookie
* Impostazioni e plug-in JavaScript

## Sintassi e valori possibili

```js
s.cookieLifetime="value"
```

I valori possibili sono elencati di seguito:

* ""
* "NONE"
* "SESSION"
* Un numero intero che rappresenta il numero di secondi fino alla scadenza

## Esempi

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

*`cookieLifetime`* influisce sul [!DNL Analytics] tracciamento. Se, ad esempio, *`cookieLifetime`* è di due giorni, i rapporti sui visitatori univoci mensili, trimestrali e annuali non saranno corretti. Prestate attenzione quando impostate *`cookieLifetime`*.
