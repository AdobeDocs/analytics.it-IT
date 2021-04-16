---
description: È possibile compilare una variabile utilizzando un parametro di stringa query.
subtopic: Processing rules
title: Compilare un ID campagna da un parametro di stringa query
feature: Strumenti di amministrazione
uuid: 2bc61f9f-d8d2-41b7-bd39-4a9df30ff013
exl-id: 526d2727-b7f6-4b41-be86-e5f5bc5e6c2b
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '114'
ht-degree: 21%

---

# Compilare un ID campagna da un parametro di stringa query

È possibile compilare una variabile utilizzando un parametro di stringa query.

Nella maggior parte dei casi si utilizza un plug-in per popolare le variabili dalla stringa di query. Se un errore di battitura o un problema simile impedisce la compilazione del valore, è possibile compilare la variabile utilizzando le regole di elaborazione.

Prima di sovrascriverlo, è sempre necessario verificare se un valore è vuoto o contiene il valore previsto.

| Set di regole | Valore |
|---|---|
| Condizione | Campagna non impostata |
| Azione | Sovrascrivi il valore di Campaign al parametro di stringa query cpid |

Ad esempio:

![](assets/set-campaign-conditionally.png)
