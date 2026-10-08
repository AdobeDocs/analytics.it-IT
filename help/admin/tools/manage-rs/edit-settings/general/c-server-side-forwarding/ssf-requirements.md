---
description: Per implementare l’inoltro lato server, è necessario soddisfare i seguenti requisiti relativi a soluzioni, servizi e codice di CX Enterprise. Troverai anche istruzioni su come verificare le versioni del codice e dove ottenere le librerie di codice più recenti.
solution: Analytics
title: Requisiti per l’inoltro lato server
feature: Report Suite Settings
exl-id: af0cf85a-381e-46d2-a4fd-9a5b073c8a8d
role: Admin
TQID: 'https://experienceleague.adobe.com/1GCflxlY4IpT-pPTr93FuOmxkJLC4baJe3Z2SGjj1So'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
    internal-label: Admin Tools
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
subfeature_v2:
  - id: c354699e-6555-4397-8706-1a9a89984069
    internal-label: Server side forwarding
  - id: fab61dd8-112a-4e5e-ad5f-fb0240b7a60b
    internal-label: Report Suite settings
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 74%
---
# Requisiti per l’inoltro lato server

Per implementare l’inoltro lato server, è necessario soddisfare i seguenti requisiti relativi a soluzioni, servizi e codice di CX Enterprise. Troverai anche istruzioni su come verificare le versioni del codice e dove ottenere le librerie di codice più recenti.

## Soluzioni richieste

L’inoltro lato server funziona con [Analytics](https://www.adobe.com/it/data-analytics-cloud/analytics.html) e [Audience Manager](https://www.adobe.com/it/data-analytics-cloud/audience-manager.html) e/o [Audiences](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=it).

## Servizi richiesti

L’inoltro lato server richiede [Identity Service](https://experienceleague.adobe.com/it/docs/id-service/using/home). Identity Service fornisce un ID universale che identifica i visitatori in tutte le soluzioni di CX Enterprise. È necessario implementare il servizio ID prima di attivare l’inoltro lato server.

## Versioni del codice

L’inoltro lato server richiede la versione 1.5 (o successiva) delle librerie di codice elencate di seguito. Nonostante tali requisiti minimi, come best practice si consiglia comunque di utilizzare le versioni più recenti.

* `AppMeasurement.js`
* `AppMeasurement_Module_AudienceManagement.js`
* `VistorAPI.js`

### Determinare la versione della libreria di codice

Gli strumenti che monitorano le richieste HTTP effettuate da un browser consentono di trovare il numero di versione del codice di AppMeasurement e di Visitor API. Il file `AppMeasurement_Module_AudienceManagement.js` non contiene o restituisce un ID versione. Gli esempi seguenti mostrano l’aspetto degli ID versione per il codice di `AppMeasurement.js` e `VisitorAPI.js`.

* `AppMeasurement.js`: la versione viene visualizzata nell&#39;URL della richiesta dopo il tipo di risposta, ad esempio `/b/ss/examplersid/1/JS-X.X.X/s234234238479`. [Strumenti di debug](/help/implement/validate/debugging-tools.md) per le richieste di decodifica possono utilizzare un&#39;etichetta diversa, ma il valore segue sempre il pattern `JS-X.X.X`, dove `X` è un numero di versione.
* `VisitorAPI.js`: cerca il parametro `d_visid_ver`. Ti mostrerà il servizio Visitor ID in questo modo: `d_visid_ver: 1.5.5`. Il codice di Visitor API precedente alla versione 1.5.2 non includeva un numero di versione. Se i risultati del monitoraggio non restituiscono alcun numero di versione, probabilmente stai utilizzando una libreria precedente (che devi quindi aggiornare).
