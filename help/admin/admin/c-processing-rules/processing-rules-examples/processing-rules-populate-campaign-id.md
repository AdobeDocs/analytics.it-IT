---
description: È possibile compilare una variabile utilizzando un parametro di stringa di query.
seo-description: È possibile compilare una variabile utilizzando un parametro di stringa di query.
seo-title: Compilare un ID campagna da un parametro di stringa query
solution: Analytics
subtopic: Regole di elaborazione
title: Compilare un ID campagna da un parametro di stringa query
topic: Strumenti di amministrazione
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

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

