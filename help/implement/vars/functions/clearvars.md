---
title: clearVars
description: Cancella i valori dall'oggetto istanza.
feature: Variables
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 18%

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
5. Imposta il [!UICONTROL Extension] in Adobe Analytics e nella sezione [!UICONTROL Action Type] a [!UICONTROL Clear Variables].

## s.clearVars() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Puoi chiamare il `s.clearVars()` in qualsiasi punto dell’implementazione, dopo aver creato un’istanza dell’istanza dell’oggetto Analytics.

```js
s.clearVars();
```
