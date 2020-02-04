---
title: campagna
description: Compilare la dimensione "Codice di tracciamento".
translation-type: tm+mt
source-git-commit: c5a60bc9756af2742740dbc6a26a081f55ee3235

---


# campagna

La `campaign` variabile è dedicata alla raccolta dei codici di monitoraggio sul sito. Nelle versioni precedenti di Adobe Analytics, aveva un trattamento speciale da usare come suddivisione per la maggior parte delle dimensioni. Nella versione corrente di Adobe Analytics, si comporta come una eVar.

Questa variabile popola la dimensione &quot;Codice di tracciamento&quot;.

## Campaign in Adobe Experience Platform Launch

Puoi impostare la campagna sia durante la configurazione dell&#39;estensione di Analytics (variabili globali) che in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Campaign] sezione.

Potete impostare la campagna su un valore o su un parametro di stringa di query.

## s.campaign in AppMeasurement e Launch editor di codice personalizzato

La `s.campaign` variabile è una stringa che in genere contiene un codice di tracciamento utilizzato nelle attività di marketing. La sua lunghezza massima è di 255 byte; i valori superiori a 100 byte vengono troncati automaticamente quando inviati ad Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
