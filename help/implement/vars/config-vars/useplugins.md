---
title: usePlugins
description: Abilitare o disabilitare la funzione doPlugins().
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# usePlugins

Se `usePlugins` è abilitata, la [`doPlugins()`](../functions/doplugins.md) funzione viene eseguita immediatamente prima della compilazione di AppMeasurement e invia un hit ad Adobe. Abilitare questa variabile se si utilizza la `doPlugins()` funzione.

## Utilizzo dei plug-in in Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.usePlugins in AppMeasurement e Launch editor di codice personalizzato

La `s.usePlugins` variabile è un valore booleano che determina se AppMeasurement chiama la `doPlugins()` funzione. Its default value is `false`. Impostate questa variabile su `true` se utilizzate la `doPlugins()` funzione nella vostra implementazione.

```js
s.usePlugins = true;
```
