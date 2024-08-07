---
title: Panoramica del pannello di confronto dei segmenti
description: Scopri come utilizzare il pannello di confronto dei segmenti, parte del Segmento IQ di Analysis Workspace.
keywords: Analysis Workspace, segmento IQ
feature: Segmentation
role: User, Admin
exl-id: 1f5df6fb-1e9f-4b8f-885c-bf9e68d88c89
source-git-commit: 1ee50c6a2231795b2ad0015a79e09b7c1c74d850
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 99%

---

# Panoramica del pannello di confronto dei segmenti

Il pannello di confronto dei segmenti è una funzione del [Segmento IQ](../../segment-iq.md) che rileva le differenze più importanti dal punto di vista statistico tra un numero illimitato di segmenti. La funzione esegue un’analisi automatizzata di tutte le dimensioni e metriche a cui hai accesso. Rileva automaticamente le caratteristiche chiave dei segmenti di pubblico che guidano i KPI della tua azienda e ti consente di conoscere il livello di sovrapposizione dei segmenti.

Ecco un video sul confronto dei segmenti:

>[!VIDEO](https://video.tv.adobe.com/v/23976/?quality=12)

## Creazione di un pannello di confronto dei segmenti

1. Accedi a [experiencecloud.adobe.com](https://experiencecloud.adobe.com) utilizzando le credenziali Adobe ID.
1. Fai clic sull’icona a 9 quadrati in alto a destra, quindi fai clic sul logo a colori di Analytics.
1. Nella barra di navigazione superiore, fai clic su Workspace.
1. Fai clic sul pulsante “Crea nuovo progetto”.
1. Nella finestra a comparsa modale, assicurati che sia selezionato “Progetto vuoto”, quindi fai clic su Crea.
1. Fai clic sul pulsante Pannelli a sinistra, quindi trascina il pannello Confronto segmenti sopra o sotto il pannello della tabella a forma libera creato automaticamente.

   ![Pannello di confronto](assets/seg-compare-panel.png)

1. Seleziona i segmenti da confrontare e trascinali nel pannello.

   ![Confronto del pubblico](assets/compare-audiences.png)

   Dopo aver trascinato un segmento nel pannello, Analytics crea automaticamente un segmento [!UICONTROL 'Everyone Else'] che include tutti gli utenti NON inclusi nel segmento scelto. Si tratta di un segmento utilizzato di frequente nel pannello di confronto, ma è possibile rimuoverlo e confrontare un segmento diverso.

   ![Tutti gli altri](assets/everyone-else.png)

1. Una volta stabiliti i due segmenti da confrontare, fai clic su [!UICONTROL Build].

   Questa azione avvia un processo di back-end che cerca le differenze statistiche tra i due segmenti selezionati e tutte le dimensioni, le metriche e gli altri segmenti. Una barra di avanzamento nella parte superiore del pannello indica il tempo rimanente per l’analisi di ogni metrica e dimensione. Le metriche, le dimensioni e i segmenti utilizzati più di frequente hanno priorità e sono analizzati per primi, in modo che i risultati più rilevanti vengano restituiti in modo tempestivo.

## Escludere componenti dal confronto

Talvolta è necessario escludere dimensioni, metriche o segmenti dal confronto di segmenti. Ad esempio, se si confronta il segmento “Utenti dispositivi mobili Stati Uniti” con “Utenti dispositivi mobili Germania”. L’inclusione di dimensioni relative alla geografia non avrebbe senso, poiché questi segmenti già implicano tali differenze.

1. Dopo aver trascinato i due segmenti desiderati nel pannello, fai clic su [!UICONTROL 'Show Advanced Options'].
1. Trascina i componenti da escludere nel pannello [!UICONTROL Excluded Components].

   ![Componenti esclusi](assets/excluded-components.png)

Fai clic su [!UICONTROL 'Set as default'] per escludere automaticamente i componenti correnti in tutti i futuri confronti fra segmenti. Se desideri modificare i componenti esclusi, fai clic su un tipo di componente, quindi fai clic sulla X accanto a un componente per includerlo nuovamente nell’analisi. Fai clic su Clear All (Cancella tutto) per includere nuovamente tutti i componenti nel confronto dei segmenti.

![Dimensioni escluse](assets/excluded-dimensions.png)

## Visualizzazione di un rapporto di confronto dei segmenti

Al termine dell’analisi dei due segmenti desiderati, Adobe mostra i risultati ottenuti tramite diverse visualizzazioni:

![Visualizzazioni 1](assets/new-viz.png)

![Visualizzazioni 2](assets/new-viz2.png)

### Dimensione e sovrapposizione

Illustra le dimensioni comparative di ciascun segmento selezionato e il livello di sovrapposizione tra di essi mediante un diagramma di Venn. Puoi passare il mouse sull’elemento visivo per vedere quanti visitatori si trovavano in ciascuna sezione di sovrapposizione o non sovrapposizione. Puoi fare clic con il pulsante destro del mouse sulla sovrapposizione per creare un nuovo segmento per un’ulteriore analisi. Se i due segmenti si escludono a vicenda, non viene visualizzata alcuna sovrapposizione tra i due cerchi (generalmente visualizzata con i segmenti che utilizzano un contenitore di hit).

![Dimensione e sovrapposizione](assets/size-overlap.png)

### Riepiloghi sulla popolazione

A destra della visualizzazione Dimensione e sovrapposizione viene visualizzato il numero totale di visitatori univoci in ciascun segmento e nella sovrapposizione.

![Riepiloghi sulla popolazione](assets/population_summaries.png)

### Metriche principali

Visualizza le metriche più importanti dal punto di vista statistico tra i due segmenti. Ogni riga in questa tabella rappresenta una metrica differenziata, valutata in base al modo in cui si differenzia tra i vari segmenti. Un punteggio di differenza pari a 1 indica che è statisticamente significativo, mentre un punteggio di differenza pari a 0 indica che non esiste alcuna rilevanza statistica.

Questa visualizzazione è simile alle tabelle a forma libera in Analysis Workspace. Per un’analisi più approfondita su una metrica specifica, posiziona il cursore del mouse su un elemento e fai clic su “Crea elemento visivo”. Viene creata una nuova tabella per analizzare tale metrica specifica. Se una metrica è irrilevante per l’analisi, posiziona il cursore del mouse sulla riga e fai clic sulla X per rimuoverlo.

>[!NOTE]
>
>Le metriche aggiunte a questa tabella al termine del confronto dei segmenti non ricevono un punteggio di differenza.

![Metriche principali](assets/top-metrics.png)

### Metrica nel tempo per segmento

Sulla destra della tabella delle metriche si trova una visualizzazione collegata. Facendo clic su un elemento nella tabella a sinistra, questa visualizzazione viene aggiornata per mostrare la tendenza della metrica nel tempo.

![Linea metriche principali](assets/linked-viz.png)

### Dimensioni principali

Mostra gli elementi dimensionali più significativi dal punto di vista statistico in tutte le dimensioni. Ciascuna riga mostra la percentuale di ciascun segmento che possiede questo elemento della dimensione. Ad esempio, questa tabella potrebbe mostrare che il 100% dei visitatori nel “Segmento A” rientrava nella dimensione “Tipo browser: Google”, mentre solo il 19,6% del “Segmento B” rientrava in questa dimensione. Un punteggio di differenza pari a 1 indica che è statisticamente significativo, mentre un punteggio di differenza pari a 0 indica che non esiste alcuna rilevanza statistica.

Questa visualizzazione è simile alle tabelle a forma libera in Analysis Workspace. Per un’analisi più approfondita su un elemento della dimensione specifico, posiziona il cursore del mouse su una riga e fai clic su “Crea elemento visivo”. Viene creata una nuova tabella per analizzare tale elemento della dimensione. Se un elemento della dimensione è irrilevante per l’analisi, posiziona il cursore del mouse sulla riga e fai clic sulla X per rimuoverlo.

>[!NOTE]
>
>Gli elementi dimensionali aggiunti alla tabella al termine del confronto dei segmenti non ricevono un punteggio di differenza.

![Dimensioni principali](assets/top-dimension-item1.png)

### Elementi dimensione per segmento

Sulla destra della tabella delle dimensioni si trova una visualizzazione grafico a barre collegata. Mostra tutti i gli elementi dimensionali sotto forma di grafico a barre. Facendo clic su un elemento nella tabella a sinistra, la visualizzazione a destra viene aggiornata.

![Grafico a barre delle dimensioni principali](assets/top-dimension-item.png)

### Segmenti principali

Mostra quali altri segmenti (diversi dai due segmenti selezionati per il confronto) presentano una sovrapposizione statisticamente significativa. Ad esempio, questa tabella può mostrare che un terzo segmento, “Visitatori ripetuti”, si sovrappone notevolmente con il “Segmento A” ma non con il “Segmento B”. Un punteggio di differenza pari a 1 indica che è statisticamente significativo, mentre un punteggio di differenza pari a 0 indica che non esiste alcuna rilevanza statistica.

Questa visualizzazione è simile alle tabelle a forma libera in Analysis Workspace. Per un’analisi più approfondita su un segmento specifico, posiziona il cursore del mouse su un elemento e fai clic su “Crea elemento visivo”. Viene creata una nuova tabella per analizzare tale segmento specifico. Se un segmento è irrilevante per l’analisi, posiziona il cursore del mouse sulla riga e fai clic sulla X per rimuoverlo.

>[!NOTE]
>
>I segmenti aggiunti a questa tabella al termine del confronto dei segmenti non ricevono un punteggio di differenza.

![Segmenti principali](assets/top-segments.png)

### Sovrapposizione segmento

Sulla destra della tabella dei segmenti si trova una visualizzazione a diagramma di Venn collegata. Mostra il segmento più significativo dal punto di vista statistico applicato ai segmenti confrontati. Ad esempio, “Segmento A” + “Segmento statisticamente significativo” rispetto a “Segmento B” + “Segmento statisticamente significativo”. Facendo clic su una riga segmento nella tabella a sinistra, la visualizzazione a destra viene aggiornata.

![Diagramma di Venn dei segmenti principali](assets/segment-overlap.png)
