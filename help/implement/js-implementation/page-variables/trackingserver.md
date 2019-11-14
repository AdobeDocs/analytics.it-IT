---
description: Le variabili di pagina popolano direttamente un report, ad esempio pageName, List Props, List Variables e così via.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variabili di pagina
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# trackingServer

La variabile viene utilizzata per l’implementazione dei cookie di prime parti per specificare il dominio in cui vengono scritti la richiesta immagine e il cookie.

<!-- 

trackingServer.xml

 -->

Utilizzato per pagine non sicure. Se *`trackingServer`* è definito, non viene inviato nulla a 2o7.net. Se non *`trackingServer`* è definito (e dc non è definito), i dati vanno a 112.2o7.net.

| Dimensioni massime | Parametro debugger | Report compilati | Valore predefinito |
|---|---|---|---|
| N/D | N/D | N/D | "" |

Un elenco dei centri dati Adobe è disponibile [qui](https://helpx.adobe.com/analytics/kb/determining-data-center.html).
