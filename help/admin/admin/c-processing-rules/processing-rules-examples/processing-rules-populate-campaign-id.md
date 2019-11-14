---
description: È possibile compilare una variabile utilizzando un parametro di stringa di query.
solution: Analytics
subtopic: Processing rules
title: Compilare un ID campagna da un parametro di stringa query
topic: Admin tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Compilare un ID campagna da un parametro di stringa query

È possibile compilare una variabile utilizzando un parametro di stringa di query.

Nella maggior parte dei casi si utilizza un plug-in per compilare le variabili dalla stringa di query. Se un errore ortografico o simile impedisce che il valore venga popolato, è possibile compilare la variabile utilizzando le regole di elaborazione.

Prima di sovrascrivere un valore, è sempre necessario verificare se è vuoto o contiene il valore previsto.

| Set di regole | Valore |
|---|---|
| Condizione | Campagna non impostata |
| Azione | Sovrascrivi valore di Campaign to Query String Parameter cpid |

Ad esempio:

![](assets/set-campaign-conditionally.png)

