---
title: charSet
description: La variabile charSet determina quale Adobe di codifica utilizza per analizzare la richiesta di immagine.
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '189'
ht-degree: 1%

---

# charSet

La variabile charSet viene utilizzata da Adobe per convertire i dati in entrata in UTF-8 per l’archiviazione e il reporting da parte di Analytics. La maggior parte dei siti non deve impostare questa variabile.

Imposta questa variabile solo se nei rapporti sono presenti valori non elaborati ([mojibake](https://en.wikipedia.org/wiki/Mojibake)). Puoi impostare questa variabile pagina per pagina se il sito utilizza codifiche diverse su pagine diverse.

## Set di caratteri in Adobe Experience Platform

Il set di caratteri è un campo sotto il pannello a soffietto [!UICONTROL General] durante la configurazione dell’estensione Adobe Analytics.

1. Vai a `experience.adobe.com` e accedi quando richiesto.
1. Select [!UICONTROL Launch / Data Collection].
1. Fare clic su [!UICONTROL Go to Launch / Data Collection], quindi selezionare [!UICONTROL Tags].
1. Fai clic sulla proprietà desiderata.
1. Vai alla scheda [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] in Adobe Analytics.
1. Espandi il [!UICONTROL General] pannello a soffietto, che mostra il campo [!UICONTROL Character Set] .

Puoi utilizzare un set di caratteri predefinito o personalizzato. Evita di modificare il valore da `UTF-8` a meno che nei rapporti non siano visualizzati valori non validi.

## s.charSet in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `charSet` è una stringa. Se in Adobe Analytics sono presenti valori non validi, imposta questa variabile sullo stesso valore del tag HTML `<meta charset="">` sul sito.

```js
s.charSet = "UTF-8";
```
