---
title: Persone con ID Experience Cloud
description: Il numero di persone in Analytics tra dispositivi che hanno un ID Experience Cloud.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 13%

---

# Persone con ID Experience Cloud

&quot;Persone con ID Experience Cloud&quot; è un [Analisi cross-device](../cda/overview.md) metrica che mostra il numero di [Persone](people.md) che sono stati identificati dall&#39;Adobe utilizzando [Servizio ID Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Come è calcolata questa metrica

Considerazione di ciascuno [Persone](people.md) (identificati o non identificati), questo [metrica](overview.md) aumenta se l’hit contiene il `mid` stringa di query (basata sulla [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) cookie).

Puoi creare la metrica calcolata `[People with ECID] ÷ [People]` per ottenere la percentuale di visitatori del sito che utilizzano il servizio ID.

Vedi la metrica equivalente non CDA [Visitatori con ID Experience Cloud](visitors-with-ecid.md) per ulteriori informazioni sull’importanza dell’ID Experience Cloud e del debug della configurazione.
