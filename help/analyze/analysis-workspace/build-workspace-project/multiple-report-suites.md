---
title: Più suite di rapporti in Workspace
description: Scopri come e perché creare progetti in Workspace con più suite di rapporti
translation-type: tm+mt
source-git-commit: e60de040e1036a1344baecfcc9c1fd5d71c4cf40

---


# Più suite di rapporti in Workspace

Ora puoi creare progetti in Analysis Workspace con dati provenienti da più suite di rapporti. Le suite di rapporti ora possono essere selezionate a livello del pannello, per cui puoi scegliere una suite di rapporti diversa per ciascun pannello all’interno dello stesso progetto Workspace.

Questa funzionalità è utile, ad esempio, per: 

* Confrontare i dati provenienti da due aree geografiche diverse: i dati risiedono in due suite di rapporti diverse. Puoi creare tabelle e visualizzazioni per eseguire confronti affiancati dei dati.

* Creare un dashboard di metriche e visualizzazioni da segnalare ad altre organizzazioni. Ora puoi estrarre dati da varie suite di rapporti nello stesso progetto.

## Pannello attivo

Con questa funzione viene introdotto il concetto di “pannello attivo” e “pannello inattivo”. Potete riconoscere il pannello attivo dal bordo blu chiaro intorno ad esso. Se si fa clic all’interno di un pannello, il pannello diventa attivo.

>[!IMPORTANT]
>Puoi trascinare e rilasciare i contenuti in qualsiasi pannello presente nella stessa suite di rapporti del pannello attivo. Trascinando in un pannello inattivo della stessa suite di rapporti, il pannello diventa attivo.

| Attività | Pannello attivo | Pannello inattivo |
|---|---|---|
| Modificare la suite di rapporti | Sì | No |
| Trascinare i componenti | Sì | Sì, per qualsiasi pannello presente nella stessa suite di rapporti del pannello attivo. |
| Trascinare le visualizzazioni | Sì | Sì, per qualsiasi pannello presente nella stessa suite di rapporti del pannello attivo. |

## Utilizzare le suite multi-rapporto

![](assets/mrs-ui.png)

1. Crea un nuovo progetto con 2 o più pannelli in Workspace.

1. Trascina i componenti (metriche, dimensioni, segmenti, intervalli di date) all’interno del pannello. Assicurati che i pannelli contengano dati e visualizzazioni specifici per la suite di rapporti.


   >[!NOTE]
   >A volte, quando carichi un progetto (o passa a una suite di rapporti) viene visualizzato un banner in cui non tutti i componenti inclusi nel progetto sono inclusi nella suite di rapporti. Verranno elencati i componenti mancanti. Segui [queste istruzioni](/help/admin/admin-console/permissions/product-profile.md) per impostare le autorizzazioni per le metriche/dimensioni richieste.

   ![](assets/incompat-rs.png)

   Hai 3 opzioni per risolvere l’incompatibilità:
   * Abilita le dimensioni/metriche richieste
   * Modifica la suite di rapporti.
   * Continua con alcuni dei componenti mancanti. Non si otterrà alcun dato per tali componenti, e/o si otterranno visualizzazioni vuote.

1. Modifica il pannello in un’altra suite di rapporti e osserva come l’etichetta del componente (suite di rapporti attualmente attiva) e i componenti elencati vengono aggiornati in base alla nuova suite di rapporti.

1. Use a keyboard shortcut (`shift` while dragging) to turn an inactive panel to an active panel.

1. (Facoltativo) Puoi anche passare ad altri generatori di componenti Analytics e accertarti che ora visualizzino l’etichetta della suite di rapporti che indica

   * Dove verrà creato un segmento: [Generatore di segmenti](https://docs.adobe.com/content/help/en/analytics/components/segmentation/segmentation-workflow/seg-build.html).
   * Dove verrà creata una metrica calcolata: [Generatore di metrica calcolata](https://docs.adobe.com/content/help/en/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html).
   * Dove verrà generato un avviso: [Generatore di avvisi](https://docs.adobe.com/content/help/en/analytics/components/alerts/alert-builder.html).