---
title: purchaseID
description: Deduplica gli hit in base a un identificatore di acquisto univoco.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 4bd46fd5a9b98bcca67a66c87c9bca67fa00061a
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 15%

---

# purchaseID

Il `purchaseID` variabile consente di evitare che gli hit contenenti lo stesso acquisto gonfiino i rapporti. Ad esempio, se un visitatore raggiunge la pagina di conferma dell’acquisto, in genere invii ad Adobe i dati relativi ai ricavi generati dalla transazione. Se l’utente aggiorna la pagina più volte o la inserisce nei segnalibri per visitarla in un secondo momento, tali hit possono gonfiare i rapporti. Il `purchaseID` la variabile deduplica le metriche quando più hit hanno lo stesso ID acquisto.

Quando Adobe riconosce un hit come acquisto duplicato, tutti i dati di conversione (come eVar ed eventi) non vengono visualizzati nel reporting. Nei feed di dati, la funzione `duplicate_purchase` è impostata su `1`.

Gli ID acquisto si applicano a tutti i visitatori e scadono dopo 37 mesi. Se un visitatore imposta un determinato ID acquisto, un visitatore diverso imposta lo stesso ID acquisto un anno dopo, il secondo acquisto viene deduplicato.

## ID acquisto tramite Web SDK

L’ID acquisto è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.purchaseID`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.purchaseID`

## ID acquisto tramite l’estensione Adobe Analytics

Puoi impostare l’ID acquisto sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Imposta il [!UICONTROL Extension] in Adobe Analytics e nella sezione [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Purchase ID].

Puoi impostare l’ID acquisto su un valore o su un elemento dati. Puoi anche copiare il valore da un’altra variabile di Analytics.

## s.purchaseID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.purchaseID` variabile è una stringa che contiene un identificatore univoco di un acquisto. È impostato sullo stesso hit di un evento di acquisto. Utilizza solo caratteri alfanumerici per compilare questa variabile.

Questa variabile può memorizzare un massimo di 20 byte; i valori superiori a 20 byte vengono troncati. Se questo valore troncato corrisponde ai valori troncati successivi, gli hit successivi vengono deduplicati.

```js
s.purchaseID = "ABC123";
```

Se utilizzi il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>Non utilizzare una funzione di randomizzazione per generare un ID acquisto.
