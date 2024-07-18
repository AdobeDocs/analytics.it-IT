---
title: API di inserimento dati in blocco
description: Bulk Data Insertion API (BDIA) è una funzionalità di Adobe Analytics che consente di caricare i dati delle chiamate al server in batch di file invece di utilizzare librerie lato client come AppMeasurement.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '186'
ht-degree: 28%

---

# API di inserimento dati in blocco

L’inserimento di dati in blocco risolve diversi casi d’uso, ad esempio:

* Acquisizione di dati storici da un sistema di analisi precedente

* Un sistema di raccolta di analisi interno che rende impossibile l’utilizzo di AppMeasurement. È possibile utilizzare i processi ETL (Extract-Transform-Load) per inserire i dati in file batch e quindi utilizzare BDIA per caricarli in Adobe Analytics.

* Raccolta di dati da dispositivi con connettività solo intermittente a Internet. Questi dispositivi memorizzano le interazioni fino a quando non ricevono una connessione. Il dispositivo può quindi caricare i dati tutti contemporaneamente tramite BDIA.

L&#39;API di inserimento dati e l&#39;[API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)sono entrambi metodi per inviare i dati della raccolta lato server ad Adobe Analytics. Le chiamate API di inserimento dati vengono effettuate un evento alla volta. L’API di inserimento dati in blocco accetta file in formato CSV contenenti dati evento, un evento per riga. Se stai lavorando a una nuova implementazione della raccolta lato server, ti consigliamo di utilizzare l’API di inserimento dati in blocco.
