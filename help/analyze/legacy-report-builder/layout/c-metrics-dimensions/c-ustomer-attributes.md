---
description: Gli attributi del cliente sono memorizzati in un nuovo tipo di elemento denominato VisAttr, che può essere configurato come dimensione o come metrica.
title: Attributi cliente
feature: Report Builder
role: User, Admin
exl-id: b5855ce0-6d17-4690-a2c2-366b66ab8e83
TQID: https://experienceleague.adobe.com/J-KoYBPg-bECW1utOk2L0YLtBWd9-jHT6gwAEm54fs4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 135
ht-degree: 20%

---

# Attributi cliente

{{legacy-arb}}

Gli attributi del cliente sono memorizzati in un nuovo tipo di elemento denominato VisAttr, che può essere configurato come dimensione o come metrica.

Per informazioni dettagliate su come caricare gli attributi del cliente, consulta la [Guida di Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/attributes.html?lang=it).

* Se è configurato come metrica, VisAttr viene esposto sia come metrica che come &quot;dimensione&quot;.

  ![Schermata che mostra la metrica e la dimensione Attributi del cliente.](assets/ca_metrics.png) ![](assets/ca_dimension.png)

* Supporta lo stesso raggruppamento di un’eVar (tutto può essere suddiviso per qualsiasi cosa).
* VisAttr supporta tutte le metriche di eVar.
* VisAttr come metrica supporta la &quot;bucketizzazione&quot; (come Tempo trascorso sul sito: da 0 a 30, da 31 a 60, ...)
* VisAttr è disponibile come dimensione di segmentazione.
