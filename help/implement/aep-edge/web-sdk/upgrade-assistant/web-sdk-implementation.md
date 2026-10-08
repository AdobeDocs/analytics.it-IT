---
title: Implementazione di Web SDK nell’Assistente all’aggiornamento di Web SDK
description: Esaminare le azioni di Web SDK aggiunte dall'assistente per l'aggiornamento alle regole dei tag esistenti.
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
source-wordcount: '298'
ht-degree: 0%
---
# Implementazione di Web SDK

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_websdkimplementation"
>title="Implementazione di Web SDK"
>abstract="Esaminare le azioni di Web SDK aggiunte dall&#39;assistente per l&#39;aggiornamento alle regole. Le azioni di Adobe Analytics rimangono sul posto. Seleziona un componente per confrontare le configurazioni corrente e Web SDK una accanto all’altra. Solo i componenti presenti in coda vengono aggiunti alla migrazione."

<!-- markdownlint-enable MD034 -->

Utilizzando i componenti selezionati e la mappatura [XDM](xdm-mapping.md), l&#39;Assistente all&#39;aggiornamento aggiunge azioni Web SDK alle regole, direttamente dopo ogni azione di Adobe Analytics. Le azioni di Analytics rimangono attive, pertanto queste regole inviano dati sia ad Adobe Analytics che al Web SDK. La maggior parte degli elementi dati viene riportata invariata e le regole continuano a farvi riferimento per nome.

La colonna **[!UICONTROL Change type]** mostra l’effetto della finalizzazione della migrazione su ciascun componente:

* **[!UICONTROL Web SDK actions added]**: l&#39;Assistente all&#39;aggiornamento aggiunge azioni Web SDK alla regola.
* **[!UICONTROL No change]**: il componente viene portato avanti invariato.
* **[!UICONTROL Blocked]**: il componente deve essere esaminato prima che l&#39;Assistente all&#39;aggiornamento possa aggiungervi azioni di Web SDK. Seleziona il componente per vedere cosa lo sta bloccando.

Seleziona un componente per confrontare la configurazione corrente con quella del Web SDK. Se hai bisogno di più contesto, l’assistente per l’aggiornamento collega al componente nell’interfaccia utente dei tag.

I componenti in coda vengono aggiunti alla migrazione. Per mettere in coda un componente, selezionarlo nell&#39;elenco oppure selezionare **[!UICONTROL Queue]** nei relativi dettagli. Per rimuoverlo, selezionare **[!UICONTROL Remove from queue]**. L&#39;Assistente per l&#39;aggiornamento non modifica la proprietà dei tag fino a quando non [finalizza la migrazione](final-review.md#finalize).

L’assistente per l’aggiornamento utilizza l’intelligenza artificiale per generare le azioni di Web SDK e i risultati potrebbero non essere precisi o completi. La generazione delle azioni non verifica il loro comportamento sul sito, pertanto eseguine il test prima di pubblicare la libreria.
