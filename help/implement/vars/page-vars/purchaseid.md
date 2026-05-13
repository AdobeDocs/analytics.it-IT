---
title: purchaseID
description: Deduplica gli hit in base a un identificatore di acquisto univoco.
feature: Appmeasurement Implementation
exl-id: 7a4d7f08-65ae-4541-a94e-cc6c445c01db
role: Admin, Developer
TQID: https://experienceleague.adobe.com/A8QIQQbtDhZcQmnokBcQdMqJVAbu1PD7N363QdHcSJc
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 356
ht-degree: 16%

---

# purchaseID

La variabile `purchaseID` consente di evitare che gli hit contenenti lo stesso acquisto gonfiino i rapporti. Ad esempio, se un visitatore raggiunge la pagina di conferma dell’acquisto, in genere invii ad Adobe dati sui ricavi generati dalla transazione. Se l’utente aggiorna la pagina più volte o la inserisce nei segnalibri per visitarla in un secondo momento, tali hit possono gonfiare i rapporti. La variabile `purchaseID` deduplica le metriche quando più hit hanno lo stesso ID acquisto.

Quando Adobe riconosce un hit come acquisto duplicato, tutti i dati di conversione (come eVar ed eventi) non vengono visualizzati nel reporting. Nei feed di dati, la colonna `duplicate_purchase` è impostata su `1`.

Gli ID acquisto si applicano a tutti i visitatori e scadono dopo 37 mesi. Se un visitatore imposta un determinato ID acquisto, un visitatore diverso imposta lo stesso ID acquisto un anno dopo, il secondo acquisto viene deduplicato.

## ID acquisto tramite Web SDK

L’ID acquisto è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.commerce.order.purchaseID`
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.purchaseID`

## ID acquisto tramite l’estensione Adobe Analytics

Puoi impostare l’ID acquisto sia durante la configurazione dell’estensione Analytics (variabili globali) sia nelle regole.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata (o crea una regola).
4. Nella sezione [!UICONTROL Actions], fai clic su un’azione [!UICONTROL Adobe Analytics - Set Variables] esistente o fai clic sull’icona “+”.
5. Impostare l&#39;elenco a discesa [!UICONTROL Extension] su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individua la sezione [!UICONTROL Purchase ID].

Puoi impostare l’ID acquisto su un valore o su un elemento dati. Puoi anche copiare il valore da un’altra variabile di Analytics.

## s.purchaseID in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.purchaseID` è una stringa che contiene un identificatore univoco di un acquisto. È impostato sullo stesso hit di un evento di acquisto. Utilizza solo caratteri alfanumerici per compilare questa variabile.

Questa variabile può memorizzare un massimo di 20 byte; i valori superiori a 20 byte vengono troncati. Se questo valore troncato corrisponde ai valori troncati successivi, gli hit successivi vengono deduplicati.

```js
s.purchaseID = "ABC123";
```

Se si utilizza il `digitalData` [livello dati](../../prepare/data-layer.md):

```js
s.purchaseID = digitalData.transaction.transactionID;
```

>[!CAUTION]
>
>Non utilizzare una funzione di randomizzazione per generare un ID acquisto.
