---
title: Tipi di sistemi operativi
description: Il sistema operativo indipendentemente dalla versione.
feature: Dimensions
exl-id: 0afd5261-98e8-4247-865a-1b8844c53ff4
TQID: https://experienceleague.adobe.com/onZ7Wt7A44gd42hqmjqYHL7OF6VtBke1NDgu1tsnMIg
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 20%
---
# Tipi di sistemi operativi

La [dimensione](overview.md) dei &#39;tipi di sistema operativo&#39; mostra il sistema operativo generale utilizzato dal visitatore, indipendentemente da specifiche versioni. Questa dimensione è utile per capire non solo quali sistemi operativi e versioni specifiche sono più comuni, ma anche quali sono utilizzate dai visitatori tipici della piattaforma del sistema operativo.

## Popolare questa dimensione con i dati

Adobe deriva questa dimensione dall&#39;intestazione HTTP `User-Agent`, confrontandola con una tabella di ricerca interna gestita da Adobe in collaborazione con [DeviceAtlas](https://deviceatlas.com/). Nessuna variabile da impostare.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dall’agente utente) |
| **Campo Web SDK / XDM** | Nessuno (derivato dall’agente utente) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

* Per le implementazioni di AppMeasurement, questa dimensione funziona in modo predefinito.
* Per le implementazioni di Web SDK, abilita [!UICONTROL Device Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi di Dimension includono il tipo di sistema operativo utilizzato. Gli esempi includono `"Microsoft Windows"`, `"Apple Macintosh"`, `"Google Android"` e `"Apple iOS"`.
