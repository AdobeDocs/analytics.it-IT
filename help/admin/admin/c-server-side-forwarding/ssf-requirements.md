---
description: Devi soddisfare questi requisiti di soluzione, servizio e codice di Experience Cloud per implementare l’inoltro lato server. Questi requisiti includono anche istruzioni su come verificare la presenza di versioni di codice e su dove ottenere le ultime librerie di codice.
solution: Analytics
title: Requisiti per l'inoltro lato server
feature: Server-Side Forwarding
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 6%

---

# Requisiti per l&#39;inoltro lato server

Devi soddisfare questi requisiti di soluzione, servizio e codice di Experience Cloud per implementare l’inoltro lato server. Questi requisiti includono anche istruzioni su come verificare la presenza di versioni di codice e su dove ottenere le ultime librerie di codice.

## Requisiti della soluzione

L&#39;inoltro lato server funziona con [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) e [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) e/o [Tipi di pubblico](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html).

## Requisiti di servizio

L&#39;inoltro lato server richiede [Servizio identità](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). Il servizio Identity fornisce un ID universale che identifica i visitatori del sito in tutte le soluzioni dell’Experience Cloud. È necessario implementare il servizio ID prima che l&#39;inoltro lato server funzioni.

## Versioni del codice

L&#39;inoltro lato server richiede la versione 1.5 (o successiva) delle librerie di codice elencate di seguito. Come best practice, consigliamo di utilizzare le versioni più recenti anziché i requisiti minimi.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determinare la versione della libreria dei codici

Qualsiasi strumento che monitori le richieste HTTP effettuate da un browser può mostrarti il numero di versione per il tuo codice AppMeasurement e API Visitor. La `AppMeasurement_Module_AudienceManagement.js` non contiene o restituisce un ID versione. Gli esempi seguenti mostrano l’aspetto degli ID di versione `AppMeasurement.js` e `VisitorAPI.js` codice.

* `AppMeasurement.js`: La [Debugger Adobe](https://experienceleague.adobe.com/docs/analytics/implementation/validate/debugger.html?lang=it) restituisce la versione AppMeasurement in questo modo: `Version of Code | JS-1.5.1`. Altri strumenti possono utilizzare un’etichetta diversa, ma il valore segue sempre il pattern `JS-X.X.X`, dove `X` è un numero di versione.
* `VisitorAPI.js`: Cerca la `d_visid_ver` parametro . Ti mostrerà il servizio ID visitatore in questo modo: `d_visid_ver: 1.5.5`. Il codice API del visitatore precedente alla versione 1.5.2 non includeva un numero di versione. Stai probabilmente utilizzando una libreria di codici precedente (e devi effettuare l’aggiornamento) se i risultati del monitoraggio non restituiscono un numero di versione.
