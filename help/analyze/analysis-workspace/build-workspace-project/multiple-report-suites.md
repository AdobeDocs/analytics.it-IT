---
title: Suite di rapporti multiple
description: Scopri come e perché creare progetti in Workspace con più suite di rapporti
feature: Workspace Basics
role: User, Admin
exl-id: 0429ddd9-935f-44ef-ae1e-97bb02e6e2df
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 87%

---

# Suite di rapporti multiple

Puoi creare progetti in Analysis Workspace con dati provenienti da più suite di rapporti. Le suite di rapporti vengono scelte a livello di pannello, in modo da poter scegliere una suite di rapporti diversa per ciascun pannello all’interno dello stesso progetto Workspace.

Questa funzionalità è utile, ad esempio, per:

* Confrontare i dati provenienti da due aree geografiche diverse: i dati risiedono in due suite di rapporti diverse. Puoi creare tabelle e visualizzazioni per eseguire confronti affiancati dei dati.

* Creare un dashboard di metriche e visualizzazioni da segnalare ad altre organizzazioni. Puoi estrarre dati da varie suite di rapporti in nello stesso progetto.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Più suite di rapporti](https://video.tv.adobe.com/v/36964?quality=12&learn=on&captions=ita){target="_blank"}.

>[!ENDSHADEBOX]


## Applica suite di rapporti a tutti i pannelli

Per applicare una suite di rapporti a tutti i pannelli contemporaneamente, fai clic con il pulsante destro del mouse sull’intestazione del pannello e seleziona **[!UICONTROL Apply Report Suite to All Panels]**.

![](assets/apply-rs-all-panels.png)

## Pannello attivo

Con questa funzione viene introdotto il concetto di “pannello attivo” e “pannello inattivo”. Il pannello attivo è riconoscibile dal bordo blu chiaro intorno ad esso. È sufficiente fare clic all’interno del pannello per renderlo attivo.

>[!TIP]
>Puoi trascinare e rilasciare contenuti in qualsiasi pannello presente nella stessa suite di rapporti del pannello attivo. Trascinare un contenuto in un pannello inattivo della stessa suite di rapporti rende il pannello attivo.

| Attività | Pannello attivo | Pannello inattivo |
| --- | --- | --- |
| Modificare la suite di rapporti | Sì | No |
| Trascinare i componenti | Sì | Sì, per qualsiasi pannello presente nella stessa suite di rapporti del pannello attivo. |
| Trascinare le visualizzazioni | Sì | Sì, per qualsiasi pannello presente nella stessa suite di rapporti del pannello attivo. |

## Utilizzare le suite multi-rapporto

![](assets/mrs-ui.png)

1. Crea un nuovo progetto con 2 o più pannelli in Workspace.

1. Trascina i componenti (metriche, dimensioni, segmenti, intervalli di date) all’interno del pannello. Assicurati che i pannelli contengano dati e visualizzazioni specifici per la suite di rapporti.


   >[!NOTE]
   >Talvolta durante il caricamento di un progetto (o il passaggio a una suite di rapporti) compare un banner se non tutti i componenti inclusi nel progetto compaiono anche nella suite di rapporti. Verranno elencati i componenti mancanti. Segui [queste istruzioni](/help/admin/admin-console/permissions/product-profile.md) per impostare le autorizzazioni per le metriche/dimensioni richieste.

   ![](assets/incompat-rs.png)

   Hai 3 opzioni per risolvere l’incompatibilità:
   * Abilita le dimensioni/metriche richieste.
   * Modifica la suite di rapporti.
   * Continua con alcuni dei componenti mancanti. Non si otterrà alcun dato per tali componenti, e/o si otterranno visualizzazioni vuote.

1. Modifica il pannello in un’altra suite di rapporti e osserva come l’etichetta del componente (suite di rapporti attualmente attiva) e i componenti elencati vengono aggiornati in base alla nuova suite di rapporti.

1. Usa una combinazione di tasti (`shift` durante lo spostamento) per trasformare un pannello inattivo in attivo.

1. (Facoltativo) Puoi anche passare ad altri generatori di componenti Analytics e accertarti che ora visualizzino l’etichetta della suite di rapporti che indica

   * Dove verrà creato un segmento: [Generatore di segmenti](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-build.html?lang=it).
   * Dove verrà creata una metrica calcolata: [Generatore di metrica calcolata](https://experienceleague.adobe.com/docs/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html?lang=it).
   * Dove verrà generato un avviso: [Generatore di avvisi](https://experienceleague.adobe.com/docs/analytics/components/alerts/alert-builder.html?lang=it).
