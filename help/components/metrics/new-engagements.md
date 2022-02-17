---
title: Nuovi engagement
description: Numero di volte in cui viene impostato un canale di primo contatto.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 2%

---

# Nuovi engagement

La metrica &quot;Nuovi impegni&quot; mostra il numero di volte in cui un visitatore corrisponde a un canale di marketing per la prima volta nel periodo di coinvolgimento di quel visitatore. Questa metrica è utile quando desideri confrontare una dimensione con un visitatore che corrisponde per la prima volta a una regola di elaborazione del canale di marketing.

## Calcolo di questa metrica

Durante l’elaborazione dei dati, ogni hit viene eseguito attraverso [Regole di elaborazione per i canali di marketing](../c-marketing-channels/c-rules.md). Se un hit corrisponde a una regola di elaborazione di un canale di marketing e il visitatore non dispone già di un canale di primo contatto, l’hit è un nuovo coinvolgimento. Se un hit non corrisponde ad alcuna regola di elaborazione del canale di marketing o se il visitatore ha già un canale di primo contatto, l’hit non è un nuovo coinvolgimento.

I visitatori possono avere più di un nuovo coinvolgimento se lasciano scadere il periodo di coinvolgimento del visitatore.
