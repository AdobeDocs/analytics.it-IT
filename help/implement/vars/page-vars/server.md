---
title: server
description: Compilare la dimensione "Server".
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# server

La `server` variabile memorizza in genere il nome host del sito. È comunemente utilizzata nelle suite di rapporti che contengono dati da più domini. È funzionalmente identico a un prop.

## Server in Adobe Experience Platform Launch

Puoi impostare il server sia durante la configurazione dell&#39;estensione di Analytics (variabili globali) che in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Server] sezione.

È possibile impostare il server su qualsiasi valore di stringa o elemento dati.

## s.server in AppMeasurement e Launch editor di codice personalizzato

La `s.server` variabile è una stringa che in genere contiene il nome host del sito. Ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
// Set the server variable to a static string
s.server = "Example server";

// Automatically set the server variable to the site's hostname
s.server = window.location.hostname;
```
