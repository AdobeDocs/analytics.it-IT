---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Dynamic variables let you copy values from one variable to another without typing the full values multiple times in the image requests on your site.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

The  variable allows deployment to flag variables, which should be populated dynamically.

Cookies, request headers, and image query string parameters are available to be populated dynamically.

| Max Size | Parametro debugger | Reports Populated | Valore predefinito |
|---|---|---|---|
| N/D | D= | Any | D= |

## Sintassi e valori possibili

```js
s.prop1="D=User-Agent”
```

OPPURE UTILIZZARE IL FLAG PERSONALIZZATO PER LE VARIABILI DINAMICHE

```js
s.dynamicVariablePrefix=".."
```

## Esempi

```js
s.prop1="D=User-Agent”
```

OPPURE UTILIZZARE IL FLAG PERSONALIZZATO PER LE VARIABILI DINAMICHE

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

## Insidie, domande e suggerimenti

* Le variabili dinamiche possono essere utilizzate per ridurre notevolmente la lunghezza totale dell’URL copiando i valori in altre variabili.

* Le variabili dinamiche possono essere utilizzate per raccogliere dati da intestazioni e cookie non altrimenti disponibili per la raccolta dei dati.
