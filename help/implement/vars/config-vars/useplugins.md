---
title: usePlugins
description: Attiva o disattiva la funzione doPlugins() .
feature: Variables
exl-id: e8499acf-d8b9-490c-9f67-ad9a8f6ca7df
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 2%

---

# usePlugins

Se `usePlugins` è abilitato, [`doPlugins()`](../functions/doplugins.md) viene eseguita immediatamente prima della compilazione di AppMeasurement e invia un hit ad Adobe. Abilita questa variabile se utilizzi la variabile `doPlugins()` funzione .

## Utilizzare i plug-in utilizzando i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.usePlugins in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.usePlugins` è una variabile booleana che determina se AppMeasurement chiama il `doPlugins()` funzione . Il valore predefinito è `false`. Imposta questa variabile su `true` se utilizzi `doPlugins()` nella tua implementazione.

```js
s.usePlugins = true;
```
