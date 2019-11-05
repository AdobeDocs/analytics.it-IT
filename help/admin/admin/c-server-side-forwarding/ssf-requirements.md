---
description: Devi soddisfare questi requisiti di soluzione, servizio e codice Experience Cloud per implementare l'inoltro lato server. Questi requisiti includono anche istruzioni su come verificare la disponibilità di versioni di codice e su dove reperire le ultime librerie di codici.
seo-description: Devi soddisfare questi requisiti di soluzione, servizio e codice Experience Cloud per implementare l'inoltro lato server. Questi requisiti includono anche istruzioni su come verificare la disponibilità di versioni di codice e su dove reperire le ultime librerie di codici.
seo-title: Requisiti per l'inoltro lato server
solution: Audience Manager
title: Requisiti per l'inoltro lato server
uuid: e52c9292-b2ed-4782-9594-c813e4f894e1
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Requisiti per l'inoltro lato server

Devi soddisfare questi requisiti di soluzione, servizio e codice Experience Cloud per implementare l'inoltro lato server. Questi requisiti includono anche istruzioni su come verificare la disponibilità di versioni di codice e su dove reperire le ultime librerie di codici.

## Requisiti della soluzione

L'inoltro lato server funziona con [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) , [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) e/o [Audience](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html).

## Requisiti di servizio

L'inoltro lato server richiede il servizio [](https://marketing.adobe.com/resources/help/en_US/mcvid/)identità. Il servizio Identity fornisce un ID universale che identifica i visitatori del sito in tutte le soluzioni Experience Cloud. Devi implementare il servizio ID prima che l’inoltro lato server funzioni.

## Versioni codice

L'inoltro lato server richiede la versione 1.5 (o successiva) delle librerie di codici elencate di seguito. Come procedura ottimale, consigliamo di utilizzare le versioni più recenti anziché questi requisiti minimi.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determinare la versione della libreria dei codici

Qualsiasi strumento che monitori le richieste HTTP effettuate da un browser può mostrarti il numero di versione per il codice AppMeasurement e Visitor API. L'ID `AppMeasurement_Module_AudienceManagement.js` non contiene o restituisce un ID versione. Gli esempi seguenti mostrano l’aspetto degli ID di versione per `AppMeasurement.js` e il `VisitorAPI.js` codice.

* `AppMeasurement.js`: Il [Adobe Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) restituisce la versione AppMeasurement come segue: `Version of Code | JS-1.5.1`. Altri strumenti possono utilizzare un'etichetta diversa, ma il valore segue sempre il pattern, dove `JS-X.X.X``X` è un numero di versione.
* `VisitorAPI.js`: Cercate il `d_visid_ver` parametro. Ti mostrerà il servizio Visitor ID in questo modo: `d_visid_ver: 1.5.5`. Il codice API del visitatore precedente alla versione 1.5.2 non includeva un numero di versione. Se i risultati del monitoraggio non restituiscono un numero di versione, è probabile che si stia utilizzando una libreria di codici precedente (e che sia necessario eseguire l'aggiornamento).
