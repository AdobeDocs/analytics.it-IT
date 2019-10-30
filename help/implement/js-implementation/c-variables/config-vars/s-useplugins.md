---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.usePlugins

Se la funzione è disponibile e contiene codice utile, [!UICONTROL s_usePlugins] impostare su 'true'.

Quando [!UICONTROL usePlugins] è 'true', la *`s_doPlugins`* funzione viene chiamata prima di ogni richiesta di immagine.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | True |

## Sintassi e valori possibili

```js
s.usePlugins=true|false
```

La [!UICONTROL usePlugins] variabile deve essere 'true' o 'false'.

## Esempi

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

La [!UICONTROL usePlugins] variabile deve essere false (o non dichiarata) solo se la *`s_doPlugins`* funzione non è dichiarata nel file JavaScript.

## Impostazioni di configurazione

Nessuno