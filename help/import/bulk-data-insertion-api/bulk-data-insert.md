---
title: API di inserimento dati in blocco
description: API di inserimento dati in blocco (BDIA) è una funzionalità di Adobe Analytics che consente di caricare i dati delle chiamate al server in batch di file invece di utilizzare librerie lato client come AppMeasurement. Le chiamate server in questi file batch possono essere dati correnti (live) o dati storici. È un successore più scalabile dell’API di inserimento dati nelle versioni precedenti dell’API Adobe Analytics.
solution: Analytics
feature: API
source-git-commit: d8603ddd6cee2ccc930281003d9ff1befa15c95c
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 8%

---


# API di inserimento dati in blocco

L’inserimento dati in blocco risolve diversi casi d’uso, ad esempio:

* Acquisizione di dati storici da un sistema di analisi precedente

* Un sistema di raccolta interno di Analytics che impedisce l’utilizzo di AppMeasurement. È possibile utilizzare i processi Extract-Transform-Load (ETL) per inserire i dati in file batch e quindi utilizzare BDIA per caricarli in Adobe Analytics.

* Raccolta di dati da dispositivi che hanno solo connettività intermittente a Internet. Questi dispositivi memorizzano le interazioni fino a quando non ricevono una connessione. Il dispositivo può quindi caricare i dati tutti contemporaneamente tramite BDIA.

API di inserimento dati e [API di inserimento dati in blocco](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md)sono entrambi metodi per inviare dati di raccolta lato server ad Adobe Analytics. Le chiamate API di inserimento dati vengono effettuate un evento alla volta. L’API di inserimento dati in blocco accetta file in formato CSV contenenti dati evento, un evento per riga. Se stai lavorando a una nuova implementazione della raccolta lato server, ti consigliamo di utilizzare l’API di inserimento dati in blocco.