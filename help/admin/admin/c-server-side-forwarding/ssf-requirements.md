---
description: Devi soddisfare questi requisiti di soluzione, servizio e codice Experience Cloud per implementare l'inoltro lato server. Questi requisiti includono anche istruzioni su come controllare le versioni dei codici e dove ottenere le ultime librerie di codici.
seo-description: Devi soddisfare questi requisiti di soluzione, servizio e codice Experience Cloud per implementare l'inoltro lato server. Questi requisiti includono anche istruzioni su come controllare le versioni dei codici e dove ottenere le ultime librerie di codici.
seo-title: Requisiti per l'inoltro lato server
solution: Audience Manager
title: Requisiti per l'inoltro lato server
uuid: e 52 c 9292-b 2 ed -4782-9594-c 813 e 4 f 894 e 1
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Requisiti per l'inoltro lato server

Devi soddisfare questi requisiti di soluzione, servizio e codice Experience Cloud per implementare l'inoltro lato server. Questi requisiti includono anche istruzioni su come controllare le versioni dei codici e dove ottenere le ultime librerie di codici.

## Requisiti della soluzione

Server-side forwarding works with [Analytics](https://www.adobe.com/data-analytics-cloud/analytics.html) and [Audience Manager](https://www.adobe.com/data-analytics-cloud/audience-manager.html) and/or [Audiences](https://marketing.adobe.com/resources/help/en_US/mcloud/audience_library.html).

## Requisiti del servizio

Server-side forwarding requires the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/). Il servizio identità fornisce un ID universale che identifica i visitatori del sito in tutte le soluzioni Experience Cloud. Prima dell'inoltro lato server è necessario implementare il servizio ID.

## Versioni codice

L'inoltro lato server richiede la versione 1.5 (o più recente) delle librerie di codice elencate di seguito. Come procedura ottimale, consigliamo di utilizzare le versioni più recenti, anziché i requisiti minimi.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determinare la versione della libreria Codice

Qualsiasi strumento che monitora le richieste HTTP effettuate da un browser può mostrare il numero di versione per appmeasurement e il codice API del visitatore. The `AppMeasurement_Module_AudienceManagement.js` does not contain or return a version ID. The following examples show you what the version IDs for look like for `AppMeasurement.js` and `VisitorAPI.js` code.

* `AppMeasurement.js`: [Adobe Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) restituisce la versione appmeasurement di questa versione: `Version of Code | JS-1.5.1`. Other tools may use a different label, but the value always follows the pattern `JS-X.X.X`, where `X` is a version number.
* `VisitorAPI.js`: Cercare il `d_visid_ver` parametro. It will show you the Visitor ID service like this: `d_visid_ver: 1.5.5`. Il codice API del visitatore precedente alla versione 1.5.2 non includeva un numero di versione. Probabilmente utilizzi una libreria di codici meno recente (e devi eseguire l'aggiornamento) se i risultati del monitoraggio non restituiscono un numero di versione.