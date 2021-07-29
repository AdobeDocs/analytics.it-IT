---
title: dynamicAccountSelection
description: La variabile dynamicAccountSelection abilita o disabilita la selezione dinamica degli account.
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
source-git-commit: 9a70d79a83d8274e17407229bab0273abbe80649
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 4%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript legacy (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement correnti o nell’interfaccia utente di Raccolta dati.

La variabile `dynamicAccountSelection` è un valore booleano che determina se viene utilizzata la selezione dinamica dell’account.

Se impostato su `true`, il file JavaScript esamina `dynamicAccountMatch` e `dynamicAccountList`.

Se impostata su `false` o se questa variabile non è definita, le variabili `dynamicAccountMatch` e `dynamicAccountList` vengono ignorate.

Se questa variabile non è definita, il valore predefinito è `false`.

## Sintassi

```js
s.dynamicAccountSelection = [boolean];
```

## Esempio

```js
s.dynamicAccountSelection = true;
```
