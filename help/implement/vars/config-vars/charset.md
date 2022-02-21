---
title: charSet
description: La variabile charSet determina quale Adobe di codifica utilizza per analizzare la richiesta di immagine.
feature: Variables
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 1%

---

# charSet

La variabile charSet viene utilizzata da Adobe per convertire i dati in entrata in UTF-8 per l’archiviazione e il reporting da parte di Analytics. La maggior parte dei siti non deve impostare questa variabile.

Imposta questa variabile solo se visualizzi valori non elaborati ([mojibake](https://en.wikipedia.org/wiki/Mojibake)) nei rapporti. Puoi impostare questa variabile pagina per pagina se il sito utilizza codifiche diverse su pagine diverse.

## Set di caratteri in Adobe Experience Platform

Il set di caratteri è un campo sotto [!UICONTROL General] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Interfaccia utente per la raccolta dati](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante [!UICONTROL Configure] sotto Adobe Analytics.
1. Espandi la [!UICONTROL General] fisarmonica, che rivela [!UICONTROL Character Set] campo .

Puoi utilizzare un set di caratteri predefinito o personalizzato. Evita di modificare il valore da `UTF-8` a meno che nei rapporti non vengano visualizzati valori illeggibili.

## s.charSet in AppMeasurement e nell&#39;editor di codice personalizzato

La `charSet` è una stringa. Se in Adobe Analytics sono presenti valori non validi, imposta questa variabile sullo stesso valore della variabile `<meta charset="">` Tag HTML sul sito.

```js
s.charSet = "UTF-8";
```
