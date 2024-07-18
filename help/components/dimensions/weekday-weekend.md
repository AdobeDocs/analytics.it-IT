---
title: Giorno feriale/Fine settimana
description: Determina se l’hit si è verificato durante un giorno feriale o un weekend.
feature: Dimensions
exl-id: c3111cdc-a5f9-4244-a725-b1bb1e72fcff
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 28%

---

# Giorno feriale/Fine settimana

La [dimensione](overview.md) di &#39;Giorno feriale/Fine settimana&#39; fornisce informazioni approfondite sul caso in cui l&#39;hit si sia verificato durante un giorno feriale (lunedì-venerdì) o un weekend (sabato-domenica). L&#39;ora dell&#39;hit è basata sul fuso orario della suite di rapporti [](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md).

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"Weekday"` e `"Weekend"`. L&#39;elemento dimensione `"Weekday"` si applica a tutti gli hit dal lunedì al venerdì, mentre l&#39;elemento dimensione `"Weekend"` si applica a tutti gli hit il sabato e la domenica.
