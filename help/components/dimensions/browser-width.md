---
title: Larghezza browser - con bucket
description: Larghezza in pixel della finestra del browser.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
TQID: https://experienceleague.adobe.com/f9AknIwL-9ZMJ8tnGMxpUNmlkQiFmbjI3gtlP3KZtSQ
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
# Larghezza browser

La &#39;Larghezza browser - con bucket&#39; [dimensione](overview.md) mostra la larghezza della finestra del browser, classificata in gruppi predefiniti. Questa dimensione è utile quando desideri comprendere il modo in cui i visitatori visualizzano il contenuto. Comprendere la larghezza in cui vengono generalmente visualizzati i contenuti può consentirti di ottimizzarli.

Questa dimensione è diversa dalla larghezza dello schermo. Larghezza browser è il numero di pixel all’interno dello spazio visualizzabile del browser, mentre la larghezza dello schermo è la larghezza dell’intero monitor in pixel. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

La larghezza del browser è sempre inferiore o uguale alla larghezza dello schermo, in quanto non include barre di scorrimento o bordi.

>[!NOTE]
>
>Data Warehouse fornisce anche una dimensione &#39;[!UICONTROL Browser width - granular]&#39; che riporta la larghezza esatta in pixel anziché raggruppare i valori in bucket predefiniti.

## Popolare questa dimensione con i dati

La larghezza del browser viene raccolta automaticamente, lato client, dalla proprietà `window.innerWidth` del browser. Funziona come previsto in qualsiasi implementazione AppMeasurement o Web SDK (tag), senza alcuna variabile da impostare. Se raccogli dati all’esterno di AppMeasurement o del Web SDK (ad esempio tramite l’API), invia il valore al primo hit di ogni visita. Se la larghezza del browser viene regolata a metà visita, la regolazione non viene registrata.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (raccolta automatica) |
| **Campo Web SDK / XDM** | Nessuno (raccolta automatica) |
| **Parametro query** | [`bw`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<browserWidth>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Intervallo di valori** | 0-65.535 |
| **Persistenza** | Visita |

## Elementi dimensionali

Gli elementi Dimension includono tutte le larghezze del browser raccolte, classificate in gruppi predefiniti. Ad esempio, se la larghezza del browser di un hit è `1280`, viene raggruppato nell&#39;elemento dimensione `1200 to 1299`.
