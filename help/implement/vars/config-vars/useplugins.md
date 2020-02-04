---
title: usePlugins
description: Abilitare o disabilitare la funzione doPlugins().
translation-type: tm+mt
source-git-commit: a02fb674ea71a05e085c8e9b2dc4460f62f2cd51

---


# usePlugins

Se `usePlugins` è abilitata, la `doPlugins()` funzione viene eseguita immediatamente prima della compilazione di AppMeasurement e invia un hit ad Adobe. Abilitate questa variabile se utilizzate la `doPlugins()` funzione.

## Utilizzo dei plug-in in Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.usePlugins in AppMeasurement e Launch editor di codice personalizzato

La `s.usePlugins` variabile è un valore booleano che determina se AppMeasurement chiama la `doPlugins()` funzione. Its default value is `false`. Impostate questa variabile su `true` se utilizzate la `doPlugins()` funzione nella vostra implementazione.

```js
s.usePlugins = true;
```
