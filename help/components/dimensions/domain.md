---
title: Dominio
description: L’organizzazione o l’ISP utilizzato dal visitatore per accedere a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
    internal-label: Methods
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
source-wordcount: '195'
ht-degree: 14%
---
# Dominio

La [dimensione](overview.md) del &#39;dominio&#39; riporta i punti di accesso utilizzati dai visitatori per accedere a Internet.

>[!NOTE]
>
>Data Warehouse include una dimensione ritirata &#39;[!UICONTROL Domains]&#39; (plural) che riporta informazioni simili. Adobe consiglia di utilizzare questa dimensione, &#39;[!UICONTROL Domain]&#39; (singolare), per coerenza.

## Popolare questa dimensione con i dati

Adobe deriva questa dimensione lato server dall’indirizzo IP del visitatore, utilizzando diversi metodi, tra cui la ricerca DNS inversa, per determinare il dominio del punto di accesso. Adobe collabora con [elemento digitale](https://www.digitalelement.com/) per mantenere questa ricerca. Nessuna variabile da impostare.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dall’indirizzo IP del visitatore) |
| **Campo Web SDK / XDM** | Nessuno (derivato dall’indirizzo IP del visitatore) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

* Per le implementazioni di AppMeasurement, questa dimensione funziona in modo predefinito.
* Per le implementazioni di Web SDK, abilita [!UICONTROL Network Lookup] quando [si configura uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=it).

## Elementi dimensionali

Gli elementi dimensionali di esempio includono `comcast.net`, `rr.com`, `sbcglobal.net` e `amazonaws.com`. Questi domini sono punti di accesso e non necessariamente il dominio che rappresenta un ISP o un’organizzazione.

I valori Dimension `None` indicano che il proprietario dell&#39;indirizzo IP del punto di accesso non ha fornito un dominio.
