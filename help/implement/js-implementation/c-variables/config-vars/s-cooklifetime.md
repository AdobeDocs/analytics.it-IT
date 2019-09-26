---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.cookieLifetime

La variabile viene utilizzata sia dai server JavaScript che dai server di raccolta dati per determinare la durata di vita di un cookie.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | cl | Traffic &gt; Technology &gt; Cookies All visitor-related reports | "" |

If  is set, it overrides any other cookie expirations for both JavaScript and data collection servers, with one exception, described below. *`cookieLifetime`* La *`cookieLifetime`* variabile può avere uno dei tre valori seguenti:

* [!DNL Analytics] Cookie
* Cookie
* JavaScript Settings and Plugins

## Syntax and Possible Values

```js
s.cookieLifetime="value"
```

The possible values are listed as follows:

* ""
* "NONE"
* "SESSION"
* An integer representing the number of seconds until expiration

## Esempi

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

## Configuration Settings

Nessuno

## Pitfalls, Questions, and Tips

*`cookieLifetime`* affects  tracking. [!DNL Analytics] Se, ad esempio, *`cookieLifetime`* è di due giorni, i rapporti sui visitatori univoci mensili, trimestrali e annuali non saranno corretti. Prestate attenzione quando impostate *`cookieLifetime`*.
