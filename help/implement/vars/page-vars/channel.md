---
title: channel
description: Compilate la dimensione "Sezioni del sito".
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# channel

La `channel` variabile memorizza in genere la sezione del sito su cui è collocata una determinata pagina. È utile determinare quali gruppi del sito sono più popolari. Questa variabile popola la dimensione &quot;Sezioni del sito&quot;.

## Canale in Adobe Experience Platform Launch

Puoi impostare il canale sia durante la configurazione dell&#39;estensione Analytics (variabili globali), sia in base alle regole.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Passate alla [!UICONTROL Rules] scheda, quindi fate clic sulla regola desiderata (o create una regola).
4. In [!UICONTROL Actions], fare clic su un&#39;azione esistente [!UICONTROL Adobe Analytics - Set Variables] o fare clic sull&#39;icona &quot;+&quot;.
5. Impostate il [!UICONTROL Extension] menu a discesa su Adobe Analytics e [!UICONTROL Action Type] su [!UICONTROL Set Variables].
6. Individuare la [!UICONTROL Channel] sezione.

Puoi impostare il canale su qualsiasi valore di stringa o elemento dati.

## s.channel in AppMeasurement e Launch editor di codice personalizzato

La `s.channel` variabile è una stringa che in genere contiene la sezione del sito della pagina. Ha un valore massimo di 100 byte; i valori più lunghi vengono troncati.

```js
s.channel = "Example site section";
```
