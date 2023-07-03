---
title: collectHighEntropyUserAgentHints
description: Utilizza la variabile collectHighEntropyUserAgentHints per determinare se Adobe richiederà suggerimenti entropici elevati dai browser Chromium (ad esempio Google Chrome e Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Variables
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 80%

---

# collectHighEntropyUserAgentHints

Adobe Analytics utilizza suggerimenti client ad alta entropia per migliorare l’identificazione del dispositivo e del browser. Questa opzione è disponibile a partire dalla versione 2.23.0 di AppMeasurement.js. Ulteriori informazioni sui suggerimenti client in [panoramica e domande frequenti](/help/technotes/client-hints.md) nonché [Blog Google](https://web.dev/user-agent-client-hints/).

## Raccogliere hint di entropia elevata utilizzando l’SDK per web

Gli hint client ad alta entropia fanno parte delle categorie di contesto in SDK per web. Vedi [Configurare l’SDK web per Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) per ulteriori dettagli.

## Raccoglere hint ad alta entropia utilizzando l’estensione Adobe Analytics

**[!UICONTROL Collect high-entropy user-agent hints]** è una casella di controllo nel pannello a soffietto Generale durante la configurazione dell’estensione Adobe Analytics.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/#/@adobepm/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sul pulsante desiderato [!UICONTROL tag property].
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic su [!UICONTROL Configure] in Adobe Analytics.
1. Espandi il soffietto [!UICONTROL General], che mostra la casella [!UICONTROL Collect high entropy user-agent hints]. Per impostazione predefinita, questa impostazione è deselezionata.

## collectHighEntropyUserAgentHints in AppMeasurement

Il `s.collectHighEntropyUserAgentHints` variabile determina se AppMeasurement richiede hint ad alta entropia dai browser Chromium (ad esempio, Google Chrome o Microsoft Edge). Questi suggerimenti vengono utilizzati da Adobe Analytics per migliorare l’identificazione del dispositivo e del browser.

Se impostato su `true`, tutti gli hint ad alta entropia verranno richiesti dal browser.

```js
s.collectHighEntropyUserAgentHints = true;
```
