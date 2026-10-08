---
title: Selezione di componenti nell'Assistente all'aggiornamento di Web SDK
description: Scegli quali regole di tag, elementi dati ed estensioni includere in una migrazione Web SDK.
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
source-wordcount: '384'
ht-degree: 0%
---
# Selezione di componenti

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection"
>title="Selezione di componenti"
>abstract="Scegli le regole, gli elementi dati e le estensioni da includere in questa migrazione. I componenti che contribuiscono attivamente all’implementazione di Adobe Analytics vengono selezionati per impostazione predefinita. I passaggi successivi funzionano solo con i componenti selezionati qui."

La selezione dei componenti è il primo passaggio di una migrazione. Puoi utilizzarlo per scegliere quali regole, elementi dati ed estensioni includere nella migrazione dalla proprietà dei tag.

L&#39;Assistente all&#39;aggiornamento organizza i componenti della proprietà dei tag in **[!UICONTROL Rules]**, **[!UICONTROL Data Elements]** e **[!UICONTROL Extensions]** schede. Ogni scheda elenca tutti i componenti della proprietà di quel tipo, in base allo snapshot della libreria eseguito dall&#39;Assistente all&#39;aggiornamento al momento della [creazione della migrazione](manager.md#create). Per impostazione predefinita, vengono selezionati solo i componenti che contribuiscono attivamente all’implementazione di Adobe Analytics. Puoi selezionare o deselezionare qualsiasi componente.

La colonna **[!UICONTROL Published]** mostra se ogni componente fa parte della libreria selezionata. I componenti che non fanno parte della libreria sono presenti nella proprietà dei tag ma non nella libreria. Per filtrare l&#39;elenco in base a questo, utilizzare il filtro **[!UICONTROL Source]**.

È possibile includere componenti non correlati ad Adobe Analytics, ad esempio componenti per Adobe Target, Adobe Audience Manager o estensioni di terze parti, ma l’assistente per l’aggiornamento non li converte nel Web SDK.

I componenti selezionati determinano i passaggi successivi da utilizzare. Ad esempio, puoi includere elementi dati che non fanno riferimento a nulla in modo che [risultati del controllo](audit-findings.md) possa contrassegnarli per la pulizia.

## Visualizza dettagli componente {#details}

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_tagsusage"
>title="Utilizzo dei tag"
>abstract="Le regole, gli elementi dati e le estensioni che utilizzano questo componente. L’utilizzo dell’estensione copre solo le impostazioni di configurazione dell’estensione. L’utilizzo all’interno di una regola viene visualizzato in Utilizzo regola."

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_componentselection_analyticsusage"
>title="Utilizzo di Analytics"
>abstract="Le variabili Adobe Analytics a cui è assegnato questo componente, raggruppate per tipo di variabile."

<!-- markdownlint-enable MD034 -->

Seleziona il nome di un componente per aprire un pannello che mostra la sua configurazione e dove viene utilizzato:

* **[!UICONTROL Tags usage]**: regole, elementi dati ed estensioni che utilizzano il componente. **[!UICONTROL Extension usage]** copre solo le impostazioni di configurazione delle estensioni. L&#39;utilizzo in una regola viene visualizzato in **[!UICONTROL Rule usage]**.
* **[!UICONTROL Analytics usage]**: variabili Adobe Analytics a cui è assegnato il componente, raggruppate per tipo di variabile.

Per visualizzare il componente nell’interfaccia utente dei tag, selezionane il nome nella parte superiore del pannello.

Al termine, selezionare **[!UICONTROL Save and continue]** per passare a [risultati controllo](audit-findings.md).