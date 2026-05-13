---
title: Giorno feriale/Fine settimana
description: Determina se l’hit si è verificato durante un giorno feriale o un weekend.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
TQID: https://experienceleague.adobe.com/9TJv-49ub1zHsgEGtBeoJVoHhsBktlOr7QhmgLdLRSo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 105
ht-degree: 28%

---

# Giorno feriale/Fine settimana

La [dimensione](overview.md) di &#39;Giorno feriale/Fine settimana&#39; fornisce ad insight informazioni se l&#39;hit si è verificato durante un giorno feriale (lunedì-venerdì) o un weekend (sabato-domenica). L&#39;ora dell&#39;hit è basata sul fuso orario della suite di rapporti [&#128279;](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"Weekday"` e `"Weekend"`. L&#39;elemento dimensione `"Weekday"` si applica a tutti gli hit dal lunedì al venerdì, mentre l&#39;elemento dimensione `"Weekend"` si applica a tutti gli hit il sabato e la domenica.
