---
description: Se si utilizza una variabile comune, ad esempio q, per compilare i termini di ricerca, è possibile utilizzare le regole di elaborazione per popolare l’eVar dei termini di ricerca interna con questi valori.
subtopic: Processing rules
title: Compilare termini di ricerca interni utilizzando un parametro di stringa di query
feature: Admin Tools
role: Admin
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '116'
ht-degree: 100%

---

# Compilare termini di ricerca interni utilizzando un parametro di stringa di query

Se si utilizza una variabile comune, ad esempio q, per compilare i termini di ricerca, è possibile utilizzare le regole di elaborazione per popolare l’eVar dei termini di ricerca interna con questi valori.

I valori della stringa di query devono essere codificati in Unicode o UTF-8 per essere letti dalle regole di elaborazione.

| Set di regole | Valore |
|---|---|
| Condizione | Se è impostato il parametro q della stringa di query |
| Azione | Sovrascrivere il valore dei termini di ricerca interna al parametro di stringa di query q |

Esempio:

![](assets/populate-internal-search-terms.png)
