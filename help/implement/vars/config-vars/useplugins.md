---
title: usePlugins
description: Attiva o disattiva la funzione doPlugins() .
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 2%

---

# usePlugins

Se `usePlugins` è abilitato, la funzione [`doPlugins()`](../functions/doplugins.md) viene eseguita immediatamente prima della compilazione di AppMeasurement e invia un hit ad Adobe. Abilita questa variabile se utilizzi la funzione `doPlugins()` .

## Utilizzare i plug-in utilizzando i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.usePlugins in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.usePlugins` è booleana che determina se AppMeasurement chiama la funzione `doPlugins()` . Il valore predefinito è `false`. Imposta questa variabile su `true` se utilizzi la funzione `doPlugins()` nella tua implementazione.

```js
s.usePlugins = true;
```
