---
title: AM/PM
description: Determina se l’hit si è verificato nelle ore AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
TQID: https://experienceleague.adobe.com/R1syrJ7ylIe2ywH1isX4sjR2O84-8eL-jooYhjUdKhI
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 121
ht-degree: 9%

---

# AM/PM

La [dimensione](overview.md) di &#39;AM/PM&#39; fornisce ad insight informazioni su se l&#39;hit si è verificato nelle ore AM o PM. L&#39;ora dell&#39;hit è basata sul fuso orario della suite di rapporti [](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito. Nessuna impostazione da modificare. La sua unica dipendenza è dal fuso orario della suite di rapporti, che determina quali ore sono AM e quali PM.

## Elementi dimensionali

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"AM"` e `"PM"`. L&#39;elemento dimensione `"AM"` si applica a tutti gli hit dalle ore 12:00 alle ore 11:59, mentre l&#39;elemento dimensione `"PM"` si applica a tutti gli hit dalle ore 12:00 alle ore 11:59.
