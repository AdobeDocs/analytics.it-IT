---
description: Scopri come filtrare e ordinare le tabelle a forma libera in Analysis Workspace.
title: Filtra E Ordina
feature: Freeform Tables
role: User, Admin
exl-id: 15fea9e2-f8d8-4489-9a44-e74a351b8f36
source-git-commit: e288365f2c984b64ae8c16ce023a7a0357a0e2b7
workflow-type: tm+mt
source-wordcount: '1538'
ht-degree: 50%

---

# Filtra e ordina tabelle a forma libera

Le tabelle a forma libera in Analysis Workspace sono la base dell’analisi interattiva dei dati. In quanto tali, possono contenere migliaia di righe di informazioni. Filtrare e ordinare i dati può essere fondamentale per far emergere in modo efficace le informazioni più importanti.

## Filtrare le tabelle

I filtri in Analysis Workspace ti aiutano a far emergere le informazioni più importanti.

>[!NOTE]
>
> Solo gli elementi dimensionali dinamici possono essere filtrati come descritto in questa sezione, non gli elementi dimensionali statici. Per ulteriori informazioni, consulta [Elementi dimensionali dinamici e statici nelle tabelle a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/manual-vs-dynamic-rows.md).

Sono disponibili vari metodi per filtrare le righe da una tabella a forma libera.

* Escludere righe specifiche da una tabella
* Applicare filtri a una tabella
* Utilizzare i filtri dei segmenti

Assicurati di leggere in che misura ogni metodo influisce sui [totali delle tabelle a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/workspace-totals.md).

### Escludere righe specifiche da una tabella

Puoi escludere rapidamente righe specifiche dalla tabella senza dover utilizzare l’opzione ![Filtro](/help/assets/icons/Filter.svg) **[!UICONTROL Filter]**.

>[!NOTE]
>
>Quando si escludono alcune righe come descritto in questa sezione, viene automaticamente aggiunta una regola [!UICONTROL Always exclude items] nella finestra di dialogo del filtro [!UICONTROL Advanced]. Puoi visualizzare la regola applicata selezionando l’icona Filtro ![Filtro](/help/assets/icons/Filter.svg), quindi [**[!UICONTROL Show advanced]**](#apply-a-simple-or-advanced-filter-to-a-table).

Per escludere righe specifiche da una tabella a forma libera:

1. Passa il puntatore sulla riga da escludere, quindi seleziona ![Chiudi](/help/assets/icons/Close.svg).

   Tieni premuto il tasto ***Maiusc*** per selezionare un intervallo di righe oppure il tasto ***Cmd*** (in Mac) o il tasto ***Ctrl*** (in Windows) per selezionare più righe.

<!--### Right-click > Delete selected rows

Note: this option does not seem to work. AN-338422

1. Select 1 or more rows. 
1. Right-click and select **[!UICONTROL Delete Selected Rows]**. 

   This action will remove the rows from the table and apply a table filter.-->


### Applicare un filtro semplice o avanzato a una tabella

Per filtrare i dati nelle tabelle a forma libera:

1. Passa il puntatore sulla colonna contenente i dati da filtrare. <!--only some types of columns show the filter... Which? Just Dimensions?-->

1. Seleziona l’icona ![Filtro](/help/assets/icons/Filter.svg) **Filtro** quando viene visualizzata.

   ![Tabella a forma libera con l’icona Filtro evidenziata.](assets/table-filter-icon.png)

   Nella finestra di dialogo **[!UICONTROL Search]** sono disponibili le seguenti opzioni:

   ![Filtro semplice](assets/filter-simple.png){width="500"}

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Includi “Nessun valore”**] | Seleziona questa opzione per visualizzare nella tabella una riga **[!UICONTROL No value]** con i dati che non hanno alcun valore per la dimensione selezionata. Deseleziona questa opzione per nascondere la riga **[!UICONTROL No value]**. |
   | [!UICONTROL **Cerca parola o frase**] | Specifica una parola o una frase in base a cui applicare il filtro. Vengono visualizzate solo le righe contenenti la parola o la frase esatta specificata. |


