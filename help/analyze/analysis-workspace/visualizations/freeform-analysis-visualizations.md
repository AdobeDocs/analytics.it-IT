---
description: Rappresenta visivamente i dati con le visualizzazioni.
keywords: Analysis Workspace
title: Panoramica delle visualizzazioni
feature: Visualizzazioni
role: Business Practices, amministratore
translation-type: tm+mt
source-git-commit: 894ee7a8f761f7aa2590e06708be82e7ecfa3f6d
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 42%

---


# Panoramica delle visualizzazioni

Workspace offre diverse visualizzazioni che consentono di generare rappresentazioni visive dei dati, ad esempio grafici a barre, grafici ad anello, istogrammi, grafici a linee, mappe, grafici a dispersione e altri. La maggior parte dei tipi di visualizzazione ti sarà familiare se utilizzi Adobe Analytics. Tuttavia, Analysis Workspace consente di configurare le impostazioni di visualizzazione e offre molti tipi di visualizzazioni nuovi o unici, con funzionalità interattive.

Puoi accedere alle visualizzazioni dall’icona in alto a sinistra in Workspace, da un [pannello vuoto](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/blank-panel.html?lang=it) o dal menu di scelta rapida nel flusso di lavoro.

![](assets/viz-rail.png)

In Analysis Workspace sono disponibili i seguenti tipi di visualizzazione:

