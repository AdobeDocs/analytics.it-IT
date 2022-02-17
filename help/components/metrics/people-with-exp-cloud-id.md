---
title: Persone con ID Experience Cloud
description: Il numero di persone in Cross-Device Analytics con un ID Experience Cloud.
feature: Metrics
exl-id: 072e7d2b-3a08-49c6-a892-4cea2cc10159
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 10%

---

# Persone con ID Experience Cloud

&quot;Persone con ID Experience Cloud&quot; è un [Analisi multidispositivo](../cda/overview.md) che mostra il numero di [Persone](people.md) che sono stati identificati per Adobe utilizzando [Servizio Experience Cloud ID](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Calcolo di questa metrica

Considerando ciascuno [Persone](people.md) (identificato o non identificato), questa metrica aumenta se l&#39;hit contiene il `mid` stringa di interrogazione (basata su [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it) cookie).

Puoi creare la metrica calcolata `[People with ECID] ÷ [People]` per ottenere la percentuale di visitatori del sito utilizzando il servizio ID.

Visualizzare la metrica equivalente non CDA [Visitatori con ID Experience Cloud](visitors-with-ecid.md) per ulteriori informazioni sull&#39;importanza di Experience Cloud ID e sul debug della configurazione.
