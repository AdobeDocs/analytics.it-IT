---
title: Verifica della suite di rapporti nell’Assistente all’aggiornamento di Web SDK
description: Esamina le variabili di Analytics nelle suite di rapporti e scegli quali portare avanti nella mappatura XDM.
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
source-wordcount: '496'
ht-degree: 0%
---
# Verifica suite di rapporti

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_rsverification"
>title="Verifica suite di rapporti"
>abstract="Esamina le variabili di Analytics che la proprietà tags invia a ogni suite di rapporti. Le variabili selezionate vengono riportate nella mappatura XDM. Utilizza le schede per verificare la presenza di dati recenti, trovare variabili duplicate e confrontare le impostazioni tra suite di rapporti."

<!-- markdownlint-enable MD034 -->

L’assistente per l’aggiornamento identifica le suite di rapporti a cui la proprietà tags invia i dati, quindi confronta le variabili Analytics nella tua implementazione con la configurazione di ogni suite di rapporti e i dati recenti. Utilizzare questo passaggio per decidere quali variabili vengono riportate al [mapping XDM](xdm-mapping.md).

L’assistente per l’aggiornamento utilizza le suite di rapporti per comprendere quali variabili vengono impostate per l’implementazione e come vengono configurate. I dati relativi alle attività coprono gli ultimi 90 giorni.

## Attività variabile {#variable-activity}

La scheda **[!UICONTROL Variable activity]** elenca le variabili di Analytics per la suite di rapporti che hai scelto di mappare in [Analisi delle variabili](#variable-analysis) e mostra se ciascuna di esse ha raccolto dati negli ultimi 90 giorni.

Variabili selezionate per il riporto al mapping XDM. Considera di cancellare le variabili che non raccolgono più dati o che non sono necessarie nell’implementazione di Web SDK. Una variabile senza attività recenti potrebbe essere ancora in uso, ad esempio se è stagionale o presenta un traffico ridotto, quindi conferma di non averne bisogno prima di cancellarla.

Per ogni variabile elenco e prop elenco da portare avanti, immettere il delimitatore che separa i relativi valori. L’assistente per l’aggiornamento non può ottenere delimitatori da Adobe Analytics e non puoi continuare finché ciascuno di essi non ha un delimitatore.

## Analisi delle variabili {#variable-analysis}

Se la proprietà tags invia dati a più di una suite di rapporti, scegli innanzitutto la suite di rapporti da mappare. La scheda **[!UICONTROL Variable analysis]** contrassegna quindi le variabili che potrebbero richiedere una decisione prima di mapparle:

* Variabili che sembrano raccogliere gli stessi dati. Assicurati che acquisiscano le stesse informazioni, quindi decidi se unirle in una singola variabile o tenerle separate.
* Variabili che non hanno raccolto dati di recente.
* Variabili i cui valori sono tutti &quot;Non specificato&quot;.

## Confrontare le suite di rapporti {#compare}

Se la proprietà tags invia dati a più di una suite di rapporti, la scheda **[!UICONTROL Compare report suites]** confronta le impostazioni di ciascuna variabile fino a tre di queste suite di rapporti. Utilizzala per trovare variabili configurate in modo diverso tra le suite di rapporti prima di mapparle su uno schema.

## Aggiornare i dati della suite di rapporti {#refresh}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_upgradeassistant_rsverification_refresh"
>title="Aggiornare i dati della suite di rapporti"
>abstract="Controlla nuovamente le suite di rapporti collegate a questa proprietà di tag, incluse le impostazioni delle variabili e i dati recenti, quindi esegue nuovamente l’analisi della variabile. Se l’assistente per l’aggiornamento non ha ancora trovato suite di rapporti, cerca prima queste nella proprietà tags. Le selezioni e le decisioni vengono mantenute."

<!-- markdownlint-enable MD034 -->

In questo passaggio è possibile modificare le suite di rapporti analizzate dall’assistente per l’aggiornamento. Se la configurazione della suite di rapporti cambia mentre è in corso una migrazione, seleziona **[!UICONTROL Refresh report suite data]** per eseguire nuovamente l&#39;analisi. L’assistente per l’aggiornamento mantiene le selezioni e le decisioni esistenti.

Al termine, selezionare **[!UICONTROL Save and continue]** per passare alla [mappatura XDM](xdm-mapping.md).
