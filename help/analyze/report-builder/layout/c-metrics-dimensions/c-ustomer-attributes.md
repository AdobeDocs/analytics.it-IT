---
description: Gli attributi del cliente sono memorizzati in un nuovo tipo di elemento denominato VisAttr, che può essere configurato come dimensione o come metrica.
title: Attributi cliente
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
source-git-commit: fb39f906d6c08713e4dc8211c917b2942502868e
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 15%

---

# Attributi cliente

Gli attributi del cliente sono memorizzati in un nuovo tipo di elemento denominato VisAttr, che può essere configurato come dimensione o come metrica.

Per informazioni dettagliate su come caricare gli attributi del cliente, consulta la [Guida di Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=it).

* Se è configurato come metrica, VisAttr viene esposto sia come metrica che come &quot;dimensione&quot;.

  ![Schermata che mostra la metrica e la dimensione Attributi del cliente.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Supporta la stessa suddivisione di un eVar (tutto può essere suddiviso per qualsiasi cosa).
* VisAttr supporta tutte le metriche eVar.
* VisAttr come metrica supporta la &quot;bucketizzazione&quot; (come Tempo trascorso sul sito: da 0 a 30, da 31 a 60, ...)
* VisAttr è disponibile come dimensione di segmentazione.
