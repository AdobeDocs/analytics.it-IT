---
description: Ulteriori informazioni sulle visualizzazioni e sulle impostazioni di visualizzazione in Analysis Workspace.
keywords: Analysis Workspace
title: Panoramica delle visualizzazioni
translation-type: ht
source-git-commit: 6eda9e3e5bd450213253a8181042c24c318c0300

---


# Panoramica delle visualizzazioni

Workspace offre diverse visualizzazioni che consentono di generare rappresentazioni visive dei dati, ad esempio grafici a barre, grafici ad anello, istogrammi, grafici a linee, mappe, grafici a dispersione e altri. Ogni visualizzazione ha le proprie impostazioni che è possibile gestire. Fai clic sul nome della visualizzazione per ulteriori informazioni.

Video su YouTube: [Tipi di visualizzazione in Analysis Workspace](https://www.youtube.com/watch?v=b1zLEywRa6w&amp;index=39&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (2:57)

| Nome della visualizzazione | Descrizione |
|---|---|
| [Superfici](/help/analyze/analysis-workspace/visualizations/area.md) | È simile a un grafico a linee ma presenta una superficie colorata al di sotto della linea. Un grafico a superficie è utile quando si hanno diverse metriche e si desidera visualizzare l’area di intersezione di due o più metriche. |
| [Barre](/help/analyze/analysis-workspace/visualizations/bar.md) | Mostra barre verticali che rappresentano diversi valori su una o più metriche. |
| [Grafico bullet](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | Mostra come un valore desiderato si confronta con altre gamme di prestazioni (obiettivi). |
| [Tabella coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Un *`cohort`* è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. Lo strumento di analisi per coorte è utile, ad esempio, quando si vuole comprendere in che modo una coorte si relaziona con un marchio. Permette di individuare facilmente cambiamenti nelle tendenze e reagire di conseguenza. |
| [Anello](/help/analyze/analysis-workspace/visualizations/donut.md) | Questa visualizzazione è simile al grafico a torta e presenta i dati come parti o segmenti di un intero. |
| [Abbandono](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | I rapporti di abbandono mostrano dove i visitatori hanno lasciato (abbandonato) una sequenza di pagine predefinite e dove hanno proseguito. |
| [Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | Mostra i percorsi dei clienti attraverso i siti web e le app. |
| [Tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table.md) | Una tabella a forma libera non è semplicemente una tabella di dati, ma è soprattutto una visualizzazione interattiva. |
| [Istogramma](/help/analyze/analysis-workspace/visualizations/histogram.md) | Un istogramma è simile a un grafico a barre, ma con i numeri raggruppati in intervalli. |
| [Barre orizzontali](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | Mostra barre orizzontali che rappresentano diversi valori su una o più metriche. |
| [Linee](/help/analyze/analysis-workspace/visualizations/line.md) | Rappresenta le metriche utilizzando una linea per mostrare il cambiamento dei valori nel corso di un intervallo di tempo. Un grafico a linee può essere usato solo con una dimensione temporale. |
| [Mappa](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | Consente di creare una mappa visiva di qualsiasi metrica (comprese le metriche calcolate). |
| [Grafico a dispersione](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | Mostra la relazione tra i valori di dimensione fino a tre metriche. |
| [Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | A seconda della cella selezionata, questa visualizzazione mostra i totali e i riepiloghi. |
| [Variazione di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | A seconda delle celle selezionate, questa visualizzazione confronta le celle tra loro. |
| [Testo](/help/analyze/analysis-workspace/visualizations/text.md) | Consente di aggiungere testo definito dall’utente al progetto Workspace. |
| [Mappa ad albero](/help/analyze/analysis-workspace/visualizations/treemap.md) | Visualizza i dati gerarchici (con struttura ad albero) come un insieme di rettangoli nidificati. |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) | Consente di trascinare fino a 3 segmenti (dai Componenti) e una metrica per costruire un diagramma di Venn. |

## Pannello Visualizzazioni {#section_DC07F032FBEF4046A40F7B95C28DA018}

Per visualizzare il pannello Visualizzazioni, fai clic su **[!UICONTROL Visualizations]** (Visualizzazioni) nel pannello laterale.

![Risultato passaggio](assets/visualizations.png)

Se usi già Adobe Analytics, la maggior parte dei tipi di visualizzazione (come ad area, a barre, a torta e a linee) ti sarà familiare. Tuttavia, Analysis Workspace consente di configurare le impostazioni di visualizzazione e offre molti tipi di visualizzazioni nuovi o unici, con funzionalità interattive.

## Impostazioni visualizzazione {#section_D3BB5042A92245D8BF6BCF072C66624B}

Per accedere a [!UICONTROL Visualization Settings] (Impostazioni visualizzazione), trascina una visualizzazione sul [!UICONTROL Freeform Panel] (Pannello a forma libera), quindi fai clic sull’icona [!UICONTROL Visualization Settings] (Impostazioni visualizzazione) a forma di ingranaggio.

>[!IMPORTANT]
>
>Le impostazioni disponibili dipendono dal tipo di visualizzazione. Alcune impostazioni non sono applicabili ad alcune visualizzazioni. Inoltre, alcune impostazioni avanzate sono disponibili **solo** per specifiche visualizzazioni, ad esempio le [impostazioni Istogramma](/help/analyze/analysis-workspace/visualizations/histogram.md#section_09D774C584864D4CA6B5672DC2927477).

![](assets/visualization_settings.png)

| Impostazione | Descrizione |
|--- |--- |
| Percentuali | Visualizza i valori in percentuale. |
| Sovrapposizione 100% | Questa impostazione – applicata a visualizzazioni Superfici sovrapposte, Barre sovrapposte o Barre orizzontali sovrapposte – converte il grafico in una visualizzazione con sovrapposizione 100%. Esempio: ![](assets/stacked_100_percent.png) |
| Visualizzazione legenda | Consente di nascondere il testo di dettagli del filtro per la visualizzazione Numero di riepilogo/Variazione di riepilogo. |
| Limite massimo elementi | Consente di limitare il numero di elementi presentati in una visualizzazione. |
| Ancoraggio asse Y su zero | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |
| Normalizzazione | Forza le metriche ad adeguarsi alle proporzioni. |
| Visualizza asse doppia | Applicabile solo in presenza di due metriche. È possibile avere un asse y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). |
| Mostra anomalie | Ottimizza i grafici a linee e le tabelle a forma libera per la visualizzazione delle anomalie nei dati. |

## Icona “Crea elemento visivo” {#section_9C11D9DEDC42413AA53E69A71A509DFC}

Se non sai quale visualizzazione scegliere, fai clic sull’icona **[!UICONTROL Create Visual]** (Crea elemento visivo) in una delle righe della tabella. Questa icona appare quando il mouse viene passato sulla riga di tabella. Facendo clic su di essa, Analysis Workspace cerca di fare una stima ragionata per individuare la visualizzazione più idonea ai tuoi dati. Ad esempio, selezionando fino a 3 segmenti, si crea un diagramma di Venn. Per più di 3 segmenti, crea un grafico a barre. Per altri tipi di dati, potrebbe creare un grafico a linee, ecc.

![](assets/create-visual.png)

## Menu di scelta rapida visualizzazione/pannello {#section_05B7914D4C9E443F97E2BFFDEC70240C}

Per accedere alle impostazioni contestuali disponibili per un grafico, fai clic con il pulsante destro del mouse accanto all’intestazione di una visualizzazione o di un pannello. Saranno disponibili tutte o alcune delle seguenti impostazioni:

![](assets/right-click_menu.png)

| Impostazione | Descrizione |
|--- |--- |
| Inserisci visualizzazione copiata/pannello copiato | Consente di incollare (inserire) l’elemento copiato in un’altra posizione all’interno del progetto o in un progetto completamente diverso. |
| Copia visualizzazione/pannello | Consente di fare clic con il pulsante destro del mouse e copiare una visualizzazione o un pannello. |
| Duplica visualizzazione/pannello | Crea una copia della visualizzazione corrente, che potrai quindi modificare. |
| Comprimi tutti i pannelli | Comprime tutti i pannelli del progetto. |
| Comprimi tutte le visualizzazioni nel pannello | Comprime tutte le visualizzazioni nel pannello di progetto corrente. |
| Espandi tutti i pannelli | Espande tutti i pannelli del progetto. |
| Espandi tutte le visualizzazioni nel pannello | Espande tutte le visualizzazioni nel pannello di progetto corrente. |
| Modifica descrizione | Aggiungi (o modifica) un testo descrittivo per la visualizzazione o il pannello. La descrizione viene visualizzata in Progetto > Informazioni e impostazioni progetto. |
| Ottieni collegamento pannello | Consente di indirizzare un utente a uno specifico pannello in un progetto. |
| Ottieni collegamento visualizzazione | Consente di copiare e condividere il collegamento per far sì che altri utenti possano accedere direttamente a questa visualizzazione. Gli utenti dovranno effettuare l’accesso. |
| Ricomincia | (Per Flusso, Venn, Istogramma) Elimina la configurazione della visualizzazione corrente e apre un nuovo pannello dove la puoi riconfigurare. |

## Modifica delle etichette delle legende {#section_94F1988CB4B9434BA1D9C6034062C3DE}

È possibile modificare i nomi delle serie nelle legende delle visualizzazioni (Abbandono, Superfici, Superfici sovrapposte, Barre, Barre sovrapposte, Anello, Istogramma, Barre orizzontali, Barre orizzontali sovrapposte, Linee, Dispersione e Venn) per facilitare la lettura dei grafici.

La modifica della legenda **non** è disponibile per le visualizzazioni Mappa ad albero, Bullet, Variazione di riepilogo o Numero di riepilogo, Testo, Forma libera, Istogramma, Coorte o Flusso.

Ad esempio, per modificare un’etichetta di legenda in un grafico a linee:

1. Fai clic su una delle etichette della legenda.
1. Fai clic su **[!UICONTROL Edit Label]** (Modifica etichetta).

   ![](assets/edit-label.png)

1. Inserisci il nuovo testo dell’etichetta.
1. Fai clic su **[!UICONTROL Enter]** per salvare.

Per approfondire, utilizza questo [collegamento a un video](https://www.youtube.com/watch?v=mry3vDrTml0&amp;index=61&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) sull’argomento.
