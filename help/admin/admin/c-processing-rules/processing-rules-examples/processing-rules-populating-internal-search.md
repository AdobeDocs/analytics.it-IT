---
description: Se utilizzate una variabile comune, come q, per compilare i termini di ricerca, potete utilizzare le regole di elaborazione per compilare la eVar dei termini di ricerca interna con questi valori.
seo-description: Se utilizzate una variabile comune, come q, per compilare i termini di ricerca, potete utilizzare le regole di elaborazione per compilare la eVar dei termini di ricerca interna con questi valori.
seo-title: Compilare termini di ricerca interni utilizzando un parametro di stringa query
solution: Analytics
subtopic: Regole di elaborazione
title: Compilare termini di ricerca interni utilizzando un parametro di stringa query
topic: Strumenti di amministrazione
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

