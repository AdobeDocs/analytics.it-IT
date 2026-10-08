---
title: Gestire le migrazioni tramite l'Assistente all'aggiornamento di Web SDK
description: Creare, visualizzare e aprire le migrazioni nell'Assistente all'aggiornamento di Web SDK.
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
source-wordcount: '385'
ht-degree: 0%
---
# Gestire le migrazioni

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_migrations"
>title="Migrazioni"
>abstract="Ogni migrazione aggiorna l’implementazione di Adobe Analytics in una proprietà tag al Web SDK. Apri una migrazione per continuare dal punto in cui hai interrotto la sessione, oppure seleziona &quot;Nuovo&quot; per avviarne una."

La pagina **[!UICONTROL Migrations]** è il punto di partenza dell&#39;Assistente all&#39;aggiornamento di Web SDK. Elenca le migrazioni all’interno dell’organizzazione, con l’indicazione dell’avanzamento, dello stato e di chi le ha create. Utilizzare questa pagina per creare una migrazione o per aprirne una esistente.

## Creare una migrazione {#create}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_newmigration"
>title="Nuova migrazione"
>abstract="Seleziona la proprietà dei tag di cui vuoi eseguire la migrazione e una libreria in tale proprietà. L’assistente per l’aggiornamento crea un’istantanea della libreria quando crei la migrazione. Le modifiche apportate alla libreria dopo uno snapshot di migrazione non sono incluse. La proprietà dei tag non viene modificata fino a quando non completi la migrazione."

<!-- markdownlint-enable MD034 -->

Prima di creare una migrazione, assicurati di soddisfare i [prerequisiti](overview.md#prerequisites).

1. Nella pagina **[!UICONTROL Migrations]**, selezionare **[!UICONTROL New]**.
1. Immettere un nome per la migrazione e, facoltativamente, una descrizione.
1. Seleziona la proprietà dei tag di cui desideri eseguire la migrazione.
1. Seleziona una libreria di tag. Quando crei la migrazione, l’assistente per l’aggiornamento crea un’istantanea dell’implementazione così come esiste in questa libreria. Le modifiche apportate successivamente alla libreria non vengono riportate nella migrazione.
1. Seleziona **[!UICONTROL Create]**.

La nuova migrazione viene visualizzata nell’elenco. Aprilo per avviare la [selezione di componenti](component-selection.md).

## Aprire una migrazione {#open}

Seleziona il nome di una migrazione per aprirla. I passaggi della migrazione vengono visualizzati nel menu di navigazione a sinistra. Puoi tornare a qualsiasi passaggio completato per rivederlo o modificarlo con la frequenza desiderata, ma i passaggi non ancora raggiunti non sono disponibili.

L’assistente per l’aggiornamento salva l’avanzamento durante l’esecuzione dei passaggi, in modo da poter uscire da una migrazione e tornare ad essa in un secondo momento. Nessuna configurazione ha effetto finché non [finalizza la migrazione](final-review.md#finalize). Una volta completata, la migrazione diventa di sola lettura. Puoi comunque aprirlo per vedere cosa ha creato, ma non puoi modificarlo.

## Altre azioni di migrazione {#actions}

Seleziona la riga di una migrazione per visualizzare le azioni disponibili:

* **[!UICONTROL Continue]**: apre la migrazione.
* **[!UICONTROL Duplicate run]**: crea una copia della migrazione.
* **[!UICONTROL Rename]**: modifica il nome e la descrizione della migrazione.
* **[!UICONTROL Archive]**: modifica lo stato della migrazione in **[!UICONTROL Archived]**.
* **[!UICONTROL Delete migration]**: elimina definitivamente la migrazione. Non puoi annullare questa operazione.