1. (Facoltativo) Per filtrare in base a criteri diversi o a più criteri, seleziona [!UICONTROL **Mostra avanzate**].

   Sono disponibili le seguenti opzioni di filtro avanzato:

   ![Filtro semplice](assets/filter-advanced.png){width=500}

   | Opzione | Funzione |
   |---------|----------|
   | [!UICONTROL **Includi “Nessun valore”**] | Seleziona questa opzione per visualizzare nella tabella una riga **[!UICONTROL No value]** con i dati che non hanno alcun valore per la dimensione selezionata. Deseleziona questa opzione per nascondere la riga **[!UICONTROL No value]**. |
   | [!UICONTROL **Corrispondenza**] | Scegli [!UICONTROL **Se sono soddisfatti tutti i criteri**] per mostrare solo i dati che soddisfano tutti i criteri specificati. In genere, questa opzione genera dati più precisi.<br/><br/>Scegli [!UICONTROL **Se sono soddisfatti i criteri**] per mostrare i dati che soddisfano tutti i criteri di filtro specificati. Di solito, questa opzione genera dati meno precisi. |
   | [!UICONTROL **Criteri**] | Seleziona tra le opzioni filtro seguenti:<br/><ul><li>[!UICONTROL **Contiene la frase**] (impostazione predefinita): nei risultati filtrati vengono inclusi solo i dati che contengono la frase esatta specificata. Le parole devono essere nell’ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].</li><li>[!UICONTROL **Contiene qualsiasi termine**]: nei risultati filtrati sono inclusi solo i dati contenenti una o più parole della frase specificata. </li><li>[!UICONTROL **Contiene tutti i termini**]: nei risultati filtrati sono inclusi solo i dati che contengono tutte le parole della frase specificata. Le parole non devono necessariamente essere nell&#39;ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].</li><li>[!UICONTROL **Non contiene alcun termine**]: nei risultati filtrati sono inclusi solo i dati che non contengono le parole della frase specificata. </li><li>[!UICONTROL **Non contiene la frase**]: nei risultati filtrati sono inclusi solo i dati che non contengono la frase esatta specificata. Le parole devono essere nell’ordine specificato nel [!UICONTROL **campo Cerca parola o frase**].</li><li>[!UICONTROL **È uguale a**]: nei risultati filtrati vengono inclusi solo i dati che corrispondono esattamente alla frase specificata. </li><li>[!UICONTROL **Non è uguale a**]: nei risultati filtrati vengono inclusi solo i dati che non corrispondono esattamente alla frase specificata. </li><li>[!UICONTROL **Inizia con**]: nei risultati filtrati sono inclusi solo i dati che iniziano con la parola o la frase esatta specificata. </li><li>[!UICONTROL **Termina con**]: nei risultati filtrati sono inclusi solo i dati che terminano con la parola o la frase esatta specificata. </li></ul>Seleziona ![Aggiungi](/help/assets/icons/Add.svg) [!UICONTROL **Aggiungi riga**] per aggiungere più criteri di filtro. L’opzione selezionata per [!UICONTROL **Corrispondenza**] determina **[!UICONTROL If all criteria are met]** o **[!UICONTROL If any criteria are met]**. |
   | [!UICONTROL **Escludi sempre gli elementi**] | Specifica il nome degli elementi da escludere dai dati filtrati. |

1. Seleziona **[!UICONTROL Apply]** per filtrare i dati. Seleziona **[!UICONTROL Clear]** per cancellare l’intero input. Seleziona **[!UICONTROL Cancel]** per annullare e chiudere la finestra di dialogo. <br/>Un’icona ![Filtro](/help/assets/icons/FilterColored.svg) **Filtro** colorata indica e visualizza i dettagli quando viene applicato un filtro alla tabella.

