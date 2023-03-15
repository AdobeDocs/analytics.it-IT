---
title: Tracciare diversi tipi di implementazione
description: Utilizza diversi tipi di implementazione e tieni traccia dei visitatori tra di loro in modo semplice.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: 90914569256cf891cb3cf693843e7cf9ede2f4ce
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 10%

---

# Tracciare diversi tipi di implementazione

L’architettura di base di un’implementazione Adobe Analytics è coerente per tutti i tipi di implementazione. Il processo comporta la definizione delle variabili e la loro compilazione in una richiesta di immagine inviata ai server di raccolta dati di Adobe. Questo concetto significa che in Raccolta dati di Adobe Experience Platform puoi passare facilmente da AppMeasurement all’SDK per web e alle rispettive estensioni nelle diverse pagine dello stesso sito.

L’Adobe consiglia di mantenere la coerenza nell’implementazione di un sito utilizzando lo stesso tipo di implementazione in tutte le pagine. Tuttavia, se alcune parti del sito presentano requisiti diversi, puoi utilizzare questa pagina per assicurarti che i visitatori vengano tracciati in modo coerente tra le pagine.

Se utilizzi più di un tipo di implementazione (ad esempio richieste di immagini AppMeasurement e hardcoded), assicurati che le seguenti variabili siano impostate correttamente e si corrispondano tra loro:

| Variabile | AppMeasurement | Estensione Analytics | SDK per web | Estensione Web SDK | Richiesta immagine hardcoded |
| --- | --- | --- | --- | --- | --- |
| ID suite di rapporti | Argomento stringa all&#39;interno di [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Report suites] sotto [!UICONTROL Library management] sezione quando [Configurazione dell’estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Aggiungere Adobe Analytics as a service quando [Configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Aggiungere Adobe Analytics as a service quando [Configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html) | Parte dell’URL `pathname` (dopo `/b/ss/`) |
| Tracking Server | Il [`trackingServer`](../vars/config-vars/trackingserver.md) e [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) Variabili | [!UICONTROL Tracking Server] e [!UICONTROL SSL Tracking Server] sotto [!UICONTROL General] sezione quando [Configurazione dell’estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html) | Il `edgeDomain` proprietà quando [Configurazione del Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) | Il [!UICONTROL Edge Domain] quando [Configurazione dell’estensione](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=it) | Il `hostname` dell’URL della richiesta di immagine |
| Servizio Experience Cloud ID | Implementazione [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=it) | Utilizza il [Estensione del servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Utilizza il [Estensione del servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Utilizza il [Estensione del servizio Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html) | Crea un [chiamata separata ai server del servizio ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) per ottenere l’ID desiderato |

{style="table-layout:auto"}

Se una di queste variabili non è coerente in ciascun tipo di implementazione, Adobe le considera come visitatori separati. Se i visitatori non vengono tracciati facilmente nei diversi tipi di implementazione sul sito, il motivo più comune è che il servizio ID non è configurato correttamente. Consulta [Metodi di implementazione](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) per ulteriori informazioni, consulta la guida utente del servizio ID.
