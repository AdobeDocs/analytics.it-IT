---
title: clearVars
description: Cancella i seguenti valori dall'oggetto istanza. Questa funzione rimuove gli elementi (li imposta come "indefiniti").
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 23%

---

# clearVars

Alcune implementazioni, ad esempio nelle applicazioni a pagina singola, richiedono più hit inviati sullo stesso caricamento di pagina. Utilizza il `clearVars()` per cancellare i valori delle variabili in modo che non persistano negli hit successivi.

Questo metodo non accetta argomenti e non restituisce alcun valore. Il suo unico scopo è cancellare i valori delle variabili dall&#39;oggetto istanza. Questo metodo imposta gli elementi seguenti su `undefined`:

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

## Cancellare le variabili tramite Web SDK

Quando invii dati ad Adobe utilizzando il Web SDK, tutti i dati XDM vengono cancellati automaticamente.

## Cancellare le variabili tramite l’estensione Adobe Analytics

Imposta l’azione Cancella variabili durante la configurazione di una regola.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fare clic sull&#39;icona &#39;+&#39;
5. Scegli Adobe Analytics nel menu a discesa [!UICONTROL Extension] e imposta [!UICONTROL Action Type] su [!UICONTROL Clear Variables].

## s.clearVars() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Puoi chiamare il `s.clearVars()` in qualsiasi punto dell’implementazione, dopo aver creato un’istanza dell’istanza dell’oggetto Analytics.

```js
s.clearVars();
```
