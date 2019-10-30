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
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

> [!NOTE] è `clearVars()` incluso in [AppMeasurement per JavaScript](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) , ma non è disponibile nel codice H e nelle versioni precedenti.

