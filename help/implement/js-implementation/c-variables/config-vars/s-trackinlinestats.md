---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.trackInlineStats

La variabile determina se i dati ClickMap vengono raccolti o meno.

Se *`trackInlineStats`* è "true", i dati sulla pagina e il collegamento su cui si fa clic vengono memorizzati in un cookie denominato s_sq. Se 'false', s_sq avrà un valore di "[[B]]", che viene considerato null.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | ClickMap | False |

## Sintassi e valori possibili

```
js
s.trackInlineStats=true|false
```

La *`trackInlineStats`* variabile deve essere 'true' o 'false'.

## Esempi

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

## Impostazioni di configurazione

Nessuno