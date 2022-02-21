---
title: dynamicAccountMatch
description: La variabile dynamicAccountMatch determina il valore da visualizzare negli account dinamici.
feature: Implementation Basics
exl-id: 3b68f2e6-1bd9-4b16-9d03-a87c9217e1b7
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 4%

---

# dynamicAccountMatch

>[!IMPORTANT]
>
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript legacy (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement o nei tag correnti in Adobe Experience Platform.

La `dynamicAccountMatch` è il valore che `dynamicAccountList` esamina e confronta i relativi valori. Se `dynamicAccountSelection` non è impostato su `true`, questa variabile viene ignorata.

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

* Le pagine salvate in un disco rigido non dispongono di più `location` variabili definite (ad esempio `location.host` è vuoto). Assicurati `s_account` contiene una suite di rapporti predefinita.
* Quando una pagina viene tradotta tramite un motore di traduzione basato su web, ad esempio Google, la selezione di account dinamici non funziona come previsto. Per un tracciamento più preciso, compila le `s_account` sul lato server.
