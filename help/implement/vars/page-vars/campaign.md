---
title: campagna
description: Popolare la dimensione "Tracking Code" (Codice di tracciamento).
feature: Variables
exl-id: 2278d2b8-8d60-4634-a176-f027a237bc12
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---

# campagna

La `campaign` è dedicata alla raccolta dei codici di tracciamento sul sito. Nelle versioni precedenti di Adobe Analytics, aveva un trattamento speciale in cui poteva essere utilizzato come suddivisione per la maggior parte delle dimensioni. Nella versione corrente di Adobe Analytics, agisce in modo identico a un eVar.

Questa variabile popola la dimensione &quot;Tracking Code&quot; (Codice di tracciamento).

## Campaign utilizzando i tag in Adobe Experience Platform

Puoi impostare campaign sia durante la configurazione dell’estensione Analytics (variabili globali) che in regole.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
2. Fai clic sulla proprietà desiderata.
3. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata (o crea una regola).
4. Sotto [!UICONTROL Actions], fai clic su un [!UICONTROL Adobe Analytics - Set Variables] fare clic sull&#39;icona &quot;+&quot;.
5. Imposta la [!UICONTROL Extension] del menu a discesa Adobe Analytics e [!UICONTROL Action Type] a [!UICONTROL Set Variables].
6. Individua il [!UICONTROL Campaign] sezione .

Puoi impostare campaign su un valore o su un parametro di stringa query.

## s.campaign in AppMeasurement e nell’editor di codice personalizzato

La `s.campaign` è una stringa che in genere contiene un codice di tracciamento utilizzato nelle attività di marketing. La sua lunghezza massima è di 255 byte; i valori superiori a 255 byte vengono troncati automaticamente quando inviati ad Adobe.

```js
// Set the campaign variable to a static value
s.campaign = "abc123";

// Collect the cid query string parameter value from the URL
// https://example.com?cid=abc123
s.campaign = s.Util.getQueryParam("cid");
```
