---
title: dynamicAccountSelection
description: La variabile dynamicAccountSelection abilita o disabilita la selezione dinamica degli account.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 4%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript legacy (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement correnti o nella raccolta dati di Adobe Experience Platform.

La `dynamicAccountSelection` è un valore booleano che determina se viene utilizzata la selezione dinamica dell&#39;account.

Se impostato su `true`, il file JavaScript esamina `dynamicAccountMatch` e `dynamicAccountList`.

Se impostato su `false`oppure, se questa variabile non è definita, la variabile `dynamicAccountMatch` e `dynamicAccountList` le variabili vengono ignorate.

Se questa variabile non è definita, il valore predefinito è `false`.

## Sintassi

```js
s.dynamicAccountSelection = [boolean];
```

## Esempio

```js
s.dynamicAccountSelection = true;
```
