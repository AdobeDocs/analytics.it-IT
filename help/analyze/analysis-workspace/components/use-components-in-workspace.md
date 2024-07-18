---
description: Scopri come aggiungere componenti a un progetto in Analysis Workspace
title: Utilizzare i componenti in Analysis Workspace
feature: Workspace Basics
role: User, Admin
exl-id: fb56e794-67e3-4f85-960e-b90684300fa0
source-git-commit: 9fcebd7a8fb3a3d98eebef53a748c8ac585cbcd1
workflow-type: tm+mt
source-wordcount: '872'
ht-degree: 10%

---

# Utilizzare i componenti in Analysis Workspace

I componenti costituiscono i dati effettivi di qualsiasi progetto in Analysis Workspace. I componenti sono costituiti da dimensioni, metriche, segmenti e intervalli di date. Puoi aggiungere componenti a un progetto trascinandoli in visualizzazioni o pannelli.

Per informazioni generali sui tipi di componenti che è possibile aggiungere, vedere [Panoramica dei componenti](/help/analyze/analysis-workspace/components/analysis-workspace-components.md).

>[!TIP]
>
>Per informazioni su ciascun componente, seleziona l&#39;icona Info accanto al nome di un componente nella barra a sinistra di Analysis Workspace oppure fai riferimento alla [Guida ai componenti di Analytics](/help/components/home.md).

## Inizia ad aggiungere componenti a un progetto

1. [Crea un progetto in Analysis Workspace](/help/analyze/analysis-workspace/build-workspace-project/create-projects.md), se non lo hai già fatto.

