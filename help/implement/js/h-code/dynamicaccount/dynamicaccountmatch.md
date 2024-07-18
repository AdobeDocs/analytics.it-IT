---
title: dynamicAccountMatch
description: La variabile dynamicAccountMatch determina il valore da esaminare negli account dinamici.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 4%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando le implementazioni legacy di JavaScript (codice H). Queste variabili non sono supportate nelle librerie o nei tag AppMeasurement correnti in Adobe Experience Platform.

La variabile `dynamicAccountMatch` è il valore che `dynamicAccountList` esamina e confronta i suoi valori. Se `dynamicAccountSelection` non è impostato su `true`, questa variabile viene ignorata.

Se questa variabile non è definita, il valore predefinito è `window.location.host`.

## Sintassi

```js
s.dynamicAccountMatch=[DOM object]
```

## Esempi

```js
// Look at the URL path to determine report suite
s.dynamicAccountMatch = location.pathname;

// Use a query string
s.dynamicAccountMatch = location.search;

// Use the full URL
s.dynamicAccountMatch = location.href;

// Use concatenated variables
s.dynamicAccountMatch =  location.hostname + location.pathname + location.search;
```

## Note aggiuntive

* Per le pagine salvate in un disco rigido non sono definite numerose variabili `location` (ad esempio, `location.host` è vuoto). Assicurarsi che `s_account` contenga una suite di rapporti predefinita.
* Quando una pagina viene tradotta tramite un motore di traduzione basato su Web, come Google, la selezione dinamica dell’account non funziona come previsto. Per un tracciamento più preciso, popolare la variabile `s_account` lato server.
