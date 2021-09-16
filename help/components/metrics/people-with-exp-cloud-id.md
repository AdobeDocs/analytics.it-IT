---
title: Persone con ID Experience Cloud
description: Il numero di persone in Cross-Device Analytics con un ID Experience Cloud.
source-git-commit: eaf0c3b751a5fbdc70ad6bef501dbf9e8400339c
workflow-type: tm+mt
source-wordcount: '130'
ht-degree: 10%

---

# Persone con ID Experience Cloud

&quot;Persone con ID Experience Cloud&quot; è una metrica [Analisi multidispositivo](../cda/overview.md) che mostra il numero di [Persone](people.md) identificate per Adobe utilizzando il servizio [ID Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Calcolo di questa metrica

Considerando ogni [Persone](people.md) (identificate o non identificate), questa metrica aumenta se l’hit contiene la stringa di query `mid` (basata sul cookie [`s_ecid`](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-analytics.html?lang=it)).

Puoi creare la metrica calcolata `[People with ECID] ÷ [People]` per ottenere la percentuale di visitatori del sito utilizzando il servizio ID.

Per ulteriori informazioni sull’importanza dell’ID Experience Cloud e sul debug della configurazione, consulta la metrica equivalente non CDA [Visitatori con ID Experience Cloud](visitors-with-ecid.md) .