| Nome della visualizzazione | Descrizione |
| --- | --- |
| [Superfici](/help/analyze/analysis-workspace/visualizations/area.md) | Come un grafico a linee, ma con un&#39;area colorata sotto la linea. Un grafico a superficie è utile quando si hanno diverse metriche e si desidera visualizzare l’area di intersezione di due o più metriche. |
| [Barre](/help/analyze/analysis-workspace/visualizations/bar.md) | Mostra barre verticali che rappresentano diversi valori su una o più metriche. |
| [Grafico bullet](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) | Mostra come un valore desiderato si confronta con altre gamme di prestazioni (obiettivi). |
| [Tabella coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/cohort-analysis.md) | Una *`cohort`* è un gruppo di persone che condividono le stesse caratteristiche per un determinato periodo di tempo. L’analisi per coorte è utile per le analisi di fidelizzazione, abbandono o latenza. |
| [Anello](/help/analyze/analysis-workspace/visualizations/donut.md) | Questa visualizzazione è simile al grafico a torta e presenta i dati come parti o segmenti di un intero. |
| [Abbandono](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) | I rapporti di abbandono mostrano dove i visitatori hanno lasciato (abbandonato) una sequenza di pagine predefinite e dove hanno proseguito. Può essere impostato su sequenze finali o esatte |
| [Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) | Mostra i percorsi esatti dei clienti attraverso i tuoi siti web e le tue app. |
| [Tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) | Una tabella a forma libera non è semplicemente una tabella di dati, ma è soprattutto una visualizzazione interattiva. È la base per l’analisi dei dati in Workspace. |
| [Istogramma](/help/analyze/analysis-workspace/visualizations/histogram.md) | Un istogramma esegue il bucket di visitatori, visite o hit in blocchi in base a un volume di metrica. |
| [Barre orizzontali](/help/analyze/analysis-workspace/visualizations/horizontal-bar.md) | Mostra barre orizzontali che rappresentano diversi valori su una o più metriche. |
| [Linee](/help/analyze/analysis-workspace/visualizations/line.md) | Rappresenta le metriche utilizzando una linea per mostrare il cambiamento dei valori nel corso di un intervallo di tempo. Un grafico a linee utilizza il tempo lungo l&#39;asse x. |
| [Mappa](/help/analyze/analysis-workspace/visualizations/map-visualization.md) | Consente di creare una mappa visiva di qualsiasi metrica (comprese le metriche calcolate). |
| [Grafico a dispersione](/help/analyze/analysis-workspace/visualizations/scatterplot.md) | Mostra la relazione tra gli elementi dimensionali fino a tre metriche. |
| [Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | Mostra la cella selezionata come 1 numero grande. |
| [Variazione di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) | Mostra la variazione tra le celle selezionate come 1 numero/percentuale grande. |
| [Testo](/help/analyze/analysis-workspace/visualizations/text.md) | Consente di aggiungere testo definito dall’utente al progetto Workspace. Utile per aggiungere ulteriore contesto alle analisi e alle informazioni, oltre a sfruttare le descrizioni di pannelli e visualizzazioni |
| [Mappa ad albero](/help/analyze/analysis-workspace/visualizations/treemap.md) | Visualizza i dati gerarchici (con struttura ad albero) come un insieme di rettangoli nidificati. |
| [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) | Utilizza i cerchi per rappresentare la sovrapposizione metrica fino a 3 segmenti. |

## Impostazioni {#settings}

Ogni visualizzazione ha le proprie impostazioni che è possibile gestire. Per accedere a [!UICONTROL Visualization Settings], fai clic sull&#39;icona a forma di ingranaggio [!UICONTROL Visualization Settings].

![](assets/settings.png)

| Impostazione | Descrizione |
| --- | --- |
| Tipo di visualizzazione | Modifica il tipo di elemento visivo utilizzato per rappresentare i dati. |
| Granularity (Granularità) | Per le visualizzazioni con tendenze, puoi modificare la granularità temporale (giorno, settimana, mese, ecc.) da questo menu a discesa. Questa modifica si applica anche alla tabella dell’origine dati. |
| Percentuali | Visualizza i valori in percentuale. |
| Sovrapposizione 100% | Questa impostazione per le visualizzazioni Superfici sovrapposte, Barre sovrapposte o Barre orizzontali sovrapposte converte il grafico in una visualizzazione con sovrapposizione 100%. Esempio: ![Sovrapposizione 100%](assets/stacked_100_percent.png) |
| Visualizzazione legenda | Consente di nascondere il testo della legenda dettagliato per la visualizzazione Numero di riepilogo/Variazione di riepilogo. |
| Limite massimo elementi | Consente di limitare il numero di elementi presentati in una visualizzazione. |
| Ancoraggio asse Y su zero | Se tutti i valori rappresentati sul grafico sono uniformemente al di sopra dello zero, per impostazione predefinita la parte inferiore dell’asse y sarà NON-ZERO. Attivando questa opzione, l’asse y verrà forzata sullo zero (e il grafico verrà ridisegnato). |
| Normalizzazione | Forza le metriche ad adeguarsi alle proporzioni. Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| Visualizza asse doppia | Applicabile solo in presenza di due metriche. È possibile avere un asse y a sinistra (per una metrica) e un altro a destra (per l’altra metrica). Questa funzione è utile quando le metriche tracciate hanno dimensioni molto diverse. |
| Mostra anomalie | Migliora i grafici a linee e le tabelle a forma libera tramite la visualizzazione del rilevamento delle anomalie. Il rilevamento delle anomalie nelle visualizzazioni a linee include un valore previsto (linea tratteggiata) e un intervallo previsto (banda ombreggiata). |

## Legend (Legenda){#legend}

Una legenda di visualizzazione consente di correlare la data in una tabella sorgente alle serie tracciate nella visualizzazione. La legenda è interattiva: puoi fare clic su un elemento della legenda per mostrare o nascondere una serie nella visualizzazione. È utile se desideri semplificare i dati visualizzati.

Inoltre, puoi rinominare le etichette delle legende per facilitarti la lettura dei grafici. Nota: la modifica della legenda **non** si applica a: Visualizzazioni mappa ad albero, Bullet, Variazione/Numero di riepilogo, Testo, Forma libera, Istogramma, Coorte o Flusso.

Per modificare un’etichetta di legenda:

1. Fai clic su una delle etichette della legenda.
1. Fai clic su **[!UICONTROL Edit Label]** (Modifica etichetta).

   ![](assets/edit-label.png)

1. Inserisci il nuovo testo dell’etichetta.
1. Fai clic su **[!UICONTROL Enter]** per salvare.

Per approfondire, utilizza questo [collegamento a un video](https://docs.adobe.com/content/help/en/analytics-learn/tutorials/analysis-workspace/visualizations/series-label-editing.html) sull’argomento.

## Menu di scelta rapida {#right-click}

Per aggiungere altre funzionalità a una visualizzazione, fai clic con il pulsante destro del mouse sull’intestazione della visualizzazione. Le impostazioni variano a seconda della visualizzazione. Alcune delle impostazioni disponibili sono:

![](assets/right-click.png)

| Impostazione | Descrizione |
| --- | --- |
| Inserisci pannello copiato/visualizzazione | Consente di incollare (&quot;inserire&quot;) un pannello o una visualizzazione copiati in un’altra posizione all’interno del progetto o in un progetto completamente diverso. |
| Copia visualizzazione | Consente di fare clic con il pulsante destro del mouse e copiare una visualizzazione in modo da poterla inserire in un’altra posizione all’interno del progetto o in un progetto completamente diverso. |
| [Download di elementi come CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-items) | Scarica come CSV fino a 50.000 elementi dimensionali per la dimensione selezionata. |
| [Scaricare dati come CSV](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/curate-share/download-send.html?#download-data) | Scarica l’origine dati di visualizzazione come CSV. |
| Duplica visualizzazione | Crea una copia della visualizzazione corrente, che potrai quindi modificare. |
| Modifica descrizione | Aggiungi (o modifica) una descrizione di testo per la visualizzazione. |
| Ottieni collegamento visualizzazione | Consente di indirizzare un utente a una visualizzazione specifica all’interno di un progetto. Quando fai clic sul collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato all’esatta visualizzazione collegata. |
| Ricomincia | (Per Flusso, Venn, Istogramma) Elimina la configurazione della visualizzazione corrente in modo da poterla riconfigurare da zero. |

## Icona “Crea elemento visivo” {#quick-viz}

Se non sai quale visualizzazione scegliere, fai clic sull’icona **[!UICONTROL Create Visual]** in una delle righe della tabella (disponibile al passaggio del mouse). Questo è il modo più veloce per aggiungere una visualizzazione. Facendo clic su di essa, Analysis Workspace cerca di fare una stima ragionata per individuare la visualizzazione più idonea ai tuoi dati. Ad esempio, se hai selezionato 1 riga, verrà creato un grafico a linee con tendenze. Se sono state selezionate 3 righe di segmento, verrà creato un diagramma di Venn.

![](assets/quick-viz.png)
