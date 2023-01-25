---
description: È possibile compilare una variabile utilizzando un parametro di stringa di query.
subtopic: Processing rules
title: Compilare un ID campagna da un parametro di stringa di query
feature: Admin Tools
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
source-git-commit: 71ff81a0ae67c6f4cc9a8df567e27223cc63f18c
workflow-type: ht
source-wordcount: '112'
ht-degree: 100%

---

# Compilare un ID campagna da un parametro di stringa di query

È possibile compilare una variabile utilizzando un parametro di stringa di query.

Nella maggior parte dei casi si utilizza un plug-in per popolare le variabili dalla stringa di query. Se un errore di battitura o altro problema simile impedisce la compilazione del valore, è possibile compilare la variabile utilizzando le regole di elaborazione.

Prima di sovrascriverlo, è sempre necessario verificare se un valore è vuoto o contiene il valore previsto.

| Set di regole | Valore |
|---|---|
| Condizione | Campaign is Not Set (Campagna è Non impostata) |
| Azione | Overwrite value of Campaign with Query String Parameter cpid (Sovrascrivi valore Campagna con Parametro stringa di query cpid) |

Esempio:

![](assets/set-campaign-conditionally.png)
