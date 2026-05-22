---
title: charSet
description: La variabile charSet determina la codifica utilizzata da Adobe per analizzare la richiesta di immagine.
feature: Appmeasurement Implementation
exl-id: 2a2660c6-809d-4b33-a846-01e49dd99c7f
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/bPK-uLu-IgKnJWGpAUnS7cmRm808jhetzm-Cyd2R39o'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 229
ht-degree: 17%

---

# charSet

La variabile `charSet` viene utilizzata da Adobe per convertire i dati in arrivo in UTF-8 per l&#39;archiviazione e il reporting da parte di Analytics. La maggior parte dei siti non deve impostare questa variabile.

Imposta questa variabile solo se nei report vengono visualizzati valori illeggibili ([mojibake](https://en.wikipedia.org/wiki/Mojibake)). Puoi impostare questa variabile pagina per pagina, se il tuo sito utilizza codifiche diverse su pagine diverse.

## Set di caratteri nel Web SDK

Il Web SDK supporta attualmente solo UTF-8 e non fornisce opzioni per modificare la codifica.

## Set di caratteri nell’estensione Adobe Analytics

Il set di caratteri è un campo nel pannello a soffietto [!UICONTROL General] durante la configurazione dell&#39;estensione Adobe Analytics in Raccolta dati Adobe Experience Platform.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in Adobe Analytics.
1. Espandi il pannello a soffietto [!UICONTROL General], che mostra il campo [!UICONTROL Character Set].

È possibile utilizzare un set di caratteri predefinito o un set di caratteri personalizzato. Evitare di modificare il valore da `UTF-8` a meno che non vengano visualizzati valori illeggibili nei report.

## s.charSet in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `charSet` è una stringa. Se in Adobe Analytics sono presenti valori illeggibili, impostare questa variabile sullo stesso valore del tag HTML `<meta charset="">` sul sito.

```js
s.charSet = "UTF-8";
```
