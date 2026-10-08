---
title: Assistente all’aggiornamento di Web SDK
description: Pianifica ed esegui la migrazione dell’estensione tag Adobe Analytics a Adobe Experience Platform Web SDK.
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
source-git-commit: 212d38950264a33b925b7281c241992cadca2bfb
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 1%
---
# Assistente all’aggiornamento di Web SDK

L’Assistente all’aggiornamento di Web SDK consente di pianificare ed eseguire la migrazione dell’estensione tag Adobe Analytics a Adobe Experience Platform Web SDK. Questa funzione porta la migrazione in un’unica area di lavoro guidata, che consente di passare dall’implementazione dei tag esistenti al Web SDK in modo strutturato e tracciabile.

## Funzionamento dell&#39;Assistente all&#39;aggiornamento {#how-it-works}

Ogni migrazione funziona con l’implementazione di Adobe Analytics in una singola proprietà di tag. L’assistente per l’aggiornamento aggiunge azioni Web SDK alle regole esistenti senza rimuovere le azioni Adobe Analytics, pertanto l’implementazione continua a inviare dati ad Adobe Analytics insieme al Web SDK.

L’assistente per l’aggiornamento converte solo i componenti di Adobe Analytics. È possibile includere componenti di altre estensioni, ad esempio Adobe Target, Adobe Audience Manager o estensioni di terze parti, ma l&#39;Assistente per l&#39;aggiornamento non li converte nel Web SDK.

L&#39;Assistente all&#39;aggiornamento ti guida attraverso i passaggi seguenti e ogni passaggio si basa sulle decisioni che hai preso nel precedente:

1. **[Selezione di componenti](component-selection.md)**: scegliere le regole, gli elementi dati e le estensioni da includere nella migrazione.
1. **[Risultati dell&#39;audit](audit-findings.md)**: rivedi i consigli di pulizia facoltativi per i componenti selezionati.
1. **[Preparazione mapper](mapper-prep.md)**: rivedi le variabili di Analytics nelle suite di rapporti e scegli quelle da portare avanti.
1. **[Mappatura XDM](xdm-mapping.md)**: mappa le variabili Analytics sui campi in uno schema XDM.
1. **[Implementazione di Web SDK](web-sdk-implementation.md)**: controlla le azioni di Web SDK aggiunte dall&#39;assistente all&#39;aggiornamento alle regole.
1. **[Revisione finale](final-review.md)**: seleziona una sandbox di Experience Platform, controlla cosa crea la migrazione e finalizza la migrazione.

Ogni passaggio configura parte della migrazione e puoi tornare ai passaggi completati per rivederli o modificarli ogni volta che lo desideri. L’assistente per l’aggiornamento non modifica la proprietà dei tag né crea nulla in Experience Platform fino a quando non completi la migrazione. Quando lo finalizzi, l’assistente per l’aggiornamento crea tutto contemporaneamente e aggiunge le modifiche dei tag a una nuova libreria. Puoi quindi testare tale libreria e pubblicarla in produzione utilizzando il flusso di pubblicazione dei tag.

>[!IMPORTANT]
>
>L’assistente per l’aggiornamento utilizza l’intelligenza artificiale (IA) per generare consigli, ad esempio le mappature dei campi XDM e le configurazioni delle regole del Web SDK. Questi consigli potrebbero non essere accurati o completi. Verificali prima di pubblicare le modifiche nell’ambiente di produzione.

## Prerequisiti {#prerequisites}

Prima di creare una migrazione, assicurati di disporre di:

* Le [autorizzazioni](#permissions) necessarie per l&#39;Assistente all&#39;aggiornamento.
* Proprietà tag che utilizza l’estensione Adobe Analytics.
* Libreria in tale proprietà che contiene l’implementazione di cui desideri eseguire la migrazione. La libreria può essere in qualsiasi stato, inclusa la pubblicazione. Vedi [Librerie](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/publishing/libraries) nella guida utente Tag.

### Autorizzazioni {#permissions}

L&#39;Assistente all&#39;aggiornamento richiede il seguente accesso. Rivolgiti all’amministratore di prodotto Experience Platform della tua organizzazione per ottenere le autorizzazioni mancanti.

| Tipo di accesso | Obbligatorio |
| --- | --- |
| [Autorizzazioni di Experience Platform](https://experienceleague.adobe.com/en/docs/experience-platform/access-control/home#permissions) | <ul><li>[!UICONTROL View Schemas]</li><li>[!UICONTROL Manage Schemas]</li><li>[!UICONTROL View Datasets]</li><li>[!UICONTROL Manage Datasets]</li><li>[!UICONTROL View Identity Namespaces]</li></ul> |
| Accesso ai prodotti | <ul><li>Raccolta dati (tag)</li><li>Adobe Analytics</li></ul> |
| [Diritti tag](https://experienceleague.adobe.com/en/docs/experience-platform/tags/ui/administration/user-permissions) | [!UICONTROL Manage Properties] |

Quando sei pronto, [crea una migrazione](manager.md#create).
