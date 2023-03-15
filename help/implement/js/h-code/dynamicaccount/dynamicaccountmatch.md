---
title: dynamicAccountMatch
description: La variabile dynamicAccountMatch determina il valore da esaminare negli account dinamici.
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
>Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript legacy (codice H). Queste variabili non sono supportate nelle librerie o nei tag AppMeasurement correnti in Adobe Experience Platform.

Il `dynamicAccountMatch` variabile è il valore che `dynamicAccountList` esamina e confronta i relativi valori. Se `dynamicAccountSelection` non è impostato su `true`, questa variabile viene ignorata.

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

* Le pagine salvate su un disco rigido non contengono più di `location` variabili definite (ad esempio, `location.host` è vuoto). Assicurati che `s_account` contiene una suite di rapporti predefinita.
* Quando una pagina viene tradotta tramite un motore di traduzione basato su Web, come Google, la selezione dinamica dell’account non funziona come previsto. Per un tracciamento più preciso, compila il `s_account` variabile lato server.
