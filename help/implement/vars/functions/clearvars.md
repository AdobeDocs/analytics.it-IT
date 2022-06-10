---
title: clearVars
description: Cancella i seguenti valori dall'oggetto instance. Questa funzione rimuove gli elementi (li imposta come "non definiti").
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 1%

---

# clearVars

Alcune implementazioni, ad esempio nelle applicazioni a pagina singola, richiedono più hit inviati allo stesso caricamento della pagina. Utilizza la `clearVars()` per cancellare i valori delle variabili in modo che non persistano negli hit successivi.

Questo metodo non accetta argomenti e non restituisce alcun valore. Il suo unico scopo è cancellare i valori delle variabili dall&#39;oggetto instance. Questo metodo imposta gli elementi seguenti su `undefined`:

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

## Cancellare le variabili con l’SDK per web

Quando invii dati ad Adobe tramite l’SDK per web, tutti i dati XDM vengono cancellati automaticamente.

## Cancella variabili utilizzando l&#39;estensione Adobe Analytics

Imposta l&#39;azione Cancella variabili durante la configurazione di una regola.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà tag desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic sull&#39;icona &quot;+&quot;
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Clear Variables].

## s.clearVars() in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

Puoi chiamare il `s.clearVars()` in qualsiasi punto dell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.clearVars();
```
