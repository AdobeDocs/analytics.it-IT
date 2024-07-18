---
title: dynamicAccountSelection
description: La variabile dynamicAccountSelection abilita o disabilita la selezione dinamica dell'account.
feature: Implementation Basics
exl-id: ccb530f9-b128-4d2d-9b5d-9b305272f0a4
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 4%

---

# dynamicAccountSelection

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando le implementazioni legacy di JavaScript (codice H). Queste variabili non sono supportate nelle librerie AppMeasurement correnti o nella raccolta dati di Adobe Experience Platform.

La variabile `dynamicAccountSelection` è un valore booleano che determina se viene utilizzata la selezione dinamica dell&#39;account.

Se impostato su `true`, il file JavaScript esamina `dynamicAccountMatch` e `dynamicAccountList`.

Se è impostato su `false` o se questa variabile non è definita, le variabili `dynamicAccountMatch` e `dynamicAccountList` verranno ignorate.

Se questa variabile non è definita, il valore predefinito è `false`.

## Sintassi

```js
s.dynamicAccountSelection = [boolean];
```

## Esempio

```js
s.dynamicAccountSelection = true;
```
