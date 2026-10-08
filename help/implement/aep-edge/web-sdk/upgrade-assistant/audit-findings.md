---
title: Risultati dei controlli nell'Assistente all'aggiornamento di Web SDK
description: Rivedi e risolvi i consigli di pulizia facoltativi per i componenti tag prima di eseguire la migrazione al Web SDK.
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
source-wordcount: '336'
ht-degree: 2%
---
# Risultati dell’audit

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_auditfindings"
>title="Risultati dell’audit"
>abstract="I risultati indicano le regole e gli elementi di dati che potresti voler pulire prima della migrazione, ad esempio elementi di dati che non fanno riferimento a nulla. Accetta un risultato per includere la modifica consigliata nella migrazione oppure rifiuta di lasciare il componente così com’è. Questo passaggio è facoltativo."

<!-- markdownlint-enable MD034 -->

L&#39;Assistente all&#39;aggiornamento controlla le regole e gli elementi dati selezionati nella [selezione di componenti](component-selection.md) e contrassegna quelli che è possibile ripulire prima della migrazione:

* Regole duplicate o regole che condividono eventi e condizioni che è possibile consolidare
* Sequenze di azioni delle regole che potrebbero influire sulla precisione dei dati
* Elementi dati duplicati che è possibile consolidare
* Elementi dati che potrebbero non essere utilizzati e che potresti disattivare

Questo passaggio è facoltativo. Puoi risolvere tutti i risultati desiderati oppure continuare direttamente alla [verifica della suite di rapporti](rs-verification.md).

## Rivedi un risultato {#review}

Selezionare un risultato per visualizzarne i dettagli, tra cui:

* Descrizione del risultato
* Configurazione corrente del componente
* Dove viene utilizzato il componente, sia nella proprietà dei tag che in Adobe Analytics

Ogni risultato include un’azione consigliata, che dipende dal tipo di risultato. Ad esempio, l’azione consigliata per un elemento dati a cui non si fa riferimento consiste nel disabilitarlo.

>[!IMPORTANT]
>
>Un elemento dati contrassegnato come non utilizzato potrebbe comunque essere oggetto di riferimento dinamico o dall’esterno dei tag. Prima di accettare un risultato, verificare le modifiche proposte, il codice personalizzato, l&#39;ordine delle azioni e i riferimenti per confermare che mantengono il comportamento desiderato.

## Risolvi i risultati {#resolve}

Quando si esegue l&#39;azione consigliata di un risultato, il risultato viene accettato. L&#39;Assistente per l&#39;aggiornamento aggiunge la modifica alla migrazione e la applica quando [finalizza la migrazione](final-review.md#finalize). Se non desideri apportare la modifica, rifiuta il risultato.

Se si cambia idea, è possibile riaprire un risultato accettato o rifiutato. Per aggiornare più risultati contemporaneamente, selezionali nell’elenco.
