---
title: Tracciare diversi tipi di implementazione
description: Utilizza diversi tipi di implementazione e tieni traccia dei visitatori tra di loro in modo semplice.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 10%

---

# Tracciare diversi tipi di implementazione

L’architettura di base di un’implementazione Adobe Analytics è coerente per tutti i tipi di implementazione. Il processo comporta la definizione delle variabili e la loro compilazione in una richiesta di immagine inviata ai server di raccolta dati di Adobe. Questo concetto significa che in Raccolta dati di Adobe Experience Platform puoi passare facilmente da AppMeasurement a Web SDK e dalle rispettive estensioni nelle diverse pagine dello stesso sito.

Adobe consiglia di mantenere la coerenza nell’implementazione di un sito utilizzando lo stesso tipo di implementazione in tutte le pagine. Tuttavia, se alcune parti del sito hanno requisiti diversi, puoi utilizzare questa pagina per assicurarti che i visitatori vengano tracciati in modo coerente tra le pagine.

Se utilizzi più di un tipo di implementazione (ad esempio richieste di immagini AppMeasurement e codificate), assicurati che le seguenti variabili siano impostate correttamente e si corrispondano tra loro:

| Variabile | AppMeasurement | Estensione Analytics | Web SDK | Estensione Web SDK | Richiesta immagine hardcoded |
| --- | --- | --- | --- | --- | --- |
| ID suite di rapporti | Argomento stringa in [`s_gi`](../vars/functions/s-gi.md) | [!UICONTROL Report suites] nella sezione [!UICONTROL Library management] quando [Configurazione dell&#39;estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=it) | Aggiungi Adobe Analytics as a service durante [la configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=it) | Aggiungi Adobe Analytics as a service durante [la configurazione di uno stream di dati](https://experienceleague.adobe.com/docs/experience-platform/edge/datastreams/configure.html?lang=it) | Parte dell&#39;URL `pathname` (dopo `/b/ss/`) |
| Tracking Server | Variabili [`trackingServer`](../vars/config-vars/trackingserver.md) e [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | [!UICONTROL Tracking Server] e [!UICONTROL SSL Tracking Server] nella sezione [!UICONTROL General] durante la [configurazione dell&#39;estensione](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=it) | La proprietà `edgeDomain` durante la [configurazione del Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) | [!UICONTROL Edge Domain] durante [la configurazione dell&#39;estensione](https://experienceleague.adobe.com/docs/experience-platform/edge/extension/web-sdk-extension-configuration.html?lang=it) | `hostname` dell&#39;URL della richiesta di immagine |
| Servizio Experience Cloud ID | Implementa [`VisitorAPI.js`](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=it) | Utilizza l&#39;estensione del servizio [Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=it) | Utilizza l&#39;estensione del servizio [Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=it) | Utilizza l&#39;estensione del servizio [Adobe Experience Cloud ID](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/id-service/overview.html?lang=it) | Effettua una [chiamata separata ai server del servizio ID](https://experienceleague.adobe.com/docs/id-service/using/implementation/direct-integration.html) per ottenere l&#39;ID desiderato |

{style="table-layout:auto"}

Se una di queste variabili non è coerente in ciascun tipo di implementazione, Adobe le considera come visitatori separati. Se i visitatori non vengono tracciati facilmente nei diversi tipi di implementazione sul sito, il motivo più comune è che il servizio ID non è configurato correttamente. Per ulteriori informazioni, consulta [Metodi di implementazione](https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-methods.html) nella guida utente del servizio ID.
