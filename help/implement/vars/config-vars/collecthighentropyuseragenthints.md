---
title: collectHighEntropyUserAgentHints
description: Utilizza la variabile collectHighEntropyUserAgentHints per determinare se Adobe richiederà suggerimenti entropici elevati dai browser Chromium (ad esempio Google Chrome e Microsoft Edge).
exl-id: 97cfa0f9-b35d-4c73-822f-adf30d0b7efc
feature: Appmeasurement Implementation
role: Admin, Developer
TQID: https://experienceleague.adobe.com/jipxox--J6tVTjpES3YuOTOqL-SXvCMLSvvbpj620Q4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 223
ht-degree: 81%

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

La variabile `s.collectHighEntropyUserAgentHints` determina se AppMeasurement richiede hint ad alta entropia dai browser Chromium (ad esempio, Google Chrome o Microsoft Edge). Questi suggerimenti vengono utilizzati da Adobe Analytics per migliorare l’identificazione del dispositivo e del browser.

Se è impostato su `true`, tutti gli hint ad alta entropia verranno richiesti dal browser.

```js
s.collectHighEntropyUserAgentHints = true;
```
