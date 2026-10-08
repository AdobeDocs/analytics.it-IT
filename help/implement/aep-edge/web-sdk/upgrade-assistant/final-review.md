---
title: Revisione finale nell'Assistente all'aggiornamento di Web SDK
description: Rivedi e finalizza una migrazione di Web SDK, quindi pubblica in produzione la libreria di tag risultante.
feature: Implementation Basics
role: Admin, Developer, Leader
badge: Beta
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
    internal-label: Use cases
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d00e9f03-e50b-4162-b143-0c0817c937c2
    internal-label: Customer journeys
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 629efca210346d32b8555c60f7db15d1d8285b20
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 1%
---
# Revisione finale

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_finalreview"
>title="Revisione finale"
>abstract="Seleziona la sandbox di Experience Platform da utilizzare, quindi controlla tutti gli elementi creati o modificati da questa migrazione. Non cambia nulla finché non finalizzi la migrazione. Quando lo finalizzi, l’assistente per l’aggiornamento crea tutto contemporaneamente, aggiunge le modifiche ai tag a una nuova libreria e rende questa migrazione di sola lettura. Quindi pubblichi autonomamente tale libreria in produzione."

<!-- markdownlint-enable MD034 -->

La revisione finale è l’ultimo passaggio di una migrazione. Mostra tutto ciò che viene creato o modificato dalla migrazione in Experience Platform e nella proprietà dei tag.

## Esamina la creazione della migrazione {#review}

Innanzitutto, seleziona la sandbox di Experience Platform in cui vengono create le risorse durante la migrazione. Non puoi finalizzare la migrazione finché non selezioni una sandbox.

L’assistente per l’aggiornamento elenca quindi tutto ciò che viene creato o modificato dal completamento della migrazione:

* **[!UICONTROL XDM]**: un nuovo schema denominato dopo la mappatura XDM, insieme ai gruppi di campi personalizzati necessari. I gruppi di campi standard esistono già, pertanto lo schema li utilizza così come sono. Questa sezione viene visualizzata solo se si è scelto di creare un nuovo schema in [Mapping XDM](xdm-mapping.md#schema).
* **[!UICONTROL Datasets]**: due set di dati, uno per lo sviluppo e uno per la produzione. Ognuno è denominato in base alla migrazione, ad esempio `My migration - Development`.
* **[!UICONTROL Datastreams]**: due flussi di dati, uno per lo sviluppo e uno per la produzione, hanno lo stesso nome dei set di dati.
* **[!UICONTROL Adobe Tags]**: una nuova libreria denominata dopo la migrazione, ad esempio `Library - "My migration"`. La libreria contiene le regole e gli elementi dati che la migrazione modifica, insieme alla configurazione dell&#39;estensione necessaria per le azioni Web SDK.

## Finalizzare la migrazione {#finalize}

Fino a quando non completi la migrazione, l’assistente per l’aggiornamento non modifica la proprietà dei tag né crea nulla in Experience Platform.

>[!IMPORTANT]
>
>Una volta completata, la migrazione diventa di sola lettura. È comunque possibile aprirlo dalla pagina **[!UICONTROL Migrations]** per vedere cosa è stato creato, ma non è possibile modificarlo o finalizzarlo di nuovo. Poiché la nuova libreria è ancora in fase di sviluppo, puoi modificare o rimuovere le modifiche apportate ai tag nell’interfaccia utente dei tag prima di pubblicarla.

1. Seleziona **[!UICONTROL Create artifacts]**.
1. Nella finestra di dialogo **[!UICONTROL Verify these recommendations]**, seleziona **[!UICONTROL Continue]**.
1. Nella finestra di dialogo **[!UICONTROL Finalize this migration?]**, seleziona **[!UICONTROL Finalize]**.

L’assistente per l’aggiornamento crea tutto contemporaneamente e ne mostra l’avanzamento. Aggiunge le modifiche dei tag alla nuova libreria, ma non la pubblica.

## Pubblicare le modifiche {#publish}

Dopo aver completato la migrazione, sposta la nuova libreria nel flusso di pubblicazione dei tag:

1. Crea e verifica la libreria nell’ambiente di sviluppo per assicurarti che l’implementazione del Web SDK invii i dati previsti.
1. Invia la libreria per l&#39;approvazione e testala nell&#39;ambiente di staging.
1. Approva la libreria e pubblicala in produzione.

Vedi [Flusso di pubblicazione](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/publishing-flow) nella guida utente Tag.
