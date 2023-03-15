---
title: API di inserimento dati in blocco
description: Bulk Data Insertion API (BDIA) è una funzionalità di Adobe Analytics che consente di caricare i dati delle chiamate al server in batch di file invece di utilizzare librerie lato client come AppMeasurement. Le chiamate al server in questi file batch possono essere dati correnti (live) o dati storici. È un successore più scalabile dell’API di inserimento dati nelle versioni precedenti dell’API di Adobe Analytics.
solution: Analytics
feature: API
exl-id: c9d23fae-2800-42bb-8f8d-adf915cadc62
source-git-commit: b1ebf6e3548ef73217ffff1cbfb66af82e38fb8f
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 27%

---

# API di inserimento dati in blocco

L’inserimento di dati in blocco risolve diversi casi d’uso, ad esempio:

* Acquisizione di dati storici da un sistema di analisi precedente

* Un sistema di raccolta di analisi interno che rende impossibile l’utilizzo di AppMeasurement. È possibile utilizzare i processi ETL (Extract-Transform-Load) per inserire i dati in file batch e quindi utilizzare BDIA per caricarli in Adobe Analytics.

* Raccolta di dati da dispositivi con connettività solo intermittente a Internet. Questi dispositivi memorizzano le interazioni fino a quando non ricevono una connessione. Il dispositivo può quindi caricare i dati tutti contemporaneamente tramite BDIA.

API di inserimento dati e [API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)sono entrambi metodi per inviare i dati di raccolta lato server ad Adobe Analytics. Le chiamate API di inserimento dati vengono effettuate un evento alla volta. L’API di inserimento dati in blocco accetta file in formato CSV contenenti dati evento, un evento per riga. Se stai lavorando a una nuova implementazione della raccolta lato server, ti consigliamo di utilizzare l’API di inserimento dati in blocco.
