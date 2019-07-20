---
description: Se utilizzi una variabile comune, ad esempio d, per compilare i termini di ricerca, puoi utilizzare le regole di elaborazione per compilare i termini di ricerca interni con questi valori.
seo-description: Se utilizzi una variabile comune, ad esempio d, per compilare i termini di ricerca, puoi utilizzare le regole di elaborazione per compilare i termini di ricerca interni con questi valori.
seo-title: Compilazione di termini di ricerca interni utilizzando un parametro di stringa query
solution: Analytics
subtopic: Regole di elaborazione
title: Compilazione di termini di ricerca interni utilizzando un parametro di stringa query
topic: Strumenti di amministrazione
uuid: 05 ae 2 b 0 a -8797-468 c -8 f 59-643 beac 614 c 5
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Compilazione di termini di ricerca interni utilizzando un parametro di stringa query

Se utilizzi una variabile comune, ad esempio d, per compilare i termini di ricerca, puoi utilizzare le regole di elaborazione per compilare i termini di ricerca interni con questi valori.

I valori delle stringhe di query devono essere codificati in Unicode o UTF -8 per essere letti dalle regole di elaborazione.

| Set di regole | Valore |
|---|---|
| Condizione | Se il parametro di stringa di query q è impostato |
| Azione | Valore sovrascritto di termini di ricerca interni in parametro stringa query q |

Ad esempio:

![](assets/populate-internal-search-terms.png)

