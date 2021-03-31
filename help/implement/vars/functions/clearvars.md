---
title: clearVars
description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (li imposta come "non definiti").
translation-type: tm+mt
source-git-commit: 4359f451692b86087efe27d4b3ec49ca85b7addc
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 2%

---


# clearVars

Alcune implementazioni, ad esempio nelle applicazioni a pagina singola, richiedono più hit inviati allo stesso caricamento della pagina. Utilizza il metodo `clearVars()` per cancellare i valori delle variabili in modo che non persistano negli hit successivi.

Questo metodo non accetta argomenti e non restituisce alcun valore. Il suo unico scopo è cancellare i valori delle variabili dall&#39;oggetto instance. Questo metodo imposta i seguenti elementi su `undefined`:

* `prop1` - `prop75`
* `eVar` -  `eVar250`
* `hier1` -  `hier5`
* `list1` -  `list3`
* `events`
* `products`
* `channel`
* `purchaseID`
* `transactionID`
* `state`
* `zip`
* `campaign`

## Cancella variabili in Adobe Experience Platform Launch

Imposta l&#39;azione Cancella variabili durante la configurazione di una regola.

1. Accedi a [launch.adobe.com](https://launch.adobe.com) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic sull&#39;icona &quot;+&quot;
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Clear Variables].

## s.clearVars() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Puoi chiamare il metodo `s.clearVars()` in qualsiasi punto dell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.clearVars();
```
