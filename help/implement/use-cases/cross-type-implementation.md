---
title: Tracciare diversi tipi di implementazione
description: Utilizza diversi tipi di implementazione e monitora i visitatori in modo semplice tra loro.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 10%

---

# Tracciare diversi tipi di implementazione

L&#39;architettura di base di un&#39;implementazione Adobe Analytics è coerente per tutti i tipi di implementazione. Il processo prevede la definizione delle variabili e la loro compilazione in una richiesta di immagine inviata ai server di raccolta dati di Adobe. Questo concetto significa che puoi passare direttamente da AppMeasurement all’SDK per web e alle rispettive estensioni in Adobe Experience Platform Data Collection su diverse pagine dello stesso sito.

Adobe consiglia di mantenere la coerenza tra l’implementazione di un sito utilizzando lo stesso tipo di implementazione in tutte le pagine. Tuttavia, se alcune parti del sito hanno requisiti diversi, puoi utilizzare questa pagina per essere certo che i visitatori siano tracciati in modo coerente tra le pagine.

Se utilizzi più di un tipo di implementazione (ad esempio le richieste di immagine hardcoded e AppMeasurement), assicurati che le seguenti variabili siano impostate correttamente e si corrispondano tra loro:

| Variabile | AppMeasurement | Estensione Analytics | SDK per web | Estensione SDK per web | Richiesta immagine hardcoded |
| --- | --- | --- | --- | --- | --- |
| ID suite di rapporti | Argomento stringa all&#39;interno di [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Report suites] in [!UICONTROL Library management] sezione quando [Configurazione dell’estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Aggiungi Adobe Analytics come servizio quando [Configurazione di un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Aggiungi Adobe Analytics come servizio quando [Configurazione di un datastream](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Parte dell’URL `pathname` (dopo `/b/ss/`) |
| Tracking Server | La [`trackingServer`](../vars/config-vars/trackingserver.md) e [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) variables | [!UICONTROL Tracking Server] e [!UICONTROL SSL Tracking Server] in [!UICONTROL General] sezione quando [Configurazione dell’estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | La `edgeDomain` quando [Configurazione dell’SDK per web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) | La [!UICONTROL Edge Domain] quando [Configurazione dell’estensione](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=it) | La `hostname` dell’URL della richiesta di immagine |
| Servizio Experience Cloud ID | Implementazione [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=it) | Utilizza la [Estensione del servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Utilizza la [Estensione del servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Utilizza la [Estensione del servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Crea un [separata chiamata ai server del servizio ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) per ottenere l&#39;ID desiderato |

{style=&quot;table-layout:auto&quot;}

Se una di queste variabili non è coerente in ciascun tipo di implementazione, Adobe le considera come visitatori separati. Se il tracciamento dei visitatori non avviene sui diversi tipi di implementazione del sito, la ragione più comune è che il servizio ID non è configurato correttamente. Vedi [Metodi di implementazione](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) nella guida utente del servizio ID per ulteriori informazioni.
