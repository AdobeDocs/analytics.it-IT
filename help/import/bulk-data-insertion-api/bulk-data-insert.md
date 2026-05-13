---
title: API di inserimento dati in blocco
description: Bulk Data Insertion API (BDIA) è una funzionalità di Adobe Analytics che consente di caricare i dati delle chiamate al server in batch di file invece di utilizzare librerie lato client come AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
TQID: https://experienceleague.adobe.com/TVa-LtTWKi6lQKGQKhH2bu5UcKsSJ2-KVqlfU5tQROQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 201
ht-degree: 32%

---

# API di inserimento dati in blocco

L’inserimento di dati in blocco risolve diversi casi d’uso, ad esempio:

* Acquisizione di dati storici da un sistema di analisi precedente

* Un sistema di raccolta di analisi interno che rende impossibile l’utilizzo di AppMeasurement. È possibile utilizzare i processi ETL (Extract-Transform-Load) per inserire i dati in file batch e quindi utilizzare BDIA per caricarli in Adobe Analytics.

* Raccolta di dati da dispositivi con connettività solo intermittente a Internet. Questi dispositivi memorizzano le interazioni fino a quando non ricevono una connessione. Il dispositivo può quindi caricare i dati tutti contemporaneamente tramite BDIA.

L&#39;API di inserimento dati e l&#39;[API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)sono entrambi metodi per inviare i dati della raccolta lato server ad Adobe Analytics. Le chiamate API di inserimento dati vengono effettuate un evento alla volta. L’API di inserimento dati in blocco accetta file in formato CSV contenenti dati evento, un evento per riga. Se stai lavorando a una nuova implementazione della raccolta lato server, ti consigliamo di utilizzare l’API di inserimento dati in blocco.
