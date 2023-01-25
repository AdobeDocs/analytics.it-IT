---
description: Per implementare l’inoltro lato server, è necessario soddisfare i seguenti requisiti relativi a soluzioni, servizi e codice di Experience Cloud. Troverai anche istruzioni su come verificare le versioni del codice e dove ottenere le librerie di codice più recenti.
solution: Analytics
title: Requisiti per l’inoltro lato server
feature: Server-Side Forwarding
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: ht
source-wordcount: '315'
ht-degree: 100%

---

# Requisiti per l’inoltro lato server

Per implementare l’inoltro lato server, è necessario soddisfare i seguenti requisiti relativi a soluzioni, servizi e codice di Experience Cloud. Troverai anche istruzioni su come verificare le versioni del codice e dove ottenere le librerie di codice più recenti.

## Soluzioni richieste

L’inoltro lato server funziona con [Analytics](https://www.adobe.com/it/data-analytics-cloud/analytics.html) e [Audience Manager](https://www.adobe.com/it/data-analytics-cloud/audience-manager.html) e/o [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=it).

## Servizi richiesti

L’inoltro lato server richiede [Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it). Identity Service fornisce un ID universale che identifica i visitatori in tutte le soluzioni di Experience Cloud. È necessario implementare il servizio ID prima di attivare l’inoltro lato server.

## Versioni del codice

L’inoltro lato server richiede la versione 1.5 (o successiva) delle librerie di codice elencate di seguito. Nonostante tali requisiti minimi, come best practice si consiglia comunque di utilizzare le versioni più recenti.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determinare la versione della libreria di codice

Gli strumenti che monitorano le richieste HTTP effettuate da un browser consentono di trovare il numero di versione del codice di AppMeasurement e di Visitor API. Il file `AppMeasurement_Module_AudienceManagement.js` non contiene o restituisce un ID versione. Gli esempi seguenti mostrano l’aspetto degli ID versione per il codice di `AppMeasurement.js` e `VisitorAPI.js`.

* `AppMeasurement.js`: [Adobe Debugger](https://experienceleague.adobe.com/docs/analytics/implementation/validate/debugger.html?lang=it) restituisce la versione AppMeasurement in questo modo: `Version of Code | JS-1.5.1`. Altri strumenti possono utilizzare un’etichetta diversa, ma il valore segue sempre il criterio `JS-X.X.X`, dove `X` è un numero di versione.
* `VisitorAPI.js`: cerca il parametro `d_visid_ver`. Ti mostrerà il servizio Visitor ID in questo modo: `d_visid_ver: 1.5.5`. Il codice di Visitor API precedente alla versione 1.5.2 non includeva un numero di versione. Se i risultati del monitoraggio non restituiscono alcun numero di versione, probabilmente stai utilizzando una libreria precedente (che devi quindi aggiornare).
