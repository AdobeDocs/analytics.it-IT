---
title: clearVars
description: Cancella i valori dall'oggetto istanza.
feature: Appmeasurement Implementation
exl-id: 8ecb2b2d-7b66-4232-b0ea-b8c6cdcc1515
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 18%

---

# clearVars

Alcune implementazioni, ad esempio nelle applicazioni a pagina singola, richiedono più hit inviati sullo stesso caricamento di pagina. Utilizza il metodo `clearVars()` per cancellare i valori delle variabili in modo che non persistano negli hit successivi.

Questo metodo non accetta argomenti e non restituisce alcun valore. Il suo unico scopo è cancellare i valori delle variabili dall&#39;oggetto istanza. Questo metodo imposta i seguenti elementi su `undefined`:

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
4. In [!UICONTROL Actions], fare clic sull&#39;icona &#39;+&#39;
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Clear Variables].

## s.clearVars() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Puoi chiamare il metodo `s.clearVars()` in qualsiasi punto dell&#39;implementazione dopo aver creato un&#39;istanza dell&#39;oggetto Analytics.

```js
s.clearVars();
```
