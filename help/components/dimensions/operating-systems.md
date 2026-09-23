---
title: Sistema operativo
description: Il sistema operativo del visitatore.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
TQID: https://experienceleague.adobe.com/WM6GQ-AhLmtudRWXF6lOez6DaVxMBU3rSaEb2UdsXdc
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
source-wordcount: '205'
ht-degree: 15%
---
# Sistema operativo

La [dimensione](overview.md) del &#39;sistema operativo&#39; mostra il sistema operativo e la versione utilizzati dal visitatore. Se nella proprietà web sono presenti funzioni specifiche per il sistema operativo, questa dimensione ti aiuta a capire quali sistemi operativi sono più comuni.

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

Gli elementi di Dimension includono i sistemi operativi utilizzati dai visitatori. Gli esempi includono `"Windows 10"`, `"OS X 10.15.7"` e `"Android 9"`.

## Tracciamento delle versioni precise del sistema operativo

Con l’evoluzione del settore verso gli hint client, alcune versioni dei sistemi operativi sono potenzialmente confuse. Ad esempio, &quot;Windows 10&quot; e &quot;Windows 11&quot; possono essere raggruppati in &quot;Windows 10&quot; se non si raccolgono hint client ad alta entropia. Per informazioni dettagliate, consulta [Client hints](/help/technotes/client-hints.md) nella guida delle note tecniche.