1. [Aggiungi un pannello](/help/analyze/analysis-workspace/c-panels/panels.md) o [aggiungi una visualizzazione](/help/analyze/analysis-workspace/visualizations/freeform-analysis-visualizations.md#add-visualizations-to-a-panel) al progetto in Analysis Workspace.

   Se aggiungi un componente a un progetto vuoto, viene automaticamente creata una visualizzazione a forma libera.

1. Seleziona l’icona **[!UICONTROL Components]** nella barra a sinistra.

   ![](assets/build-components.png)

1. Scorri fino al componente da aggiungere oppure cercalo, quindi trascinalo su un pannello o su una visualizzazione all’interno del progetto.

1. (Facoltativo) Trascina un componente nella zona di rilascio del segmento nell’intestazione di un pannello.

   I segmenti si applicano a tutto il contenuto del pannello.

   Per informazioni su come utilizzare la zona di rilascio dei segmenti su un pannello per filtrare il pannello, vedi [Zona di rilascio](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Panoramica dei pannelli](/help/analyze/analysis-workspace/c-panels/panels.md).

   ![rilascia un segmento nella zona di rilascio](assets/segment-dropzone.png)

1. Per informazioni più dettagliate, continua con una delle sezioni seguenti, a seconda del tipo di componente che stai aggiungendo:

   * [Aggiungere dimensioni a un progetto](#add-dimensions-to-a-project)

   * [Aggiungere metriche a un progetto](#add-metrics-to-a-project)

   * [Aggiungere segmenti a un progetto](#add-segments-to-a-project)

   * [Aggiungere intervalli di date a un progetto](#add-date-ranges-to-a-project)

## Aggiungere dimensioni a un progetto

[Dimension](/help/components/dimensions/overview.md) sono variabili in Adobe Analytics che in genere contengono valori stringa. Le dimensioni comuni includono [Pagina](/help/components/dimensions/page.md), [Dominio di riferimento](/help/components/dimensions/referring-domain.md) o una [eVar](/help/components/dimensions/evar.md). Al contrario, le [metriche](/help/components/metrics/overview.md) contengono valori numerici che si legano a una dimensione. Un rapporto di base mostra righe di valori stringa (dimensione) rispetto a una colonna di valori numerici (metrica).

1. Inizia ad aggiungere una dimensione al progetto in Analysis Workspace, come descritto in [Inizia ad aggiungere componenti a un progetto](#begin-adding-components-to-a-project).

1. Scegliere uno dei metodi seguenti per aggiungere dimensioni e determinare il tipo di dati da analizzare:

   * Trascina una dimensione in una visualizzazione (ad esempio una tabella a forma libera) in Analysis Workspace.

     ![Aggiungere dimensioni a un progetto](assets/add-dimensions.png)

   * Trascina una o più dimensioni dalla barra a sinistra alla zona di rilascio dei segmenti per creare un segmento ad hoc, come descritto in [Aggiungi segmenti a un progetto](#add-segments-to-a-project).

     ![rilascia un segmento nella zona di rilascio](assets/segment-dropzone.png)

1. (Facoltativo) Puoi suddividere dimensioni ed elementi dimensionali in Analysis Workspace con altri componenti.

   Per ulteriori informazioni, vedere [Suddividere dimensioni](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md).

Per ulteriori informazioni sull&#39;utilizzo delle dimensioni in Analysis Workspace, vedere [Anteprima dimensioni](/help/analyze/analysis-workspace/components/dimensions/view-dimensions.md), [Suddivisione dimensioni](/help/analyze/analysis-workspace/components/dimensions/t-breakdown-fa.md) e [Dimensioni suddivise in base al tempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md).

## Aggiungere metriche a un progetto

[Le metriche](/help/analyze/analysis-workspace/components/apply-create-metrics.md) ti consentono di quantificare i punti dati in Analysis Workspace. Sono più comunemente utilizzate come colonne in una visualizzazione e legate alle dimensioni.

Per aggiungere una metrica a un progetto in Analysis Workspace:

1. Inizia ad aggiungere una metrica al progetto in Analysis Workspace, come descritto in [Inizia ad aggiungere componenti a un progetto](#begin-adding-components-to-a-project).

1. Per aggiungere una metrica in Analysis Workspace, scegli uno dei seguenti metodi:

   * Trascina una metrica nella zona di rilascio della metrica in una tabella a forma libera vuota per visualizzare la tendenza della metrica nel periodo di date del progetto.

     ![Aggiungere una metrica a un progetto](assets/add-metrics.png)

   * Trascina una metrica quando è presente una dimensione per visualizzarla rispetto a ciascun elemento dimensione.

   * Trascina una metrica sopra un’intestazione di metrica esistente per sostituirla.

   * Trascina una metrica accanto a un’intestazione per vedere entrambe le metriche una accanto all’altra.

Per ulteriori informazioni sull&#39;utilizzo delle metriche in Analysis Workspace, vedere [Metriche](/help/analyze/analysis-workspace/components/apply-create-metrics.md).

## Aggiungere segmenti a un progetto

[I segmenti](/help/components/segmentation/seg-overview.md) ti consentono di identificare sottoinsiemi di visitatori in base a caratteristiche o interazioni specifiche.

Puoi utilizzare i segmenti in Analysis Workspace in uno dei seguenti modi:

### Aggiungere segmenti a un pannello

Quando aggiungi segmenti a un pannello, i segmenti vengono applicati a tutto il contenuto al suo interno.

Per informazioni su come utilizzare la zona di rilascio dei segmenti su un pannello per filtrare il pannello, vedi [Zona di rilascio](/help/analyze/analysis-workspace/c-panels/panels.md#drop-zone) in [Panoramica dei pannelli](/help/analyze/analysis-workspace/c-panels/panels.md).

### Aggiungere segmenti a una colonna di una tabella a forma libera

Quando aggiungi segmenti a una colonna di una tabella a forma libera, i segmenti si applicano a tutto il contenuto della colonna della tabella.

### Utilizzare i segmenti durante la creazione di metriche calcolate

Nel generatore di metriche calcolate, puoi applicare segmenti all’interno della definizione della metrica.

Per ulteriori informazioni, vedere [Metriche segmentate](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/metrics-with-segments.md).

## Aggiungere intervalli di date a un progetto

[Gli intervalli di date](/help/analyze/analysis-workspace/components/calendar-date-ranges/custom-date-ranges.md) determinano l&#39;intervallo di tempo di reporting in Analysis Workspace e possono essere applicati a uno o più pannelli all&#39;interno di un progetto.

Per impostazione predefinita, ogni pannello include un intervallo di date. Esistono diversi modi per aggiornare un intervallo di date per un pannello. Un modo per aggiornare un intervallo di date per un pannello in Analysis Workspace consiste nel trascinare un componente intervallo di date dalla barra a sinistra:

1. Inizia ad aggiungere un intervallo di date al progetto in Analysis Workspace, come descritto in [Inizia ad aggiungere componenti a un progetto](#begin-adding-components-to-a-project).

1. Trascina un intervallo di date dalla barra a sinistra all’intervallo di date corrente nella parte superiore destra del pannello.

   ![rilascia un intervallo di date](assets/daterange-drop.png)

Per ulteriori informazioni sull&#39;utilizzo dei calendari e degli intervalli di date in Analysis Workspace, vedere [Panoramica del calendario e degli intervalli di date](/help/analyze/analysis-workspace/components/calendar-date-ranges/calendar.md).
