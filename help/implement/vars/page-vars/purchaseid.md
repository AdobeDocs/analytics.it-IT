---
title: purchaseID
description: Deduplicare gli hit in base a un identificatore di acquisto univoco.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---


# purchaseID

La `purchaseID` variabile aiuta a evitare che gli hit contenenti lo stesso acquisto possano generare report in eccesso. Ad esempio, se un visitatore raggiunge la pagina di conferma dell&#39;acquisto, in genere invii ad Adobe i dati relativi alle entrate generate dalla transazione. Se l’utente aggiorna la pagina più volte o crea segnalibri per la pagina da visitare in un secondo momento, gli hit possono gonfiare i rapporti. La `purchaseID` variabile deduplica le metriche quando più hit hanno lo stesso ID acquisto.

Quando Adobe riconosce un hit come acquisto duplicato, tutti i dati di conversione (ad esempio eVar ed eventi) non vengono visualizzati nel reporting. Nei feed di dati, la `duplicate_purchase` colonna è impostata su `1`.

L&#39;ID acquisto si applica a tutti i visitatori e non scade. Se un visitatore imposta un determinato ID acquisto, un visitatore diverso imposta lo stesso ID acquisto un anno dopo, il secondo viene deduplicato.

## ID acquisto  lancio Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.purchaseID in AppMeasurement e Launch editor di codici personalizzati

La `s.purchaseID` variabile è una stringa che contiene un identificatore univoco per un acquisto. È impostata sullo stesso hit di un evento di acquisto. Per compilare questa variabile è possibile utilizzare solo caratteri alfanumerici.

Questa variabile può contenere un massimo di 20 byte; vengono troncati valori superiori a 20 byte. Se questo valore troncato corrisponde ai valori troncati successivi, gli hit successivi vengono deduplicati.

```js
s.purchaseID = "ABC123";
```

>[!NOTE]
>
>Non utilizzate una funzione di randomizzazione per generare un ID acquisto. Adobe consiglia di utilizzare un livello [](../../prepare/data-layer.md) dati per memorizzare un ID acquisto specificato.
