---
description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (li imposta come "undefined").
keywords: Analytics Implementation
solution: Analytics
title: La funzione s.clearVars()
topic: Developer and implementation
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# La funzione s.clearVars()

Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (li imposta come "undefined").

* `props`
* `eVars`
* `hier`
* `list`
* `events`
* `eventList`
* `products`
* `productsList`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

Ad esempio:

```js
s.clearVars()
```

>[!NOTE]
>
>`clearVars()` è incluso in [AppMeasurement per JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) ma non è disponibile nel codice H e nelle versioni precedenti.

