---
title: linkName
description: Impostate il nome dell’hit di collegamento personalizzato.
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkName

Utilizzare la `linkName` variabile per determinare il valore della dimensione dei collegamenti personalizzati, dei collegamenti di download o dei collegamenti di uscita quando si esegue la `tl()` funzione successiva.

Se questa variabile è vuota, AppMeasurement ripristina la `linkURL` variabile.

## Nome collegamento in Adobe Experience Platform Launch

Potete impostare il campo del nome del collegamento quando configurate una regola per l&#39;invio di un beacon.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic sull&#39;icona &quot;+&quot;
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e su [!UICONTROL Action Type] Invia beacon.
6. Fare clic sul `s.tl()` pulsante di scelta che mostra il [!UICONTROL Link Name] campo.

## s.linkName nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.linkName` variabile è una stringa che determina il valore della dimensione per i collegamenti personalizzati, i collegamenti di download o i collegamenti di uscita (a seconda di cosa `s.linkType` si tratta). Può contenere fino a 100 byte.

> [!TIP] Questa variabile è il terzo parametro della `tl()` funzione e in genere non deve essere impostata come variabile standalone. Tuttavia, è possibile utilizzare la `linkName` variabile se non si desidera impostare i valori come argomenti nella `tl()` funzione.

```js
s.linkName = "Example custom link";
```

## Esempio

Le due seguenti chiamate di tracciamento dei collegamenti di esempio sono funzionalmente identiche. Sono metodi diversi per ottenere lo stesso hit di tracciamento dei collegamenti.

```js
// Set link tracking arguments as individual variables
s.linkType = "d";
s.linkName = "Example download link";
s.tl();

// Set link tracking arguments directly in the tl() function
s.tl(this,"d","Example download link");
```
