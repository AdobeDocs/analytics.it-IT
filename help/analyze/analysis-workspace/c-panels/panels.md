---
description: Scopri come utilizzare i pannelli in Analysis Workspace per organizzare i rapporti, filtrare o suddividere i dati e definire l’intervallo di dati.
title: Panoramica Dei Pannelli In Analysis Workspace
feature: Panels
role: User, Admin
exl-id: dd1a3c40-8b5b-47dd-86d9-da766575ee46
source-git-commit: c86e1ef4a93591e7623fe5a9f2f9d92529773516
workflow-type: tm+mt
source-wordcount: '2566'
ht-degree: 35%

---

# Panoramica dei pannelli

Un [!UICONTROL panel] è una raccolta di tabelle e visualizzazioni. Puoi accedere ai pannelli dall’icona in alto a sinistra in Workspace o da un [pannello vuoto](/help/analyze/analysis-workspace/c-panels/blank-panel.md). I pannelli sono utili per organizzare i progetti in base a specifici periodi di tempo, suite di rapporti o casi di utilizzo di analisi.

## Tipi di pannello

In Analysis Workspace sono disponibili i seguenti tipi di pannello per [!UICONTROL Adobe Analytics]:

| Nome pannello | Descrizione |
| --- | --- |
| [Pannello vuoto](/help/analyze/analysis-workspace/c-panels/blank-panel.md) | Per iniziare a eseguire analisi, scegli tra i pannelli e le visualizzazioni disponibili. |
| [Attribuzione](attribution.md) | Confronta e visualizza rapidamente più modelli di attribuzione utilizzando qualsiasi dimensione e metrica di conversione. |
| [Analytics for Target](a4t-panel.md) | Analizza le attività ed esperienze Target in Analysis Workspace. |
| [A forma libera](freeform-panel.md) | Esegui confronti illimitati e raggruppamenti, quindi aggiungi visualizzazioni per raccontare una storia ricca di dati. |
| [Pubblico medio per minuto del file multimediale](average-minute-audience-panel.md) | Analizza il pubblico medio per minuto di una parte del contenuto specifico o in un periodo di tempo personalizzato. |
| [Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md) | Analizza i visualizzatori simultanei nel tempo, con dettagli sui picchi di concorrenza e con la possibilità di suddividerli e confrontarli. |
| [Tempo trascorso su contenuti multimediali](/help/analyze/analysis-workspace/c-panels/media-playback-time-spent.md) | L’analisi del tempo di riproduzione trascorso consente di comprendere dove si è verificato il picco di concorrenza o dove si è verificato il calo. |
| [Elemento successivo o precedente](next-previous.md) | Mostra le pagine successive o precedenti a cui si accede. |
| [Quick Insights](quickinsight.md) | Crea rapidamente una tabella a forma libera e una relativa visualizzazione per analizzare e individuare più rapidamente le informazioni. |
| [Riepilogo pagina](page-summary.md) | Esplora le statistiche chiave su pagine specifiche. |
| [Confronto segmenti](/help/analyze/analysis-workspace/c-panels/c-segment-comparison/segment-comparison.md) | Confronta rapidamente due segmenti su tutti i punti dati per trovare automaticamente differenze rilevanti. |


I pannelli [!UICONTROL Quick insights], [!UICONTROL Blank] e [!UICONTROL Freeform] sono ideali per iniziare con le attività di analisi, mentre [!UICONTROL Attribution] si presta ad analisi più avanzate. Nella parte inferiore dell’area di lavoro è disponibile un ![AddCircle](/help/assets/icons/AddCircle.svg), che consente di aggiungere pannelli vuoti in qualsiasi momento.

