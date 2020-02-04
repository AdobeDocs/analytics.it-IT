---
title: charSet
description: La variabile charSet determina la codifica utilizzata da Adobe per analizzare la richiesta di immagine.
translation-type: tm+mt
source-git-commit: f769da139d9890fd736a9b277934b11aa131e166

---


# charSet

La variabile charSet è utilizzata da Adobe per convertire i dati in entrata in UTF-8 per l&#39;archiviazione e il reporting da parte di Analytics. Se il sito utilizza un charSet diverso da UTF-8, questa variabile consente la corretta codifica dei dati da parte di Adobe. Questa variabile può essere impostata pagina per pagina se il sito utilizza codifiche diverse su pagine diverse.

## Set di caratteri in Adobe Experience Platform Launch

Set di caratteri è un campo situato sotto la struttura di [!UICONTROL General] navigazione quando si configura l’estensione Adobe Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante in Adobe Analytics.
4. Espandere la [!UICONTROL General] struttura a soffietto, che mostra il [!UICONTROL Character Set] campo.

Potete usare un set di caratteri predefinito o personalizzato. Questo valore deve corrispondere alla codifica dei caratteri sul sito. Utilizzano la maggior parte dei siti `UTF-8`.

## s.charSet nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `charSet` variabile è una stringa. Impostate questa variabile sullo stesso valore del tag `<meta charset="">` HTML sul sito.

```js
s.charSet = "UTF-8";
```
