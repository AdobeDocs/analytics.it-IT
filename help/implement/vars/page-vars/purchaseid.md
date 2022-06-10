---
title: purchaseID
description: Deduplica gli hit in base a un identificatore di acquisto univoco.
feature: Variables
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# purchaseID

La `purchaseID` aiuta a evitare che i rapporti gonfiino gli hit contenenti lo stesso acquisto. Ad esempio, se un visitatore raggiunge la pagina di conferma dell’acquisto, in genere invii ad Adobe i dati relativi ai ricavi generati dalla transazione. Se l’utente aggiorna la pagina più volte o annota la pagina da visitare in un secondo momento, questi hit possono gonfiare i rapporti. La `purchaseID` La variabile deduplica le metriche quando più di un hit ha lo stesso ID acquisto.

Quando Adobe riconosce un hit come acquisto duplicato, tutti i dati di conversione (come eVar ed eventi) non vengono visualizzati nei rapporti. Nei feed di dati, la `duplicate_purchase` è impostato su `1`.

L’ID acquisto è valido per tutti i visitatori e non scade. Se un visitatore imposta un determinato ID acquisto, un visitatore diverso lo imposta un anno dopo, il secondo acquisto viene deduplicato.

## ID acquisto tramite SDK per web

ID acquisto: [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) nel campo XDM `commerce.order.purchaseID`.

## ID acquisto tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.purchaseID in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.purchaseID` è una stringa che contiene un identificatore univoco di un acquisto. È impostato sullo stesso hit di un evento di acquisto. Utilizza solo caratteri alfanumerici per compilare la variabile.

Questa variabile può memorizzare un massimo di 20 byte; vengono troncati i valori superiori a 20 byte. Se questo valore troncato corrisponde ai valori troncati successivi, gli hit successivi vengono deduplicati.

```js
s.purchaseID = "ABC123";
```

Se utilizzi `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>Non utilizzare una funzione di randomizzazione per generare un ID acquisto.
