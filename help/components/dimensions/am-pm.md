---
title: AM/PM
description: Determina se l’hit si è verificato nelle ore AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '159'
ht-degree: 13%
---
# AM/PM

La [dimensione](overview.md) di &#39;AM/PM&#39; fornisce ad insight informazioni su se l&#39;hit si è verificato nelle ore AM o PM. L&#39;ora dell&#39;hit è basata sul fuso orario della suite di rapporti [](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Popolare questa dimensione con i dati

Questa dimensione deriva dalla marca temporale di ciascun hit; non esiste una variabile da impostare. La sua unica dipendenza è il fuso orario della suite di rapporti, che determina quali ore sono AM e quali PM.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal timestamp dell’hit) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal timestamp dell’hit) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Hit |

## Elementi dimensionali

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"AM"` e `"PM"`. L&#39;elemento dimensione `"AM"` si applica a tutti gli hit dalle 00:00 alle 01:59, mentre l&#39;elemento dimensione `"PM"` si applica a tutti gli hit dalle 12:00 alle 23:59.
