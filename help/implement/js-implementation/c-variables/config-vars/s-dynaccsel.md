---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicAccountSelection

La variabile consente di selezionare dinamicamente la suite di rapporti in base all'URL di ogni pagina.

> [!NOTE] non `dynamicAccountSelection` funziona con il tracciamento personalizzato dei collegamenti.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | False |

> [!NOTE] Entrambi `dynamicAccountList` e `dynamicAccountMatch` vengono ignorati se la `dynamicAccountSelection` variabile non è dichiarata o impostata su 'false'.

## Sintassi e valori possibili

```js
s.dynamicAccountSelection=[true|false]
```

Solo 'true' e 'false' sono consentiti come valori di *`dynamicAccountSelection`*.

## Esempi

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

## Impostazioni di configurazione

Nessuno

## Insidie, domande e suggerimenti

* La selezione di account dinamici non è supportata da [AppMeasurement per JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Usa sempre [!DNL DigitalPulse Debugger] per determinare quale suite di rapporti riceve i dati da ogni pagina.
