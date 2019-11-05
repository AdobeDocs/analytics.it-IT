---
description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (li imposta come "undefined").
keywords: Implementazione di Analytics
seo-description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (li imposta come "undefined").
seo-title: La funzione s.clearVars()
solution: Analytics
title: La funzione s.clearVars()
topic: Sviluppatore e implementazione
uuid: 43c425bc-15ae-4892-a5a5-e1defcb25ff4
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

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

