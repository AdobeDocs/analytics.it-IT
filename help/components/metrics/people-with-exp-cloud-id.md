---
title: Persone con Experience Cloud ID
description: Il numero di persone in Analytics tra dispositivi che hanno un Experience Cloud ID.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 14%

---

# Persone con Experience Cloud ID

&#39;Persone con Experience Cloud ID&#39; è una metrica di analisi [cross-device](../cda/overview.md) che mostra il numero di [persone](people.md) identificate da Adobe con il servizio [Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Come è calcolata questa metrica

Considerando ogni [persona](people.md) (identificata o non identificata), questa [metrica](overview.md) aumenta se l&#39;hit contiene la stringa di query `mid` (basata sul cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it)).

Puoi creare la metrica calcolata `[People with ECID] ÷ [People]` per ottenere la percentuale di visitatori del tuo sito utilizzando il servizio ID.

Per ulteriori informazioni sull&#39;importanza di Experience Cloud ID e del debug della configurazione, consulta la metrica non CDA equivalente [Visitatori con Experience Cloud ID](visitors-with-ecid.md).
