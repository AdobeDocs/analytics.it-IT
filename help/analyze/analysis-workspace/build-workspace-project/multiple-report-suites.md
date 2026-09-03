---
title: Più suite di rapporti
description: Scopri come utilizzare più suite di rapporti in un unico progetto Analysis Workspace.
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
TQID: https://experienceleague.adobe.com/IrWsvooPWqWmbDAD-70CgI71gEPJCQY-1wFHFyuJsyc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: a544b409-2610-410d-a842-474ac1d0d54e
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: dcae653e-62c6-4cc8-84e6-ee110b848296
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 449
ht-degree: 68%

---

# Suite di rapporti multiple

Puoi creare progetti in Analysis Workspace con dati provenienti da più suite di rapporti. Le suite di rapporti vengono scelte a livello di pannello, in modo da poter scegliere una suite di rapporti diversa per ciascun pannello all’interno dello stesso progetto Workspace.

Questa funzionalità è utile per:

* Confrontare i dati provenienti da due aree geografiche diverse: i dati risiedono in due suite di rapporti diverse. Puoi creare tabelle e visualizzazioni per eseguire confronti affiancati dei dati.

* Creare un dashboard di metriche e visualizzazioni da segnalare ad altre organizzazioni. Puoi estrarre dati da varie suite di rapporti in nello stesso progetto.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Più suite di rapporti](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/multiple-report-suites-in-analysis-workspace){target="_blank"}.

>[!ENDSHADEBOX]


## Applica suite di rapporti a tutti i pannelli

Per applicare una suite di rapporti a tutti i pannelli contemporaneamente, fai clic con il pulsante destro del mouse sull’intestazione del pannello e seleziona **[!UICONTROL Apply Report Suite to All Panels]**.

![](assets/apply-rs-all-panels.png)

## Pannello attivo

Il pannello attivo è riconoscibile dal bordo blu chiaro intorno ad esso. È sufficiente selezionare all’interno di un pannello per renderlo attivo.

>[!TIP]
>
>Puoi trascinare e rilasciare contenuti in qualsiasi pannello presente nella stessa suite di rapporti del pannello attivo. Trascinare un contenuto in un pannello inattivo della stessa suite di rapporti rende il pannello attivo.
>

## Utilizzare le suite multi-rapporto

![](assets/mrs-ui.png)

1. Crea un nuovo progetto con 2 o più pannelli in Workspace.

1. Trascina i componenti (metriche, dimensioni, segmenti, intervalli di date) all’interno del pannello. Assicurati che i pannelli contengano dati e visualizzazioni specifici per la suite di rapporti.


   >[!NOTE]
   >
   >Talvolta durante il caricamento di un progetto (o il passaggio a una suite di rapporti) viene visualizzato un banner se non tutti i componenti inclusi nel progetto compaiono anche nella suite di rapporti. Verranno elencati i componenti mancanti. Segui [queste istruzioni](/help/admin/admin-console/permissions/product-profile.md) per impostare le autorizzazioni per le metriche/dimensioni richieste.
   >

   ![](assets/incompat-rs.png)

   Hai 3 opzioni per risolvere l’incompatibilità:
   * Abilita le dimensioni/metriche richieste.
   * Modifica la suite di rapporti.
   * Continua con alcuni dei componenti mancanti. Non si otterrà alcun dato per tali componenti, e/o si otterranno visualizzazioni vuote.

1. Modifica il pannello in un’altra suite di rapporti e osserva come l’etichetta del componente (suite di rapporti attualmente attiva) e i componenti elencati vengono aggiornati in base alla nuova suite di rapporti.

1. Usa una combinazione di tasti (`shift` durante lo spostamento) per trasformare un pannello inattivo in attivo.

1. (Facoltativo) Puoi anche passare ad altri generatori di componenti Analytics e accertarti che ora visualizzino l’etichetta della suite di rapporti che indica

   * Dove verrà creato un segmento: [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-build.md).
   * Dove verrà creata una metrica calcolata: [Generatore di metrica calcolata](/help/components/calculated-metrics/workflow/c-build-metrics/cm-build-metrics.md).
   * Dove verrà generato un avviso: [Generatore di avvisi](/help/components/alerts/alert-builder.md).
