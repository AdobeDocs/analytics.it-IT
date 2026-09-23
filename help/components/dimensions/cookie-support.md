---
title: Supporto per cookie
description: Determina se il browser supporta i cookie.
feature: Dimensions
exl-id: 07d4fe12-0d60-469d-98b1-e93ce5a0fd21
TQID: https://experienceleague.adobe.com/axOR-Ut8kkRSCTYPescoSCa44g25E8xxp4gg-yQlyYw
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
source-wordcount: '211'
ht-degree: 9%
---
# Supporto per cookie

Il rapporto &quot;Supporto cookie&quot; [dimension](overview.md) indica se il browser supporta i cookie per un determinato hit. È utile determinare la proporzione di visitatori che utilizzano browser che supportano i cookie e di quelli che li disabilitano intenzionalmente.

## Popolare questa dimensione con i dati

Il supporto dei cookie viene raccolto automaticamente, lato client: AppMeasurement tenta di impostare un cookie denominato `s_cc`, quindi segnala se esiste: `Y` se il browser supporta e dispone di cookie abilitati oppure `N` se i cookie sono disabilitati. Funziona come previsto in qualsiasi implementazione AppMeasurement o Web SDK (tag), senza alcuna variabile da impostare. Se raccogli dati all&#39;esterno di AppMeasurement o Web SDK (ad esempio tramite l&#39;API), invia `Y` o `N` per ogni hit.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (raccolta automatica) |
| **Campo Web SDK / XDM** | Nessuno (raccolta automatica) |
| **Parametro query** | [`k`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<cookiesEnabled>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 1 byte |
| **Persistenza** | N/D |

## Elementi dimensionali

Gli elementi della dimensione includono `Enabled`, `Disabled` e `Unknown`.

* **`Enabled`**: il browser supporta i cookie e li ha abilitati.
* **`Disabled`**: il browser non supporta i cookie o il visitatore li ha disabilitati.
* **`Unknown`**: AppMeasurement non è in grado di determinare il supporto dei cookie. La stringa di query `k` non è presente nella richiesta di immagine.
