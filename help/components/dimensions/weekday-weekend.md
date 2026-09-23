---
title: Giorno feriale/Fine settimana
description: Determina se l’hit si è verificato durante un giorno feriale o un weekend.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
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
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 13%
---
# Giorno feriale/Fine settimana

La [dimensione](overview.md) di &#39;Giorno feriale/Fine settimana&#39; fornisce ad insight informazioni se l&#39;hit si è verificato durante un giorno feriale (lunedì-venerdì) o un weekend (sabato-domenica). L&#39;ora dell&#39;hit è basata sul fuso orario della suite di rapporti [&#128279;](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Popolare questa dimensione con i dati

Questa dimensione deriva dalla marca temporale di ciascun hit; non esiste una variabile da impostare. L’unica dipendenza è il fuso orario della suite di rapporti, che determina il giorno della settimana per ogni hit.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dal timestamp dell’hit) |
| **Campo Web SDK / XDM** | Nessuno (derivato dal timestamp dell’hit) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | Hit |

## Elementi dimensionali

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"Weekday"` e `"Weekend"`. L&#39;elemento dimensione `"Weekday"` si applica a tutti gli hit dal lunedì al venerdì, mentre l&#39;elemento dimensione `"Weekend"` si applica a tutti gli hit il sabato e la domenica.
