---
title: Risoluzione monitor
description: Risoluzione in pixel del monitor del visitatore.
feature: Dimensions
exl-id: 6bae65eb-4546-4d07-877d-6e257fbe6cfa
TQID: https://experienceleague.adobe.com/d3AuMT0seRbZpuKVGPeWo98Bkhc8tcJIP6gt4y-rq38
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
source-wordcount: '289'
ht-degree: 6%
---
# Risoluzione monitor

La &#39;risoluzione monitor&#39; [dimensione](overview.md) mostra l&#39;altezza e la larghezza dello schermo attivo in pixel. Questa dimensione è utile quando desideri comprendere dove si trova la &quot;piega&quot; sul sito per i visitatori o quanto i visitatori possono fare la loro finestra del browser. Sapere dove si trova la piega può consentirti di ottimizzare il contenuto da visualizzare.

Questa dimensione è diversa da quella del browser [height](browser-height.md) e [width](browser-width.md). Altezza/larghezza browser è il numero di pixel all’interno dello spazio visualizzabile del browser, mentre risoluzione monitor è il numero di pixel dell’intero monitor. Se desideri vedere la differenza tra queste due variabili sul tuo computer, apri la console del browser (F12 nella maggior parte dei browser) e copia e incolla il seguente codice nella console:

```js
"Monitor resolution: " + screen.width + "x" + screen.height + "; Browser resolution: " + window.innerWidth + "x" + window.innerHeight;
```

Le dimensioni del browser sono sempre inferiori alla risoluzione del monitor, poiché non includono la navigazione o i bordi del browser.

## Popolare questa dimensione con i dati

La risoluzione del monitoraggio viene raccolta automaticamente, lato client, dalle proprietà `screen.width` e `screen.height` del browser. Funziona come previsto in qualsiasi implementazione AppMeasurement o Web SDK (tag), senza alcuna variabile da impostare. Se raccogli dati all’esterno di AppMeasurement o del Web SDK (ad esempio tramite l’API), invia il valore nelle richieste di immagini. Se manca o una libreria di raccolta dati non è in grado di raccogliere la risoluzione del monitoraggio, tali dati sono elencati in [!UICONTROL `Not Specified`].

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (raccolta automatica) |
| **Campo Web SDK / XDM** | Nessuno (raccolta automatica) |
| **Parametro query** | [`s`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<resolution>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 20 byte |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi Dimension includono tutte le risoluzioni del monitor raccolte. I valori di esempio includono `1920 x 1080`, `1366 x 768` e `1280 x 720`.
