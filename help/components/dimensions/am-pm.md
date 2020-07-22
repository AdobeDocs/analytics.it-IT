---
title: AM/PM
description: Determina se l’hit ha avuto luogo durante le ore AM o PM.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 3%

---


# AM/PM

La dimensione &#39;AM/PM&#39; fornisce informazioni sul caso in cui l&#39;hit sia avvenuto durante le ore AM o PM. L&#39;ora dell&#39;hit si basa sul fuso orario della suite di [rapporti](/help/admin/admin/general-acct-settings-admin.md).

## Compilare questa dimensione con i dati

Questa dimensione funziona fuori dalla scatola. Non ha impostazioni da modificare. La sua unica dipendenza è dal fuso orario della suite di rapporti, che determina quali ore sono AM e quali sono PM.

## Elementi dimensione

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"AM"` e `"PM"`. L’elemento della dimensione `"AM"` si applica a tutti gli hit dalle 12:00 AM alle 11:59 AM, mentre l’elemento della dimensione `"PM"` si applica a tutti gli hit dalle 12:00 PM alle 11:59 PM.
