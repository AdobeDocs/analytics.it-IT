---
title: Persone con Experience Cloud ID
description: Il numero di persone in Analytics tra dispositivi che hanno un Experience Cloud ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 23%

---

# Persone con Experience Cloud ID

&#39;Persone con Experience Cloud ID&#39; è una metrica di analisi [cross-device](../cda/overview.md) che mostra il numero di [persone](people.md) identificate da Adobe con il servizio [Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Come è calcolata questa metrica

Considerando ogni [persona](people.md) (identificata o non identificata), questa [metrica](overview.md) aumenta se l&#39;hit contiene la stringa di query `mid` (basata sul cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it)).

Puoi creare la metrica calcolata `[People with ECID] ÷ [People]` per ottenere la percentuale di visitatori del tuo sito utilizzando il servizio ID.

Per ulteriori informazioni sull&#39;importanza di Experience Cloud ID e del debug della configurazione, consulta la metrica non CDA equivalente [Visitatori con Experience Cloud ID](visitors-with-ecid.md).
