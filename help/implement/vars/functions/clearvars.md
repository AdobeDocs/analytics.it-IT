---
title: clearVars
description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (li imposta come "non definiti").
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 1%

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

## Cancella variabili utilizzando i tag in Adobe Experience Platform

Imposta l&#39;azione Cancella variabili durante la configurazione di una regola.

1. Accedi all&#39; [Interfaccia di raccolta dati](https://experience.adobe.com/data-collection) utilizzando le tue credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai alla scheda [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. In [!UICONTROL Actions], fai clic sull&#39;icona &quot;+&quot;
5. Imposta il menu a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Clear Variables].

## s.clearVars() in AppMeasurement e nell&#39;editor di codice personalizzato

Puoi chiamare il metodo `s.clearVars()` in qualsiasi punto dell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.clearVars();
```