### Includere criteri di filtro nei dati con tendenze nelle visualizzazioni grafici a linee sparkline e a linee {#include-filter-criteria}

Qualsiasi criterio di filtro di ricerca applicato alla dimensione tabella in una tabella a forma libera è sempre incluso nei grafici sparkline.

Oltre ai grafici sparkline, puoi configurare i criteri di filtro da includere nelle visualizzazioni delle linee connesse. Per impostazione predefinita, i criteri di filtro non sono inclusi nelle visualizzazioni a linee. Le visualizzazioni a linee visualizzano i dati per la riga selezionata nella tabella connessa. Se non è selezionata alcuna riga, vengono visualizzati solo i dati per la prima dimensione della tabella collegata.)

Per ulteriori informazioni sugli sparkline e sulle visualizzazioni a linee, consulta [Visualizzare i dati con tendenze per una tabella a forma libera](/help/analyze/analysis-workspace/visualizations/freeform-table/freeform-table-trended-data.md).

#### Configurare le visualizzazioni a linee per includere i criteri di filtro

1. Seleziona il grafico sparkline nell’intestazione della colonna della metrica.

   Quando la cella sparkline è selezionata, viene visualizzata in grigio scuro. Questo indica che i criteri di filtro sono inclusi nella visualizzazione della linea connessa. I criteri di filtro vengono applicati come segmento nella colonna. <!--show how to see it? Show what the segment looks like when it's applied? -->

   ![sparkline selezionato](assets/table-sparkline-selected.png)

#### Comprendere quando i totali delle colonne potrebbero non essere accurati

I totali delle colonne potrebbero non essere esatti nei seguenti scenari:

* Quando si utilizzano componenti statici nella colonna sinistra e [i totali di colonna vengono calcolati come somma delle righe](/help/analyze/analysis-workspace/visualizations/freeform-table/column-row-settings/table-settings.md)

  Se gli elementi riga contengono dati sovrapposti in questo scenario, i totali delle colonne non saranno accurati.

  Ad esempio, se aggiungi segmenti statici alla colonna sinistra e quindi aggiungi Utenti come metrica nella colonna destra, alcuni di questi utenti potrebbero far parte di più di un segmento statico. In questo caso, Workspace non deduplica gli utenti per ciascun segmento statico. Questo può comportare un numero più elevato di utenti totali, perché alcuni utenti potrebbero essere conteggiati più di una volta.

* Quando si utilizzano dimensioni multivalore

>[!NOTE]
>
>I grafici sparkline e line riflettono ancora i totali accurati in questi scenari.


## Ordinare le tabelle

In Analysis Workspace, puoi ordinare i dati di una tabella a forma libera in base ai seguenti tipi di colonne:

* Qualsiasi colonna di metrica

* Qualsiasi colonna di dimensione (tranne le dimensioni basate su stringhe)

È anche possibile ordinare in base a più colonne contemporaneamente.

Per impostazione predefinita, le dimensioni sono ordinate in ordine crescente e le metriche in ordine decrescente.

## Ordinare le tabelle in base a una singola colonna

