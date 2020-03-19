---
title: clearVars
description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (li imposta come "undefined").
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# clearVars

Alcune implementazioni, come nelle applicazioni a pagina singola, richiedono più hit inviati sullo stesso caricamento di pagina. Utilizzare il `clearVars()` metodo per cancellare i valori delle variabili in modo che non persistano negli hit successivi.

Questo metodo non accetta argomenti e non restituisce alcun valore. Il suo unico scopo è cancellare i valori variabili dall&#39;oggetto instance. Questo metodo imposta gli elementi seguenti su `undefined`:

* `prop1` - `prop75`
* `eVar` - `eVar250`
* `hier1` - `hier5`
* `list1` - `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Cancella variabili in Adobe Experience Platform Launch

Impostate l&#39;azione Cancella variabili durante la configurazione di una regola.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic sull&#39;icona &quot;+&quot;
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Clear Variables].

## s.clearVars() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Puoi chiamare il `s.clearVars()` metodo ovunque nell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.clearVars();
```
