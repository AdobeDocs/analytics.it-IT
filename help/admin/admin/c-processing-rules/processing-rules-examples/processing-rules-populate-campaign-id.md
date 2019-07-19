---
description: È possibile compilare una variabile utilizzando un parametro di stringa query.
seo-description: È possibile compilare una variabile utilizzando un parametro di stringa query.
seo-title: Compilazione di un ID campagna da un parametro di stringa query
solution: Analytics
subtopic: Regole di elaborazione
title: Compilazione di un ID campagna da un parametro di stringa query
topic: Strumenti di amministrazione
uuid: 2 bc 61 f 9 f-d 8 d 2-41 b 7-bd 39-4 a 9 df 30 ff 013
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Compilazione di un ID campagna da un parametro di stringa query

È possibile compilare una variabile utilizzando un parametro di stringa query.

Nella maggior parte dei casi, si utilizza un plug-in per compilare variabili dalla stringa query. Se un problema ortografico o simile impedisce la compilazione del valore, potete comporre la variabile utilizzando le regole di elaborazione.

Verificate sempre se un valore è vuoto o se contiene il valore previsto prima di sovrascriverlo.

| Set di regole | Valore |
|---|---|
| Condizione | Campagna non impostata |
| Azione | Valore sovrascrittura da Campaign a Parametro stringa query cpid |

Ad esempio:

![](assets/set-campaign-conditionally.png)

