---
title: AM/PM
description: Determina se l’hit si è verificato nelle ore AM o PM.
feature: Dimensions
exl-id: 93fcdb9f-2ba3-402c-a389-b02ed8c990d2
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 9%

---

# AM/PM

La [dimensione](overview.md) di &#39;AM/PM&#39; fornisce ad insight informazioni su se l&#39;hit si è verificato nelle ore AM o PM. L&#39;ora dell&#39;hit è basata sul fuso orario della suite di rapporti [&#128279;](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md).

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito. Nessuna impostazione da modificare. La sua unica dipendenza è dal fuso orario della suite di rapporti, che determina quali ore sono AM e quali PM.

## Elementi dimensionali

Questa dimensione contiene sempre esattamente due elementi dimensionali: `"AM"` e `"PM"`. L&#39;elemento dimensione `"AM"` si applica a tutti gli hit dalle ore 12:00 alle ore 11:59, mentre l&#39;elemento dimensione `"PM"` si applica a tutti gli hit dalle ore 12:00 alle ore 11:59.
