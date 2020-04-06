---
title: dynamicAccountSelection
description: La variabile dynamicAccountSelection abilita o disabilita la selezione dinamica degli account.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# dynamicAccountSelection

>[!IMPORTANT] Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript precedenti (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement correnti né nel lancio della piattaforma Adobe Experience.

La `dynamicAccountSelection` variabile è un valore booleano che determina se è utilizzata la selezione dinamica dell&#39;account.

Se impostato su `true`, il file JavaScript cerca `dynamicAccountMatch` e `dynamicAccountList`.

Se questa variabile è impostata su `false`, o se non è definita, le `dynamicAccountMatch` variabili e `dynamicAccountList` le variabili vengono ignorate.

Se questa variabile non è definita, il valore predefinito è `false`.

## Sintassi

```js
s.dynamicAccountSelection = [boolean];
```

## Esempio

```js
s.dynamicAccountSelection = true;
```
