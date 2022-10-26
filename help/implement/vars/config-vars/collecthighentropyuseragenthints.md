---
title: collectHighEntropyUserAgentHints
description: Utilizza la variabile collectHighEntropyUserAgentHint per determinare se Adobe richiederà suggerimenti entropici elevati dai browser Chromium (ad esempio Google Chrome e Microsoft Edge).
source-git-commit: 885a8f229fa814053e4766f3b38b6e7fb209fc00
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 4%

---


# collectHighEntropyUserAgentHint

Adobe Analytics utilizza suggerimenti client ad alta entropia per migliorare l’identificazione del dispositivo e del browser. Questa opzione è disponibile a partire dalla versione 2.23.0 di AppMeasurement.js. Ulteriori informazioni sui suggerimenti client in [panoramica e domande frequenti](/help/technotes/client-hints.md) nonché [Blog Google](https://web.dev/user-agent-client-hints/).

## raccogliere hint di entropia elevata utilizzando l’SDK per web

Gli hint client ad alta entropia fanno parte delle categorie di contesto in SDK per web. Vedi [Configurare l’SDK web per Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=en) per ulteriori dettagli.

## Raccogli hint ad alta entropia utilizzando l’estensione Adobe Analytics

**[!UICONTROL Collect high-entropy user-agent hints]** è una casella di controllo nel pannello a soffietto Generale durante la configurazione dell&#39;estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/#/@adobepm/data-collection) utilizzo delle credenziali AdobeID.

1. Fai clic sul pulsante desiderato [!UICONTROL tag property].

1. Vai a [!UICONTROL Extensions] scheda , quindi fai clic su [!UICONTROL Configure] in Adobe Analytics.

1. Espandi la [!UICONTROL General] fisarmonica, che rivela [!UICONTROL Collect high entropy user-agent hints] casella di controllo. Per impostazione predefinita, questa impostazione è deselezionata.

## collectHighEntropyUserAgentHint in AppMeasurement

La `s.collectHighEntropyUserAgentHints` La variabile determina se AppMeasurement richiede hint ad alta entropia dai browser Chromium (ad esempio, Google Chrome e Microsoft Edge). Questi suggerimenti vengono utilizzati da Adobe Analytics per migliorare l’identificazione del dispositivo e del browser.

Se impostato su TRUE, tutti i suggerimenti entropici elevati verranno richiesti dal browser.

`s.collectHighEntropyUserAgentHints = TRUE`

`s.collectHighEntropyUserAgentHints = FALSE`
