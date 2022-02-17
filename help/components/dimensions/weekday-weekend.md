---
title: Giorno feriale/Fine settimana
description: Determina se l'hit si è verificato durante un giorno feriale o un weekend.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 3%

---

# Giorno feriale/Fine settimana

La dimensione &quot;Giorno feriale/fine settimana&quot; fornisce informazioni sul fatto che l’hit sia stato rilevato durante un giorno feriale (lunedì - venerdì) o un weekend (sabato - domenica). L&#39;ora dell&#39;hit è basata sul [fuso orario della suite di rapporti](/help/admin/admin/general-acct-settings-admin.md).

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"Weekday"` e `"Weekend"`. Elemento dimensione `"Weekday"` si applica a tutti gli hit dal lunedì al venerdì, mentre l’elemento dimensione `"Weekend"` si applica a tutti gli hit di sabato e domenica.