Quando si ordinano i dati per una singola colonna come descritto in questa sezione, qualsiasi [ordinamento avanzato](#sort-tables-by-multiple-columns-advanced-sorting) applicato alla tabella viene rimosso.

Per ordinare i dati nelle tabelle in base a una singola colonna:

1. Passa il puntatore del mouse sull&#39;intestazione della colonna che desideri ordinare, quindi seleziona l&#39;icona **Ordina** ![Ordina](/help/assets/icons/SortOrderDown.svg) quando viene visualizzata.

   ![Menu a discesa Ordina](assets/sort-dropdown-menu.png)

1. Seleziona **[!UICONTROL Ascending]** (Mostra origine dati) o **[!UICONTROL Descending]** (Blocca selezione).

   L’icona di ordinamento rimane visibile quando l’ordinamento viene applicato alla colonna. Una freccia indica l&#39;ordinamento dei dati (![Ordinamento](/help/assets/icons/SortOrderUp.svg) per crescente o ![Ordinamento](/help/assets/icons/SortOrderDown.svg) per decrescente).

## Ordinare le tabelle in base a più colonne (ordinamento avanzato)

{{release-limited-testing-section}}

### Applica ordinamento a più colonne

Per ordinare i dati nelle tabelle in base a più colonne:

1. Passa il puntatore del mouse sull&#39;intestazione di una colonna che desideri ordinare, quindi seleziona l&#39;icona **Ordina** ![Ordina](/help/assets/icons/SortOrderDown.svg) quando viene visualizzata.

   ![Menu a discesa Ordina](assets/sort-dropdown-menu.png)

1. Seleziona **[!UICONTROL Advanced sorting]**.

   ![Finestra di dialogo Ordinamento avanzato](assets/sort-advanced-dialog.png)

1. Nella finestra di dialogo Ordinamento avanzato, eseguire una delle operazioni seguenti:

   * Aggiungere le colonne che non sono ancora ordinate selezionando il pulsante **[!UICONTROL Add sort column]**.

   * Rimuovere le colonne che non si desidera più ordinare selezionando l&#39;icona **Rimuovi** ![Rimuovi](/help/assets/icons/Close.svg).

   * Trascina le colonne più in alto o più in basso nell’elenco per regolare la priorità di ordinamento.

     Per ulteriori informazioni, vedere [Priorità ordinamento](#sort-priority).

   * Modificare il valore di ordinamento selezionando **[!UICONTROL Ascending]** o **[!UICONTROL Descending]** nel menu a discesa.

   * Seleziona una colonna diversa selezionando il menu a discesa nome colonna.

1. Seleziona **[!UICONTROL Apply]**.

L’icona di ordinamento rimane visibile quando l’ordinamento viene applicato a una colonna. Una freccia indica l&#39;ordinamento dei dati (![Ordinamento](/help/assets/icons/SortOrderUp.svg) per crescente o ![Ordinamento](/help/assets/icons/SortOrderDown.svg) per decrescente).

![esempio di ordinamento multiplo](assets/dimensions-multiple-sort.png)

### Priorità di ordinamento

Quando si ordinano dati per più colonne, i dati vengono ordinati in base alla priorità assegnata a ciascuna colonna. La numerazione delle priorità viene visualizzata accanto all&#39;icona di ordinamento ![icona priorità ordinamento](assets/sort-priority-icon.png).

La colonna con priorità primaria determina l&#39;ordine principale, la colonna con priorità secondaria determina l&#39;ordine quando le righe hanno lo stesso valore nella colonna principale, la colonna con priorità terziaria determina l&#39;ordine quando le righe hanno lo stesso valore nelle colonne principale e secondaria e così via.

Consideriamo ad esempio una tabella con le seguenti colonne:

* Giorno (dimensione)

* Visualizzazioni pagina (metrica)

* Visite (metrica)

* Velocità del contenuto (metrica)

È possibile assegnare una priorità di ordinamento a ciascuna colonna nel modo seguente:

| Nome colonna (componente) | Tipo di componente | Priorità di ordinamento |
|---------|----------|---------|
| Giorno | Dimensione | 1 |
| Visualizzazioni pagina | Metrica | 2 |
| Visite | Metrica | 3 |
| Velocità dei contenuti | Metrica | 4 |

Assegnando una priorità di ordinamento a ciascuna colonna, è possibile controllare esattamente la modalità di visualizzazione dei dati nella tabella. In questo esempio, le informazioni vengono ordinate prima per Giorno, poi per Visualizzazioni pagina, poi per Visite e infine per Velocità contenuto.

![esempio di ordinamento multiplo](assets/dimensions-multiple-sort.png)