Il pannello iniziale predefinito è [!UICONTROL Freeform], ma puoi impostare come predefinito il [Pannello vuoto](/help/analyze/analysis-workspace/c-panels/blank-panel.md) o [Quick Insights](/help/analyze/analysis-workspace/c-panels/quickinsight.md). Consulta [Preferenze Progetti e Analisi](/help/analyze/analysis-workspace/user-preferences.md#projects--analyses-preferences).


## Creare un pannello

Per creare un pannello:

* Trascina un pannello dal pannello a sinistra **[!UICONTROL Panels]** nell’area di lavoro.
* Seleziona un pannello dal [Pannello vuoto](blank-panel.md).
* Utilizza il menu **[!UICONTROL Insert]** in Workspace e seleziona il tuo pannello. In alternativa, puoi utilizzare una delle [scelte rapide da tastiera](../build-workspace-project/fa-shortcut-keys.md) per inserire un pannello.

  ![Creare un pannello](assets/create-panel.png)

Puoi:

* Seleziona ![AddCircle](/help/assets/icons/AddCircle.svg) **all’interno** di un pannello per aggiungere un’altra visualizzazione. Viene visualizzato un riquadro a comparsa che consente di selezionare una visualizzazione.

  ![Popup che mostra le visualizzazioni possibili](assets/blank-panel.png)

  | Seleziona... | Per creare una visualizzazione... |
  |---|---|
  | ![Tabella](/help/assets/icons/Table.svg) | [Tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table.md) |
  | ![Linee](/help/assets/icons/GraphTrend.svg) | [Linee](/help/analyze/analysis-workspace/visualizations/line.md) |
  | ![GraphBarVertical](/help/assets/icons/GraphBarVertical.svg) | [Barre](/help/analyze/analysis-workspace/visualizations/bar.md) |
  | ![123](/help/assets/icons/123.svg) | [Numero di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Testo](/help/assets/icons/Text.svg) | [Testo](/help/analyze/analysis-workspace/visualizations/text.md) |
  | ![Funnel di conversione](/help/assets/icons/ConversionFunnel.svg) | [Fallout](/help/analyze/analysis-workspace/visualizations/fallout/fallout-flow.md) |
  | ![Flusso di lavoro](/help/assets/icons/GraphPathing.svg) | [Flusso](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md) |
  | ![Area grafica sovrapposta](/help/assets/icons/GraphAreaStacked.svg) | [Area sovrapposta](/help/analyze/analysis-workspace/visualizations/area.md) |
  | ![Testo numerato](/help/assets/icons/TextNumbered.svg) | [Tabella coorte](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md) |
  | ![Grafico bullet](/help/assets/icons/GraphBullet.svg) | [Bullet](/help/analyze/analysis-workspace/visualizations/bullet-graph.md) |
  | ![Grafico ad anello](/help/assets/icons/GraphDonut.svg) | [Anello](/help/analyze/analysis-workspace/visualizations/donut.md) |
  | ![Sposta verso l’alto o il basso](/help/assets/icons/MoveUpDown.svg) | [Variazione di riepilogo](/help/analyze/analysis-workspace/visualizations/summary-number-change.md) |
  | ![Istogramma](/help/assets/icons/Histogram.svg) | [Istogramma](/help/analyze/analysis-workspace/visualizations/histogram.md) |
  | ![Grafico a dispersione](/help/assets/icons/GraphScatter.svg) | [A dispersione](/help/analyze/analysis-workspace/visualizations/scatterplot.md) |
  | ![Tipo](/help/assets/icons/TwoDots.svg) | [Venn](/help/analyze/analysis-workspace/visualizations/venn.md) |
  | ![Grafico ad albero](/help/assets/icons/GraphTree.svg) | [Mappa ad albero](/help/analyze/analysis-workspace/visualizations/treemap.md) |

* Seleziona ![Aggiungi cerchio](/help/assets/icons/AddCircle.svg) **all&#39;esterno** dell’ultimo pannello nell’area di lavoro per aggiungere un altro [pannello vuoto](blank-panel.md).


## Gestire un pannello

Puoi gestire un pannello nei modi seguenti:

![Gestire un pannello](assets/manage-panel.png)

* Per comprimere un pannello, seleziona ![ChevronDown](/help/assets/icons/ChevronDown.svg).
* Per visualizzare un pannello compresso, seleziona ![ChevronLeft](/help/assets/icons/ChevronLeft.svg).
* Per eliminare un pannello, selezionare ![CrossSize200](/help/assets/icons/CrossSize200.svg). Per annullare, selezionare **[!UICONTROL Edit]** > **[!UICONTROL Undo]** (**[!UICONTROL *cmd *+*z *]**|**[!UICONTROL * ctrl *+* z *]**).
* Per spostare un pannello, trascina e rilascia il pannello ogni volta che è visibile un ![Sposta](/help/assets/icons/Move.svg) (in genere quando passi il cursore sull&#39;intestazione).


## Suite di rapporti

Ogni pannello è associato a una [suite di rapporti](/help/admin/tools/manage-rs/report-suites-admin.md), identificata da ![Dati](/help/assets/icons/Data.svg) **[!UICONTROL *nome della suite di rapporti *]**nel menu a discesa in alto a destra del pannello.

Quando crei un nuovo pannello, la suite di rapporti predefinita si basa sulla suite di rapporti dell’ultimo pannello su cui hai lavorato nel progetto Analysis Workspace.

All&#39;interno di un progetto, puoi utilizzare una o [molte suite di rapporti](/help/analyze/analysis-workspace/build-workspace-project/multiple-report-suites.md) a seconda dei casi di utilizzo dell&#39;analisi.

L’elenco delle suite di rapporti è ordinato in base alla rilevanza, che Adobe definisce in base a quanto recentemente e con quale frequenza l’utente corrente ha utilizzato la suite. E con quale frequenza la suite viene utilizzata all’interno dell’organizzazione.

![Menu a discesa della suite di rapporti in un pannello](assets/panel-report-suite.png)

>[!IMPORTANT]
>
>La suite di rapporti selezionata determina le dimensioni, le metriche e i segmenti disponibili per la creazione di visualizzazioni in un pannello.
>
>
>Quando cambi suite di rapporti per un pannello, alcuni componenti potrebbero non essere disponibili in quella nuova suite di rapporti. Questa modifica può impedire il corretto rendering della visualizzazione. Potresti visualizzare avvisi come:
>
>* Questo pannello contiene componenti non abilitati nella suite di rapporti selezionata. Modifica la suite di rapporti o abilita i componenti richiesti nella suite di rapporti.
>* Impossibile eseguire il rendering della visualizzazione: controlla le colonne e le righe per assicurarti che contengano componenti validi.
>

## Calendario

Il calendario del pannello controlla l’intervallo della date di reporting per tabelle e visualizzazioni all’interno di un pannello.

>[!NOTE]
>
>Se un componente Intervallo di date del ![Calendario](/help/assets/icons/Calendar.svg) viene utilizzato all’interno di una visualizzazione o di un pannello (ad esempio, come segmento), tale componente sostituisce il calendario del pannello.
>


![Finestra del calendario che mostra l’intervallo di date selezionato.](assets/panel-calendar.png)

1. Seleziona un intervallo di date selezionando prima la data di inizio e quindi la data di fine.
In alternativa, puoi selezionare **[!UICONTROL Preset]** dal menu a discesa [!UICONTROL *Seleziona un predefinito*].

1. Facoltativamente, seleziona **[!UICONTROL Show advanced settings]** per:

   * Specificare **[!UICONTROL Start time]** e **[!UICONTROL End time]** diversi da `12:00 AM` (`0:00`) e `11:59 PM` (`23:59`) predefiniti. Gli orari di fine includono sempre 59 secondi. Per un intervallo di date che si estende su più giorni, l’ora di inizio si applica al primo giorno dell’intervallo di date e l’ora di fine si applica all’ultimo giorno dell’intervallo di date. Utilizza **[!UICONTROL (Reset time values)]** per ripristinare le impostazioni predefinite dell’ora di inizio e di fine.
   * **[!UICONTROL Make date range components relative to panel calendar]**. Se l’opzione è disattivata, i componenti dell’intervallo di date utilizzati nel pannello sono relativi all’ora corrente. Se questa opzione è abilitata, i componenti dell’intervallo di date utilizzati nel pannello sono relativi al calendario del pannello.
   * **[!UICONTROL Use rolling dates]**. Se abilitati, gli intervalli di date predefiniti come **[!UICONTROL Last 7 full days]** vengono aggiornati in modo dinamico in base all&#39;avanzamento della data e dell&#39;ora corrente. Se disattivate, tali predefiniti non vengono aggiornati una volta applicati.

     ![Date continue](assets/calendar-rolling.png)

     È possibile selezionare il testo tra parentesi (ad esempio **[!UICONTROL fixed start - rolling daily]**) per estendere il pannello e specificare i dettagli per **[!UICONTROL Start]** e **[!UICONTROL End]**.

      1. Seleziona **[!UICONTROL Start of]**, **[!UICONTROL End of]**, or **[!UICONTROL Fixed day]**.
      1. Dopo aver selezionato **[!UICONTROL Start of]** o **[!UICONTROL End of]**, è possibile creare un’espressione completa. Ad esempio: **[!UICONTROL End of]** **[!UICONTROL current year]** **[!UICONTROL plus]** `1` **[!UICONTROL day]**. Seleziona il valore appropriato per ogni singola parte dell’espressione.
         * Seleziona un valore corrente. Ad esempio: **[!UICONTROL current year]**.
         * Seleziona un valore per il calcolo aggiuntivo. Ad esempio: **[!UICONTROL plus]**.
         * Dopo aver specificato un calcolo aggiuntivo, specifica un valore. Ad esempio: `1`.
         * Dopo aver specificato un calcolo aggiuntivo, seleziona il periodo di tempo da utilizzare per il calcolo. Ad esempio **[!UICONTROL day]**.

     Seleziona **[!UICONTROL Hide details]** per nascondere i dettagli del calcolo delle date continue.

1. Seleziona **[!UICONTROL Apply]** per applicare l’intervallo di date al pannello da cui è stato richiamato il calendario.
Seleziona **[!UICONTROL Apply to all panels]** per applicare l’intervallo di date a tutti i pannelli nel progetto Workspace.



## Zona di rilascio {#dropzone}

La zona di rilascio del pannello, denominata **[!UICONTROL _Rilascia un componente per filtrare o suddividere i dati_]**, consente di filtrare o suddividere i dati del pannello. I segmenti o i raggruppamenti utilizzati per filtrare o raggruppare i dati si applicano a tutte le tabelle e visualizzazioni a forma libera all’interno del pannello.

Segmenti e raggruppamenti ti consentono di interagire con i dati in modo controllato. Ad esempio, puoi aggiungere un menu a discesa dei segmenti per i tipi di dispositivi mobili, in modo da filtrare il pannello selezionando Tablet, Telefono cellulare o Desktop.

I segmenti possono essere utilizzati anche per consolidare più progetti in un unico progetto. Ad esempio, se disponi di versioni diverse dello stesso progetto, ciascuna con un segmento di paese diverso applicato, puoi consolidarle tutte in un unico progetto e aggiungere un menu a discesa Segmento di paese.

L’illustrazione seguente mostra le diverse varianti di segmenti o raggruppamenti (rapidi) risultanti dall’aggiunta di componenti alla zona di rilascio.

![Zona di rilascio per un pannello](assets/panel-drop-zone.png)

### Aggiungi o sostituisci

Per aggiungere o sostituire segmenti o raggruppamenti (rapidi):

1. Seleziona uno o più componenti nella barra Componenti. Utilizza ⇧+![Seleziona](/help/assets/icons/Select.svg) o ^+![Seleziona](/help/assets/icons/Select.svg) per selezionare più di un componente.
1. Trascina la selezione nella zona di rilascio, con l&#39;etichetta **[!UICONTROL _Rilascia un componente per filtrare o suddividere i dati_]** ❶, oppure su un componente esistente già posizionato nelle vicinanze della zona di rilascio.
1. Sono disponibili due opzioni quando si visualizza ![Aggiungi](/help/assets/icons/Add.svg) **[!UICONTROL Add (press "shift" to create dropdown)]** o ![Scambia](/help/assets/icons/Switch.svg) **[!UICONTROL Replace (press "shift" to add to dropdown)]**:

   ![Aggiungi o sostituisci nella zona di rilascio](assets/add-or-replace-to-drop-zone.png)

   * Rilascia la selezione per creare i seguenti componenti:
      * [Segmento](#segment) per qualsiasi componente del segmento di cui si rilascia ❷.
      * [Segmento rapido](#quick-segment) per qualsiasi componente non relativo al segmento (intervalli di date, metriche, dimensioni, elementi dimensionali) eliminato ❸.
   * Rilascia la selezione **mentre tieni premuto** ⇧ (MAIUSC) per creare i seguenti componenti:
      * Menu a discesa del segmento statico [](#drop-down-menu) con elementi da filtrare per i segmenti selezionati da eliminare ❹.
      * Menu a discesa del segmento statico [](#drop-down-menu) con elementi da filtrare per gli intervalli di date selezionati per i quali si rilascia ❺.
      * Menu a discesa del segmento statico [](#drop-down-menu) con elementi da filtrare per le metriche selezionate su cui si rilascia ❻.
      * Menu a discesa [statico](#drop-down-menu) o menu a discesa [con raggruppamenti](#drop-down-menu) con elementi su cui filtrare o raggruppare la dimensione selezionata *elementi* per la quale si eliminano ❼.
      * Menu a discesa [segmento dinamico](#drop-down-menu) o menu a discesa [raggruppamento](#drop-down-menu) con elementi su cui filtrare o raggruppare le dimensioni selezionate su cui rilasciare ❽.


### Segmento

Qualsiasi componente del segmento rilasciato viene utilizzato per segmentare il pannello. Utilizza i segmenti per ottenere informazioni segmentate sui dati e sulle visualizzazioni del pannello.

### Segmento rapido

Qualsiasi componente non appartenente ai segmenti (dimensione, elemento dimensione, metrica, intervallo di date) rilasciato definisce un [segmento rapido](#quick-segment) per segmentare il pannello. Utilizza qualsiasi componente non di segmento per creare un segmento rapido senza utilizzare il [Generatore di segmenti](/help/components/segmentation/segmentation-workflow/seg-quick.md). Un segmento creato in questo modo viene automaticamente definito come segmento a livello di evento ed etichettato **[!UICONTROL Quick segment]** per impostazione predefinita.

In alternativa, è possibile utilizzare ![FilterAdd](/help/assets/icons/FilterAdd.svg) per creare un segmento rapido.

Consulta [Segmenti rapidi](/help/components/segmentation/segmentation-workflow/seg-quick.md) per informazioni su come creare e gestire i segmenti rapidi.


### Menu a discesa

Un menu a discesa creato mentre si tiene premuto ⇧ consente di:

* contiene un elenco di elementi [static](#static) o [dynamic](#dynamic).
* comportati come [filtrare un pannello](#filter) o [suddividere un pannello](#breakdown).


#### Statico

Vengono creati menu a discesa statici per la dimensione selezionata *elementi*, metriche, segmenti e intervalli di date. Gli elementi di un menu a discesa statico si basano sui componenti selezionati che vengono rilasciati e non cambiano quando si aggiungono o sostituiscono i componenti.


#### Dinamico

I menu a discesa dinamici vengono creati solo quando si rilasciano i componenti delle dimensioni. I menu a discesa dinamici sono indicati con ![FilterRefresh](/help/assets/icons/FilterRefresh.svg) come parte dell&#39;etichetta.

Gli elementi disponibili in un menu a discesa dinamico si basano su:

* i dati risultanti dagli elementi selezionati in altri menu a discesa, segmenti e segmenti rapidi all’interno della zona di rilascio del pannello e
* i dati disponibili nell’intervallo di reporting del pannello.

Ad esempio, puoi aggiungere due menu a discesa dinamici utilizzando una dimensione Paesi e una dimensione Città. Quando si seleziona un paese dal menu a discesa **[!UICONTROL Countries]**, il menu a discesa **[!UICONTROL Cities]** viene regolato in modo dinamico in modo da visualizzare solo le città all&#39;interno del paese selezionato. Quando si dispone di menu a discesa statici aggiuntivi, gli elementi selezionati in tali menu a discesa influiscono anche sugli elementi disponibili nei menu a discesa dinamici. Gli elementi selezionati nei menu a discesa dinamici non influiscono sugli elementi disponibili nei menu a discesa statici.


#### Filtrare un pannello

Per qualsiasi componente di metrica, segmento o intervallo di date che rilasci **mentre tieni premuto** ⇧, viene creato un menu a discesa del segmento. Il menu a discesa consente di filtrare il pannello in base agli elementi disponibili per il componente rilasciato.

Per qualsiasi componente *dimension* a cui viene rilasciato **mentre si tiene** ⇧, viene creato un menu a discesa dei segmenti. Questo menu a discesa ti consente di filtrare il pannello in base agli elementi disponibili per gli elementi dimensione eliminati (menu a discesa [static](#static) segmento) o per il componente dimensione (menu a discesa [dynamic](#dynamic) segmento). Per configurare il menu a discesa in modo esplicito per filtrare utilizzando i segmenti:

* Selezionare ![Raggruppamento](/help/assets/icons/Breakdown.svg) e ![Filtro](/help/assets/icons/Filter.svg) dal menu di scelta rapida per il componente ❾.


#### Suddividere un pannello

Per qualsiasi componente *dimension* a cui viene rilasciato **mentre si tiene** ⇧, viene creato un menu a discesa dei segmenti. Al suo posto, puoi configurare il menu a discesa per suddividerlo. Per configurare il menu a discesa in modo esplicito per la suddivisione utilizzando le suddivisioni:

* Selezionare ![Filtro](/help/assets/icons/Filter.svg) e selezionare ![Raggruppamento](/help/assets/icons/Breakdown.svg) dal menu di scelta rapida per il componente ❾.

>[!IMPORTANT]
>
>I raggruppamenti sono disponibili solo per dimensioni ed elementi dimensionali, non per segmenti, intervalli di date o metriche.
>



#### Segmenti e raggruppamenti

Considera la possibilità di suddividere un pannello invece di filtrarlo (utilizzando i segmenti) nei seguenti scenari:

* Se utilizzi metriche abilitate per l’attribuzione all’interno del pannello, i segmenti spesso cancellano le metriche abilitate per l’attribuzione. I raggruppamenti vengono applicati in un punto diverso all’interno della query eseguita per recuperare i dati per il pannello. Di conseguenza, i raggruppamenti non cancellano queste metriche abilitate per gli attributi.

  Ad esempio, puoi vedere la differenza tra la metrica **[!UICONTROL Online Revenue]** basata sull&#39;attributo quando utilizzi un segmento **[!UICONTROL Luma: Product Category]** ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Women]** e un raggruppamento **[!UICONTROL Luma: Product Category]** ![Breakdown](/help/assets/icons/Breakdown.svg) **[!UICONTROL Women]**.

  ![Metriche basate su attributi: filtro rispetto a raggruppamento](assets/attribute-filter-breakdown.png)

* Se utilizzi una dimensione a livello di evento secondario all’interno di un menu a discesa di raggruppamento, i raggruppamenti vengono eseguiti a tale livello di evento secondario. Al contrario, i segmenti all’interno di un menu a discesa dei segmenti vengono eseguiti a livello di evento.

  Ad esempio, osserva la differenza tra la metrica **[!UICONTROL Online Revenue]** quando si utilizza un segmento **[!UICONTROL Luma: Product Subcategory]** ![Filter](/help/assets/icons/Filter.svg) **[!UICONTROL Tops]** e un raggruppamento **[!UICONTROL Luma: Product Subcategory]** ![Breakdown](/help/assets/icons/Breakdown.svg) **[!UICONTROL Tops]**. Il raggruppamento esegue la query esplicitamente a livello di evento secondario, mentre il segmento esegue la query a livello di evento.

  ![Metriche basate su eventi secondari: filtro rispetto a raggruppamento](assets/sub-event-filter-breakdown.png)

### Gestire

Puoi gestire i componenti nella zona di rilascio come segue:

| Operazioni da eseguire nella zona di rilascio del pannello... | Come fare... |
|---|---|
| Per rimuovere un segmento o un segmento rapido. | Selezionare ![CrossSize300](/help/assets/icons/CrossSize300.svg) all&#39;interno del componente. |
| Per rimuovere un elemento selezionato da un menu a discesa. | Selezionare ![CrossSize100](/help/assets/icons/CrossSize100.svg) nell&#39;elemento. |
| Per rimuovere tutti gli elementi selezionati da un menu a discesa. | Selezionare ![CrossSize200](/help/assets/icons/CrossSize200.svg) nel menu a discesa. |
| Per modificare l&#39;etichetta di qualsiasi componente. | Passa il puntatore sull&#39;etichetta del componente e seleziona ![Modifica](/help/assets/icons/Edit.svg). |
| Per eliminare l&#39;etichetta di qualsiasi componente. | Passa il puntatore del mouse sull&#39;etichetta del componente, quindi seleziona **[!UICONTROL Delete label]** dal menu di scelta rapida del componente. |
| Per eliminare il componente dalla zona di rilascio. | Selezionare **[!UICONTROL Delete drop-down]** dal menu di scelta rapida del componente. |
| Per ottenere informazioni su un segmento o un segmento rapido. | Passa il puntatore del mouse all&#39;interno del componente e seleziona ![Informazioni](/help/assets/icons/Info.svg) per aprire il dizionario dati con le informazioni sul componente. |
| Per ottenere informazioni sul componente che definisce un menu a discesa. | Passa il puntatore del mouse all&#39;interno del menu a discesa e seleziona ![InfoOutline](/help/assets/icons/InfoOutline.svg) per aprire il dizionario dati con le informazioni sul componente. |
| Per modificare un segmento rapido. | Passa il mouse all&#39;interno del segmento rapido e seleziona ![Modifica](/help/assets/icons/Edit.svg). Vedi [Segmenti rapidi](/help/components/segmentation/segmentation-workflow/seg-quick.md) per ulteriori dettagli. |
| Per richiedere una selezione per un menu a discesa. | Selezionare **[!UICONTROL Require selection]** dal menu di scelta rapida del componente. |
| Per non consentire filtri per un menu a discesa. | Selezionare **[!UICONTROL Allow no filter]** dal menu di scelta rapida del componente. |
| Per ripristinare tutti i componenti e cancellare tutte le selezioni dei menu a discesa. | Seleziona **[!UICONTROL Reset all]**. |



>[!BEGINSHADEBOX]

Vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Utilizzo di filtri in Analysis Workspace](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/using-panels/using-drop-down-filters){target="_blank"} per un video demo.

>[!ENDSHADEBOX]

>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Menu a discesa dinamici](https://experienceleague.adobe.com/en/docs/customer-journey-analytics-learn/tutorials/analysis-workspace/tips-and-tricks/dynamic-drop-downs){target="_blank"}.

{{videocja}}

>[!ENDSHADEBOX]



## Menu di scelta rapida

Ulteriori funzionalità per un pannello sono disponibili tramite il menu di scelta rapida (clic con il pulsante destro del mouse) sull’intestazione del pannello.

![Opzioni disponibili dal menu di scelta rapida per l’intestazione di un pannello.](assets/right-click-menu.png)

Sono disponibili le seguenti opzioni:

| Opzione | Descrizione |
| --- | --- |
| **[!UICONTROL Insert copied panel]** | Consente di incollare un pannello copiato in un’altra posizione all’interno del progetto o in un progetto diverso. |
| **[!UICONTROL Insert copied visualization]** | Consente di incollare un pannello copiato in un’altra posizione all’interno del pannello, del progetto o in un progetto diverso. |
| **[!UICONTROL Apply Report Suite to all panels]** | Applica la suite di rapporti per questo pannello a tutti gli altri pannelli del progetto. |
| **[!UICONTROL Copy panel]** | Copia un pannello, in modo da poterlo inserire in un’altra posizione all’interno di un progetto o in un progetto diverso. |
| **[!UICONTROL Duplicate panel]** | Crea un duplicato esatto del pannello corrente, che potrai quindi modificare. |
| **[!UICONTROL Collapse all panels]** | Comprimi tutti i pannelli del progetto. |
| **[!UICONTROL Expand all panels]** | Espandi tutti i pannelli del progetto. |
| **[!UICONTROL Collapse all visualizations in panel]** | Comprimi tutte le visualizzazioni nel pannello corrente. |
| **[!UICONTROL Expand all visualizations in panel]** | Espandi tutte le visualizzazioni nel pannello corrente. |
| **[!UICONTROL Edit Description]** | Aggiungi (o modifica) un testo descrittivo per il pannello. |
| **[!UICONTROL Get Panel Link]** | Indirizza un utente a uno specifico pannello all’interno di un progetto. Quando selezioni il collegamento, al destinatario verrà richiesto di effettuare l’accesso prima di essere indirizzato al pannello esatto a cui è collegato. |

## Configurazione

Alcuni pannelli (come [!UICONTROL Attribution], [!UICONTROL Experimentation], [!UICONTROL Media average minute audience] e altri) dispongono di una finestra di dialogo per la configurazione che consente di creare la visualizzazione. Utilizza ![Modifica](/help/assets/icons/Edit.svg) nella parte superiore del pannello per accedere e modificare la configurazione.

![Configurare un pannello](/help/analyze/analysis-workspace/c-panels/assets/configure-panel.png)
