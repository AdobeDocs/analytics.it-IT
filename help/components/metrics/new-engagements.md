---
title: Nuovi engagement
description: Il numero di volte in cui è impostato un canale di primo contatto.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 6%

---

# Nuovi engagement

I &quot;Nuovi impegni&quot; [metrica](overview.md) mostra quante volte un visitatore corrisponde a un canale di marketing per la prima volta nel periodo di coinvolgimento del visitatore. Questa metrica è utile quando desideri confrontare per la prima volta qualsiasi dimensione con un visitatore che corrisponde a una regola di elaborazione del canale di marketing.

## Come è calcolata questa metrica

Durante l’elaborazione dei dati, viene eseguito ogni hit [Regole di elaborazione per il canale di marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-rules.md). Se un hit corrisponde a una regola di elaborazione del canale di marketing e il visitatore non dispone già di un canale di primo contatto, l’hit è un nuovo coinvolgimento. Se un hit non corrisponde ad alcuna regola di elaborazione del canale di marketing o se il visitatore dispone già di un canale di primo contatto, l’hit non è un nuovo coinvolgimento.

I visitatori possono avere più di un nuovo coinvolgimento se lasciano scadere il periodo di coinvolgimento dei visitatori.
