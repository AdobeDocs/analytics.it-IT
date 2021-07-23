---
title: dynamicAccountMatch
description: La variabile dynamicAccountMatch determina il valore da visualizzare negli account dinamici.
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
source-git-commit: 562ed0e190954b7687fa79efaf5c5c54eb202af8
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 4%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript legacy (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement o nei tag correnti in Adobe Experience Platform.

La variabile `dynamicAccountMatch` è il valore che `dynamicAccountList` esamina e confronta i relativi valori. Se `dynamicAccountSelection` non è impostato su `true`, questa variabile viene ignorata.

Se questa variabile non è definita, il suo valore predefinito è `window.location.host`.

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

* Le pagine salvate su un disco rigido non dispongono di diverse variabili `location` definite (ad esempio, `location.host` è vuoto). Assicurati che `s_account` contenga una suite di rapporti predefinita.
* Quando una pagina viene tradotta tramite un motore di traduzione basato sul web, ad esempio Google, la selezione dinamica dell’account non funziona correttamente. Per un tracciamento più preciso, compila la variabile `s_account` lato server.
