---
title: charSet
description: La variabile charSet determina la codifica utilizzata da Adobe per analizzare la richiesta di immagine.
translation-type: tm+mt
source-git-commit: 70410af433f540764b71bd29a81ff9d8210cb95c
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 2%

---


# charSet

La variabile charSet viene utilizzata da Adobe per convertire i dati in entrata in UTF-8 per l&#39;archiviazione e il reporting da parte di  Analytics. La maggior parte dei siti non deve impostare questa variabile.

Impostate questa variabile solo se nei rapporti sono visualizzati valori non validi ([mojibake](https://en.wikipedia.org/wiki/Mojibake)). È possibile impostare questa variabile pagina per pagina se il sito utilizza codifiche diverse su pagine diverse.

## Set di caratteri in  lancio Adobe Experience Platform

Set di caratteri è un campo situato sotto la struttura di [!UICONTROL General] navigazione quando si configura l’estensione Adobe  Analytics.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic sul [!UICONTROL Configure] pulsante sotto Adobe  Analytics.
4. Espandere la [!UICONTROL General] struttura a soffietto, che mostra il [!UICONTROL Character Set] campo.

Potete usare un set di caratteri predefinito o personalizzato. Evitate di modificare il valore da `UTF-8` a meno che nei rapporti non vengano visualizzati valori illeggibili.

## s.charSet nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `charSet` variabile è una stringa. Se avete valori non validi in Adobe  Analytics, impostate questa variabile sullo stesso valore del tag `<meta charset="">` HTML presente sul sito.

```js
s.charSet = "UTF-8";
```
