---
description: Gli attributi del cliente sono memorizzati in un nuovo tipo di elemento denominato VisAttr, che può essere configurato come dimensione o come metrica.
title: Attributi cliente
uuid: a8340b83-d7ba-46fe-bb20-b546cdf375b8
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 21%

---

# Attributi cliente

Gli attributi del cliente sono memorizzati in un nuovo tipo di elemento denominato VisAttr, che può essere configurato come dimensione o come metrica.

Per informazioni dettagliate su come caricare gli attributi del cliente, consulta la [Guida di Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=it).

* Se è configurato come metrica, VisAttr viene esposto sia come &quot;dimensione&quot; che come metrica.

   ![](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Supporta lo stesso raggruppamento di un eVar (tutto può essere suddiviso per qualsiasi cosa).
* VisAttr supporta tutte le metriche eVar.
* VisAttr come metrica supporta la &quot;bucketization&quot; (come Tempo trascorso sul sito: da 0 a 30, da 31 a 60, ...)
* VisAttr è disponibile come dimensione di segmentazione.
