---
title: purchaseID
description: Deduplica gli hit in base a un identificatore di acquisto univoco.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 8%

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

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

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
