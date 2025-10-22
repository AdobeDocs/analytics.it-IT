---
title: Tracciare diversi tipi di implementazione
description: Utilizza diversi tipi di implementazione e tieni traccia dei visitatori tra di loro in modo semplice.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
source-git-commit: 98e9dc4932bd23d3e0b632705945f56c243750c5
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 7%

---

# Tracciare diversi tipi di implementazione

L’architettura di base di un’implementazione Adobe Analytics è coerente per tutti i tipi di implementazione. Il processo comporta la definizione delle variabili e la loro compilazione in una richiesta di immagine inviata ai server di raccolta dati di Adobe. Questo concetto significa che in Raccolta dati di Adobe Experience Platform puoi passare facilmente da AppMeasurement a Web SDK e dalle rispettive estensioni nelle diverse pagine dello stesso sito.

Adobe consiglia di mantenere la coerenza nell’implementazione di un sito utilizzando lo stesso tipo di implementazione in tutte le pagine. Tuttavia, se alcune parti del sito hanno requisiti diversi, puoi utilizzare questa pagina per assicurarti che i visitatori vengano tracciati in modo coerente tra le pagine.

Se utilizzi più di un tipo di implementazione (ad esempio richieste di immagini AppMeasurement e hardcoded), assicurati che le seguenti variabili siano impostate correttamente e si corrispondano tra loro.

>[!NOTE]
>
>Tutti i tipi di implementazione devono utilizzare lo stesso tipo di identificazione del visitatore (ID Analytics legacy o servizio ID visitatore). Adobe consiglia di utilizzare il servizio ID visitatore in tutte le implementazioni, ove possibile.

| Variabile | Estensione tag Web SDK | Web SDK (Alloy) | Estensione Analytics | AppMeasurement | Richiesta immagine hardcoded |
|---|---|---|---|---|---|
| ID suite di rapporti | Aggiungi Adobe Analytics as a service durante [la configurazione di uno stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure) | Aggiungi Adobe Analytics as a service durante [la configurazione di uno stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure) | [!UICONTROL Report suites] nella sezione [!UICONTROL Library management] quando [Configurazione dell&#39;estensione](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) | Argomento stringa in [`s_gi`](../vars/functions/s-gi.md) | Parte dell&#39;URL `pathname` (dopo `/b/ss/`) |
| Servizio Experience Cloud ID | [Inclusione nativa](web-sdk-extension.md) | [Inclusione nativa](alloy.md) | Utilizza l&#39;estensione del servizio [Experience Cloud ID](analytics-extension.md) | Implementare [`VisitorAPI.js`](appmeasurement.md) | Effettua una [chiamata separata al servizio ID](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration) per ottenere l&#39;ID desiderato e includere `mid` nella stringa di query |
| Dominio Edge | Il campo [!UICONTROL Edge Domain] durante la [configurazione dell&#39;estensione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | La proprietà `edgeDomain` durante la [configurazione del Web SDK](https://experienceleague.adobe.com/en/docs/experience-platform/web-sdk/commands/configure/overview) | [!UICONTROL SSL Tracking Server] nella sezione [!UICONTROL General] quando [Configurazione dell&#39;estensione](https://experienceleague.adobe.com/en/docs/experience-platform/tags/extensions/client/analytics/overview) | La variabile [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | `hostname` dell&#39;URL della richiesta di immagine |

Se una di queste variabili non è coerente in ciascun tipo di implementazione, Adobe probabilmente le considera come visitatori separati. Se i visitatori non vengono tracciati facilmente nei diversi tipi di implementazione sul sito, il motivo più comune è che il servizio ID non è configurato correttamente. Assicurarsi che ogni tipo di implementazione ottenga correttamente lo stesso Experience Cloud ID (`mid`) nel sito.
