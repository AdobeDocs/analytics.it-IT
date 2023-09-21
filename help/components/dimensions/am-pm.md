---
title: AM/PM
description: Determina se l’hit si è verificato nelle ore AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 5%

---

# AM/PM

&#39;AM/PM&#39; [dimensione](overview.md) fornisce indicazioni su se l’hit è accaduto durante le ore AM o PM. L’ora dell’hit si basa sul [fuso orario della suite di rapporti](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito. Nessuna impostazione da modificare. La sua unica dipendenza è dal fuso orario della suite di rapporti, che determina quali ore sono AM e quali PM.

## Elementi dimensionali

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"AM"` e `"PM"`. Elemento dimensione `"AM"` si applica a tutti gli hit dalle 00:00 alle 00:59, mentre l’elemento dimensionale `"PM"` si applica a tutti gli hit dalle 12:00 alle 23:59.
