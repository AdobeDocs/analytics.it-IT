---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountSelection

La variabile consente di selezionare dinamicamente la suite di rapporti in base all'URL di ogni pagina.

>[!NOTE]
>
>`dynamicAccountSelection` non funziona con il tracciamento personalizzato dei collegamenti.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | False |

>[!NOTE]
>
>Entrambi `dynamicAccountList` e `dynamicAccountMatch` vengono ignorati se la `dynamicAccountSelection` variabile non è dichiarata o impostata su 'false'.

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
