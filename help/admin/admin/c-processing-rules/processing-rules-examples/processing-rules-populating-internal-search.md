---
description: Se utilizzate una variabile comune, come q, per compilare i termini di ricerca, potete utilizzare le regole di elaborazione per compilare la eVar dei termini di ricerca interna con questi valori.
subtopic: Processing rules
title: Compilare termini di ricerca interni utilizzando un parametro di stringa query
topic: Admin tools
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Compilare termini di ricerca interni utilizzando un parametro di stringa query

Se utilizzate una variabile comune, come q, per compilare i termini di ricerca, potete utilizzare le regole di elaborazione per compilare la eVar dei termini di ricerca interna con questi valori.

I valori delle stringhe di query devono essere codificati in Unicode o UTF-8 per essere letti dalle regole di elaborazione.

| Set di regole | Valore |
|---|---|
| Condizione | Se il parametro q della stringa query è impostato |
| Azione | Sovrascrivi il valore dei termini di ricerca interni al parametro stringa query q |

Ad esempio:

![](assets/populate-internal-search-terms.png)

