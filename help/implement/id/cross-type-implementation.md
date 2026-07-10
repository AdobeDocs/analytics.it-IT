---
title: Tracciare diversi tipi di implementazione
description: Utilizza diversi tipi di implementazione e tieni traccia dei visitatori tra di loro in modo semplice.
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
feature: Implementation Basics
role: Admin, Developer, Leader
TQID: https://experienceleague.adobe.com/FM6c33rpXxzy1huu8KE0VBkfe4FGIySczmVMrprFEUY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: a947d2d7f45d4155a61cbfe0f8110851cca32e60
workflow-type: tm+mt
source-wordcount: 590
ht-degree: 11%

---

# Tracciare diversi tipi di implementazione

L’architettura di base di un’implementazione Adobe Analytics è coerente per tutti i tipi di implementazione. Il processo comporta la definizione delle variabili e la loro compilazione in una richiesta di immagine inviata ai server di raccolta dati di Adobe. Questo concetto significa che in Raccolta dati di Adobe Experience Platform puoi passare facilmente da AppMeasurement a Web SDK e dalle rispettive estensioni nelle diverse pagine dello stesso sito.

Adobe consiglia di mantenere la coerenza nell’implementazione di un sito utilizzando lo stesso tipo di implementazione in tutte le pagine. Tuttavia, se alcune parti del sito hanno requisiti diversi, puoi utilizzare questa pagina per assicurarti che i visitatori vengano tracciati in modo coerente tra le pagine.

Se utilizzi più di un tipo di implementazione (ad esempio richieste di immagini AppMeasurement e hardcoded), assicurati che le seguenti variabili siano impostate correttamente e si corrispondano tra loro.

>[!NOTE]
>
>Tutti i tipi di implementazione devono utilizzare lo stesso tipo di identificazione del visitatore (ID Analytics legacy, servizio ID visitatore o servizio Experience Platform Identity). Adobe consiglia di utilizzare un ECID in tutte le implementazioni, ove possibile.

| Variabile | Estensione tag Web SDK | Web SDK (Alloy) | Estensione Analytics | AppMeasurement | Richiesta immagine hardcoded |
|---|---|---|---|---|---|
| ID suite di rapporti | Aggiungi Adobe Analytics as a service durante [la configurazione di uno stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure) | Aggiungi Adobe Analytics as a service durante [la configurazione di uno stream di dati](https://experienceleague.adobe.com/it/docs/experience-platform/datastreams/configure) | [!UICONTROL Report suites] nella sezione [!UICONTROL Library management] quando [Configurazione dell&#39;estensione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/analytics/overview) | Argomento stringa in [`s_gi`](../vars/functions/s-gi.md) | Parte dell&#39;URL `pathname` (dopo `/b/ss/`) |
| Servizio ID visitatore | Include in modalità nativa il [servizio Experience Platform Identity](https://experienceleague.adobe.com/it/docs/experience-platform/identity/home); richiede [`idMigrationEnabled`](https://experienceleague.adobe.com/it/docs/experience-platform/collection/js/commands/configure/idmigrationenabled) per leggere i cookie del servizio ID visitatore | Include in modalità nativa il [servizio Experience Platform Identity](https://experienceleague.adobe.com/it/docs/experience-platform/identity/home); richiede [[!UICONTROL Migrate ECID from VisitorAPI to the Web SDK]](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/web-sdk/configure/identity) per leggere i cookie del servizio ID visitatore | Utilizza l&#39;estensione tag [&#39;[!UICONTROL Experience Cloud ID Service]&#39;](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/id-service/overview), che implementa il [servizio ID visitatori](https://experienceleague.adobe.com/it/docs/id-service/using/home) | Implementa il [servizio ID visitatori](https://experienceleague.adobe.com/it/docs/id-service/using/home) (`VisitorAPI.js`) | Effettua una [chiamata separata al servizio ID visitatore](https://experienceleague.adobe.com/it/docs/id-service/using/implementation/direct-integration) per ottenere l&#39;ID desiderato e includere `mid` nella stringa di query |
| Dominio Edge | Il campo [!UICONTROL Edge Domain] durante la [configurazione dell&#39;estensione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/web-sdk/web-sdk-extension-configuration) | La proprietà `edgeDomain` durante la [configurazione del Web SDK](https://experienceleague.adobe.com/it/docs/experience-platform/web-sdk/commands/configure/overview) | [!UICONTROL SSL Tracking Server] nella sezione [!UICONTROL General] quando [Configurazione dell&#39;estensione](https://experienceleague.adobe.com/it/docs/experience-platform/tags/extensions/client/analytics/overview) | La variabile [`trackingServerSecure`](../vars/config-vars/trackingserversecure.md) | `hostname` dell&#39;URL della richiesta di immagine |

>[!NOTE]
>
>Le implementazioni basate su AppMeasurement (inclusa l&#39;estensione tag Analytics) non sono compatibili con il [servizio Experience Platform Identity](https://experienceleague.adobe.com/it/docs/id-service/using/home). Devi usare il minimo comune denominatore per l&#39;identificazione dei visitatori per eseguire la sincronizzazione tra i tipi di implementazione, che in genere è il [Servizio ID visitatori](https://experienceleague.adobe.com/it/docs/id-service/using/home) (`VisitorAPI.js`).

Se una di queste variabili non è coerente in ciascun tipo di implementazione, Adobe probabilmente le considera come visitatori separati. Se i visitatori non vengono tracciati facilmente nei diversi tipi di implementazione sul sito, il motivo più comune è che l’identificazione dei visitatori non è configurata correttamente. Verificare che ogni tipo di implementazione ottenga correttamente lo stesso ECID (`mid` [stringa di query](/help/implement/validate/query-parameters.md)) nel sito.
