---
title: Persone con ID Experience Cloud
description: Il numero di persone in Analytics tra dispositivi che hanno un ID Experience Cloud.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 10%

---

# Persone con ID Experience Cloud

&quot;Persone con ID Experience Cloud&quot; è un [Analisi cross-device](../cda/overview.md) metrica che mostra il numero di [Persone](people.md) che sono stati identificati dall&#39;Adobe utilizzando [Servizio ID Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Modalità di calcolo di questa metrica

Considerazione di ciascuno [Persone](people.md) (identificato o non identificato), questa metrica aumenta se l’hit contiene il `mid` stringa di query (basata sulla [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) cookie).

Puoi creare la metrica calcolata `[People with ECID] ÷ [People]` per ottenere la percentuale di visitatori del sito che utilizzano il servizio ID.

Vedi la metrica equivalente non CDA [Visitatori con ID Experience Cloud](visitors-with-ecid.md) per ulteriori informazioni sull’importanza dell’ID Experience Cloud e del debug della configurazione.
