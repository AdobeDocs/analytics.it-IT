---
title: charSet
description: La variabile charSet determina il tipo di codifica utilizzato dall’Adobe per analizzare la richiesta di immagine.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 17%

---

# charSet

La variabile charSet viene utilizzata da Adobe per convertire i dati in arrivo in UTF-8 per l’archiviazione e il reporting da parte di Analytics. La maggior parte dei siti non deve impostare questa variabile.

Imposta questa variabile solo se vengono visualizzati valori illeggibili ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) nei rapporti. Puoi impostare questa variabile pagina per pagina, se il tuo sito utilizza codifiche diverse su pagine diverse.

## Set di caratteri nell’SDK per web

L’SDK per web supporta attualmente solo UTF-8 e non fornisce opzioni per modificare la codifica.

## Set di caratteri nell’estensione Adobe Analytics

Il set di caratteri è un campo sotto [!UICONTROL General] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics in Raccolta dati Adobe Experience Platform.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL General], che mostra il campo [!UICONTROL Character Set].

È possibile utilizzare un set di caratteri predefinito o un set di caratteri personalizzato. Evita di modificare il valore da `UTF-8` a meno che nei rapporti non vengano visualizzati valori illeggibili.

## s.charSet in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `charSet` variabile è una stringa. Se in Adobe Analytics sono presenti valori illeggibili, imposta questa variabile sullo stesso valore del `<meta charset="">` HTML sul sito.

```js
s.charSet = "UTF-8";
```
