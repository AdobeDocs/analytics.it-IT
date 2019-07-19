---
description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (impostandoli come «undefined». ")
keywords: Implementazione di Analytics
seo-description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (impostandoli come «undefined». ")
seo-title: La funzione s. clearvars ()
solution: Analytics
title: La funzione s. clearvars ()
topic: Sviluppatore e implementazione
uuid: 43 c 425 bc -15 ae -4892-a 5 a 5-e 1 defcb 25 ff 4
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# La funzione s. clearvars ()

Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (impostandoli come «undefined». ")

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
>`clearVars()` è incluso in [appmeasurement per javascript](../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) ma non è disponibile nel codice H e nelle versioni precedenti.

