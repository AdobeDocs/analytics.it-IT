---
description: Gli amministratori sono responsabili del monitoraggio dell’integrità del dizionario dei dati. Ciò include verificare se i componenti raccolgono dati, sono approvati, contengono descrizioni e sono privi di duplicati.
title: Monitorare l’integrità del dizionario dei dati
feature: Components
role: Admin
exl-id: 82176931-2bd9-4f4e-9ca7-4214d44151a8
TQID: https://experienceleague.adobe.com/q-wAiW4oUc9kH-ywKVLfNKtXHdEfnIr01GXSK-g0YqY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: c45e2849-b5ab-4ac6-8df1-bbe34c2dd79e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ba438d61e6834acb07c86cd0af58f95b88c1de7
workflow-type: tm+mt
source-wordcount: 361
ht-degree: 66%

---

# Monitorare l’integrità del dizionario dei dati {#monitor-data-dictionary}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_share_primary"
>title="Condividi componente primario"
>abstract="Quando questa opzione è selezionata, il componente principale viene condiviso con tutti coloro che hanno accesso ai componenti duplicati (sia i proprietari che gli utenti con cui i componenti sono condivisi). Tali utenti possono quindi selezionare il componente principale dall’elenco dei componenti per i progetti futuri. Tuttavia, non possono modificare il componente, anche se erano i proprietari di un componente duplicato che era stato consolidato. <br/>Questa opzione è disponibile solo quando il componente principale è un segmento, una metrica calcolata o un intervallo di date. Le metriche e le dimensioni sono sempre disponibili per tutti gli utenti.
>
>When this option is deselected, the primary component still replaces duplicates in existing projects and segments, but users who didn't previously have access to it can't access it from the component list for future projects. "

<!-- markdownlint-disable MD034 -->

<!-- markdownlint-enable MD034 -->

>[!CONTEXTUALHELP]
>id="aa_datadictionary_delete_duplicates"
>title="Elimina duplicati sostituiti"
>abstract="Quando questa opzione è selezionata, i duplicati consolidati non sono più disponibili per l’uso. Deseleziona questa opzione se desideri che i duplicati continuino a essere disponibili."

<!-- markdownlint-enable MD034 -->

Gli amministratori di Analytics sono responsabili della gestione di un dizionario dei dati integro.

## Caratteristiche di un dizionario dei dati integro

Un dizionario dei dati integro è un dizionario in cui tutti i componenti:

* Sono in uso e stanno raccogliendo dati

* Contengono descrizioni utili che consentono agli utenti di utilizzarle al meglio

* Sono privi di duplicati non necessari

* Sono approvati dall’amministratore

## Verificare l’integrità del dizionario dei dati

Per identificare i problemi di integrità nel dizionario dei dati:

1. Apri un progetto di Analysis Workspace.

1. Seleziona l’icona Dizionario dei dati a sinistra di Analysis Workspace. I modi alternativi per accedere al dizionario dati sono descritti in “Accedere al dizionario dei dati” in [Panoramica del dizionario dei dati](/help/analyze/analysis-workspace/components/data-dictionary/data-dictionary-overview.md).

   Viene visualizzata la finestra Dizionario dei dati.

   ![Vista amministratore del dizionario dei dati](assets/data-dictionary-admin.png)

1. Assicurati che nel menu a discesa sia selezionata la suite di rapporti corretta.

1. Nella scheda [!UICONTROL **Integrità del dizionario**], seleziona [!UICONTROL **Visualizza**] accanto a una delle seguenti opzioni:

   * [!UICONTROL **mancano descrizioni dei componenti**]

   * [!UICONTROL **i componenti hanno duplicati**]

   * [!UICONTROL **ai componenti non sono collegati dati**]

   A seconda di ciò che selezioni, il filtro appropriato viene applicato al dizionario dei dati e vengono visualizzati solo i componenti rilevanti.

1. Modifica i componenti per migliorare lo stato del dizionario dei dati. Per informazioni su come modificare un componente nel dizionario dei dati, vedi [Modificare le voci dei componenti nel dizionario dei dati](/help/analyze/analysis-workspace/components/data-dictionary/edit-entries-data-dictionary.md).
