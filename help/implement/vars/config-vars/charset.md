---
title: charSet
description: La variabile charSet determina il tipo di codifica utilizzato dall’Adobe per analizzare la richiesta di immagine.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 17%

---

# charSet

La variabile `charSet` viene utilizzata da Adobe per convertire i dati in arrivo in UTF-8 per l&#39;archiviazione e il reporting da parte di Analytics. La maggior parte dei siti non deve impostare questa variabile.

Imposta questa variabile solo se nei report vengono visualizzati valori illeggibili ([mojibake](https://en.wikipedia.org/wiki/Mojibake)). Puoi impostare questa variabile pagina per pagina, se il tuo sito utilizza codifiche diverse su pagine diverse.

## Set di caratteri nell’SDK per web

L’SDK per web supporta attualmente solo UTF-8 e non fornisce opzioni per modificare la codifica.

## Set di caratteri nell’estensione Adobe Analytics

Il set di caratteri è un campo nel pannello a soffietto [!UICONTROL General] durante la configurazione dell&#39;estensione Adobe Analytics in Raccolta dati Adobe Experience Platform.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL General], che mostra il campo [!UICONTROL Character Set].

È possibile utilizzare un set di caratteri predefinito o un set di caratteri personalizzato. Evitare di modificare il valore da `UTF-8` a meno che non vengano visualizzati valori illeggibili nei report.

## s.charSet in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `charSet` è una stringa. Se in Adobe Analytics sono presenti valori illeggibili, impostare questa variabile sullo stesso valore del tag HTML `<meta charset="">` sul sito.

```js
s.charSet = "UTF-8";
```
