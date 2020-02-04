---
title: dynamicAccountMatch
description: La variabile dynamicAccountMatch determina il valore da visualizzare negli account dinamici.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountMatch

> [!IMPORTANT] Gli account dinamici sono supportati solo utilizzando implementazioni JavaScript precedenti (H Code). Queste variabili non sono supportate nelle librerie AppMeasurement correnti né nel lancio della piattaforma Adobe Experience.

La `dynamicAccountMatch` variabile è il valore che `dynamicAccountList` esamina e confronta i relativi valori. Se non `dynamicAccountSelection` è impostato su `true`, questa variabile viene ignorata.

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

* Le pagine salvate in un disco rigido non presentano diverse `location` variabili definite (ad esempio, `location.host` è vuoto). Accertati che `s_account` contenga una suite di rapporti predefinita.
* Quando una pagina viene tradotta tramite un motore di traduzione basato sul Web, come Google, la selezione dell&#39;account dinamico non funziona correttamente. Per un tracciamento più preciso, compila la `s_account` variabile lato server.
