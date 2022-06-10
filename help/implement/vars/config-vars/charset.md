---
title: charSet
description: La variabile charSet determina quale Adobe di codifica utilizza per analizzare la richiesta di immagine.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 0%

---

# charSet

La variabile charSet viene utilizzata da Adobe per convertire i dati in entrata in UTF-8 per l’archiviazione e il reporting da parte di Analytics. La maggior parte dei siti non deve impostare questa variabile.

Imposta questa variabile solo se visualizzi valori non elaborati ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) nei rapporti. Puoi impostare questa variabile pagina per pagina se il sito utilizza codifiche diverse su pagine diverse.

## Set di caratteri nell’SDK per web

L&#39;SDK per web supporta attualmente solo UTF-8 e non fornisce opzioni per modificare la codifica.

## Set di caratteri nell’estensione Adobe Analytics

Il set di caratteri è un campo sotto [!UICONTROL General] pannello a soffietto durante la configurazione dell’estensione Adobe Analytics in Adobe Experience Platform Data Collection.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** sotto Adobe Analytics.
1. Espandi la [!UICONTROL General] fisarmonica, che rivela [!UICONTROL Character Set] campo .

Puoi utilizzare un set di caratteri predefinito o personalizzato. Evita di modificare il valore da `UTF-8` a meno che nei rapporti non vengano visualizzati valori illeggibili.

## s.charSet in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `charSet` è una stringa. Se in Adobe Analytics sono presenti valori non validi, imposta questa variabile sullo stesso valore della variabile `<meta charset="">` Tag HTML sul sito.

```js
s.charSet = "UTF-8";
```
