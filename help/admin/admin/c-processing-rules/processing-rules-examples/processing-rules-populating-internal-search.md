---
description: Se si utilizza una variabile comune, ad esempio q, per compilare i termini di ricerca, è possibile utilizzare le regole di elaborazione per popolare l'eVar dei termini di ricerca interna con questi valori.
subtopic: Processing rules
title: Compilare termini di ricerca interni utilizzando un parametro di stringa query
feature: Strumenti di amministrazione
uuid: 05ae2b0a-8797-468c-8f59-643beac614c5
exl-id: bc7cc712-0f2a-4260-a82c-ad0e48149e73
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 21%

---

# Compilare termini di ricerca interni utilizzando un parametro di stringa query

Se si utilizza una variabile comune, ad esempio q, per compilare i termini di ricerca, è possibile utilizzare le regole di elaborazione per popolare l&#39;eVar dei termini di ricerca interna con questi valori.

I valori della stringa di query devono essere codificati in Unicode o UTF-8 per essere letti dalle regole di elaborazione.

| Set di regole | Valore |
|---|---|
| Condizione | Se è impostato il parametro q della stringa di query |
| Azione | Sovrascrivi il valore dei termini di ricerca interna al parametro di stringa query q |

Ad esempio:

![](assets/populate-internal-search-terms.png)
