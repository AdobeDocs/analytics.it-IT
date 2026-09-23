---
title: Profondità colore
description: Profondità colore del dispositivo.
feature: Dimensions
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
TQID: https://experienceleague.adobe.com/JLxm06wch2r7RslhdKx-gFLBLhMSXuWkb-0EYM7nT5s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
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
source-wordcount: '255'
ht-degree: 7%
---
# Profondità colore

La &#39;Profondità colore&#39; [dimensione](overview.md) indica quanti colori supporta il dispositivo. Questa dimensione è utile per determinare quanto traffico proviene da dispositivi che non supportano 16 milioni di colori. Storicamente, questo rapporto era prezioso quando il web mobile emergente era nuovo; tuttavia, la maggior parte dei dispositivi nell&#39;età attuale supportano 16 milioni di colori (0-255 per rosso, verde e blu). <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## Popolare questa dimensione con i dati

La profondità colore viene raccolta automaticamente, lato client, dalla proprietà `screen.colorDepth` del browser, che Adobe traduce in un formato leggibile tramite una tabella di ricerca. Funziona come previsto in qualsiasi implementazione AppMeasurement o Web SDK (tag), senza alcuna variabile da impostare. Se raccogli dati all’esterno di AppMeasurement o del Web SDK (ad esempio tramite l’API), invia un valore di bit valido a ogni hit.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (raccolta automatica) |
| **Campo Web SDK / XDM** | Nessuno (raccolta automatica) |
| **Parametro query** | [`c`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<colorDepth>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 20 byte |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi Dimension includono il numero di colori supportati dal dispositivo. Valori di esempio includono `"16 million (24-bit)"`, `"16 million (32-bit)"`, e `"65,536 (16-bit)"`. Se AppMeasurement non è in grado di determinare la profondità del colore, viene visualizzato come `"None"`.

>[!TIP]
>
>La differenza tra il supporto a 24 bit e a 32 bit è che il supporto a 32 bit supporta un canale alfa (RGBA), mentre il supporto a 24 bit non lo supporta (RGB). Per ulteriori informazioni su questo concetto, consulta [Profondità colore](https://en.wikipedia.org/wiki/Color_depth) su Wikipedia.
