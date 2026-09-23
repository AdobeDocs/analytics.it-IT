---
title: Altezza browser - con bucket
description: Altezza della finestra del browser in pixel.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 4%
---
# Altezza browser

In &#39;Altezza browser - bucket&#39; [dimensione](overview.md) è visualizzata l&#39;altezza della finestra del browser, classificata in gruppi predefiniti. Questa dimensione è utile quando desideri capire dove si trova la &quot;piega&quot; sul sito per i visitatori. Sapere dove si trova la piega può consentirti di ottimizzare il contenuto da visualizzare.

Questa dimensione è diversa dall’altezza dello schermo. L&#39;altezza del browser è il numero di pixel all&#39;interno dello spazio visualizzabile del browser, mentre l&#39;altezza dello schermo è l&#39;altezza dell&#39;intero monitor in pixel. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

L&#39;altezza del browser è in genere inferiore o uguale all&#39;altezza dello schermo, poiché l&#39;altezza del browser non include la navigazione o i bordi.

>[!NOTE]
>
>Data Warehouse fornisce anche una dimensione &#39;[!UICONTROL Browser height - granular]&#39; che riporta l&#39;altezza esatta dei pixel invece di raggruppare i valori in bucket predefiniti.

## Popolare questa dimensione con i dati

L&#39;altezza del browser viene raccolta automaticamente, lato client, dalla proprietà `window.innerHeight` del browser. Funziona come previsto in qualsiasi implementazione AppMeasurement o Web SDK (tag), senza alcuna variabile da impostare. Se raccogli dati all’esterno di AppMeasurement o del Web SDK (ad esempio tramite l’API), invia il valore al primo hit di ogni visita. Se l’altezza del browser viene regolata a metà visita, la regolazione non viene registrata.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (raccolta automatica) |
| **Campo Web SDK / XDM** | Nessuno (raccolta automatica) |
| **Parametro query** | [`bh`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<browserHeight>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Intervallo di valori** | 0-65.535 |
| **Persistenza** | Visita |

## Elementi dimensionali

Gli elementi Dimension includono tutte le altezze del browser raccolte, classificate in gruppi predefiniti. Ad esempio, se l&#39;altezza del browser di un hit è `720`, viene raggruppato nell&#39;elemento dimensione `700 to 799`.
