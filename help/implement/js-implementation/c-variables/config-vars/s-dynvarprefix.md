---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Analytics Implementation
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

La variabile consente alla distribuzione di contrassegnare le variabili, che devono essere popolate in modo dinamico.

I cookie, le intestazioni delle richieste e i parametri delle stringhe delle query sulle immagini possono essere compilati in modo dinamico.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | D= | Any | D= |

## Sintassi e valori possibili

```js
s.prop1="D=User-Agent"
```

OPPURE UTILIZZARE IL FLAG PERSONALIZZATO PER LE VARIABILI DINAMICHE

```js
s.dynamicVariablePrefix=".."
```

## Esempi

```js
s.prop1="D=User-Agent"
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
