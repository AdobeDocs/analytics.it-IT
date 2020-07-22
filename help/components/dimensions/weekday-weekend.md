---
title: Giorno feriale/Fine settimana
description: Determina se l’hit ha avuto luogo durante un giorno feriale o un weekend.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---


# Giorno feriale/Fine settimana

La dimensione &quot;Giorno feriale/Fine settimana&quot; fornisce informazioni sul caso in cui l’hit sia avvenuto durante un giorno feriale (lunedì - venerdì) o un weekend (sabato - domenica). L&#39;ora dell&#39;hit si basa sul fuso orario della suite di [rapporti](/help/admin/admin/general-acct-settings-admin.md).

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensione

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"Weekday"` e `"Weekend"`. L’elemento dimensione `"Weekday"` `"Weekend"` si applica a tutti gli hit da lunedì a venerdì, mentre l’elemento dimensione si applica a tutti gli hit da sabato e domenica.
