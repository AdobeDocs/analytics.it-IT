---
title: Mappatura XDM nell’assistente all’aggiornamento di Web SDK
description: Mappa le variabili Adobe Analytics ai campi in uno schema XDM come parte di una migrazione di Web SDK.
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
source-wordcount: '412'
ht-degree: 3%
---
# Mappatura XDM

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping"
>title="Mappatura XDM"
>abstract="Mappa le variabili di Analytics selezionate sui campi di uno schema XDM. L’assistente per l’aggiornamento può creare un nuovo schema con mappature suggerite dall’intelligenza artificiale, oppure è possibile mappare le variabili a uno schema già esistente. Rivedi tutte le mappature prima di continuare."

<!-- markdownlint-enable MD034 -->

Il Web SDK invia i dati utilizzando i campi [Experience Data Model (XDM)](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/home), pertanto ogni variabile di Analytics portata avanti dalla [verifica della suite di rapporti](rs-verification.md) richiede un campo corrispondente in uno schema XDM. In questo passaggio, scegli uno schema e mappi le variabili ai relativi campi.

## Scegliere uno schema {#schema}

Puoi creare la mappatura in uno dei due modi seguenti:

* **Crea un nuovo schema**: l&#39;assistente per l&#39;aggiornamento analizza le variabili di Analytics e suggerisce un campo XDM per ciascuna, quindi genera uno schema da tali suggerimenti per la revisione.
* **Utilizza uno schema esistente**: seleziona uno schema già esistente in Experience Platform, quindi mappa autonomamente ogni variabile su un campo.

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_xdmmapping_fieldgroups"
>title="Preferenze per il gruppo di campi"
>abstract="Scegli il tipo di gruppo di campi preferito dall’assistente per l’aggiornamento quando crea lo schema. I gruppi di campi standard sono definiti da Adobe. I gruppi di campi personalizzati sono definiti dall’organizzazione."

<!-- markdownlint-enable MD034 -->

Quando crei un nuovo schema, scegli anche se l’assistente per l’aggiornamento preferisce gruppi di campi standard o personalizzati. I gruppi di campi standard sono definiti da Adobe, mentre i gruppi di campi personalizzati sono definiti dalla tua organizzazione. Vedi [Gruppo di campi](https://experienceleague.adobe.com/it/docs/experience-platform/xdm/schema/composition#field-group) nella documentazione XDM.

## Rivedi la mappatura {#review}

La mappatura elenca ogni variabile di Analytics accanto al campo XDM a cui è mappata, con un’anteprima dello schema completo accanto. Seleziona parte dello schema per filtrare l’elenco in base alle variabili associate. Puoi regolare sia le singole mappature che lo schema stesso.

L’assistente per l’aggiornamento utilizza l’intelligenza artificiale per suggerire le mappature; i risultati potrebbero non essere precisi o completi. Prima di continuare, controlla ogni mappatura. L&#39;Assistente all&#39;aggiornamento non crea lo schema in Experience Platform fino a quando non [finalizza la migrazione](final-review.md#finalize).

Al termine, seleziona **[!UICONTROL Save and continue]** per salvare la mappatura e passare a [Implementazione di Web SDK](web-sdk-implementation.md). Per modificare la mappatura dopo averla salvata, selezionare **[!UICONTROL Edit]**, apportare le modifiche desiderate, quindi selezionare di nuovo **[!UICONTROL Save and continue]**. Le modifiche che non vengono salvate in questo modo non vengono incluse quando si finalizza la migrazione.
