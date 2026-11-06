---
title: Persone con Experience Cloud ID
description: Il numero di persone in Analytics tra dispositivi con un ECID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
TQID: https://experienceleague.adobe.com/w85poHKHnDYQ0iTItr2r26q1aRpN50AsdYzg6v82Jpk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 0ba418a49e6a226540e0791f0138027566022d6f
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 15%
---
# Persone con Experience Cloud ID

&#39;Persone con Experience Cloud ID&#39; è una metrica di analisi [cross-device](../cda/overview.md) che mostra il numero di [persone](people.md) identificate da Adobe tramite il [Servizio ID visitatore](https://experienceleague.adobe.com/it/docs/id-service/using/home) o [Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/collection/identity/overview).

## Come è calcolata questa metrica

Considerando ogni [persona](people.md) (identificata o non identificata), questa [metrica](overview.md) aumenta se l&#39;hit contiene la stringa di query `mid` (basata sul cookie [`s_ecid`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics)).

Puoi creare la metrica calcolata `[People with ECID] ÷ [People]` per ottenere la percentuale di visitatori del tuo sito utilizzando il servizio ID.

Per ulteriori informazioni sull&#39;importanza di ECID e del debug della configurazione, consulta la metrica equivalente non CDA [Visitatori con ID Experience Cloud](visitors-with-ecid.md).
