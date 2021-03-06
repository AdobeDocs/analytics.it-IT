---
title: AM/PM
description: Determina se l'hit si è verificato nelle ore AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---

# AM/PM

La dimensione &quot;AM/PM&quot; fornisce informazioni sul caso in cui l’hit si sia verificato nelle ore AM o PM. L&#39;ora dell&#39;hit è basata sul [fuso orario della suite di rapporti](/help/admin/admin/general-acct-settings-admin.md).

## Popolare questa dimensione con i dati

Questa dimensione è preconfigurata. Non dispone di impostazioni da modificare. La sua unica dipendenza è dal fuso orario della suite di rapporti, che determina quali ore sono AM e quali sono PM.

## Elementi Dimension

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"AM"` e `"PM"`. Elemento dimensione `"AM"` si applica a tutti gli hit dalle 12:00 alle 11:59, mentre l’elemento dimensione `"PM"` si applica a tutti gli hit dalle 12:00 alle 11:59 PM.
