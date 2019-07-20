---
description: Filtri di classificazione e condizionali configurati utilizzando la logica booleana con espressioni di ricerca AND/OR.
seo-description: Filtri di classificazione e condizionali configurati utilizzando la logica booleana con espressioni di ricerca AND/OR.
seo-title: Filtro più comune
solution: Analytics
title: Filtro più comune
topic: Generatore di report
uuid: 558 fa 592-41 be -4 e 66-8705-81262 afe 1 fc 7
translation-type: tm+mt
source-git-commit: dcddb02157ac3e62781b602c5e6c7de3ef79b4fc

---


# Filtro più comune

Filtri di classificazione e condizionali configurati utilizzando la logica booleana con espressioni di ricerca AND/OR.

Most Popular filters are expression filters that you configure using Boolean logic with AND/OR conditions, such as [!UICONTROL Page does not contain]*`<product name>`* with conditions or groups of conditions like [!UICONTROL Includes All], [!UICONTROL Includes Any], or [!UICONTROL Excludes All]. [Potete salvare](../../../../analyze/report-builder/layout/c-filter-dimensions/saved-filters.md#concept_562AC2C5628247909FBA5E1867BB6AE5) queste espressioni per altre richieste in questa cartella di lavoro o in altre cartelle di lavoro.

**Per creare un filtro più popolare**

1. Create or edit a request, and advance to the [!UICONTROL Request Wizard: Step 2].

   ![Informazioni passo](assets/dimension_filter.png)

1. On the [!UICONTROL Request Wizard: Step 2], click the link next to the dimension in the grid, then choose **[!UICONTROL Filter]**.
1. On the [!UICONTROL Choose Page] form, enable **[!UICONTROL Most Popular]**, then configure the following options:

   **Classificazione iniziale:** Punto iniziale di una dimensione. Un valore predefinito pari a 1 indica il primo elemento nell'elenco dei dati segnalati. For example, for the dimension [!UICONTROL Page], a starting mark of 1 indicates the single most requested page of your site. Potreste specificare 10 o un altro valore come cella di classificazione iniziale, che produce un rapporto a partire da 10. Le metriche sono disposte in ordine decrescente, in modo che gli elementi delle linee con la maggior parte delle attività vengano segnalati per prima nell'elenco. Se hai bisogno di più di 50,000 nomi di pagina in una richiesta, ma hai migliaia di pagine su cui eseguire il rapporto, puoi copiare la richiesta e cambiare il livello iniziale per recuperare i dati appropriati in blocchi di 50,000.

   **Numero di voci:** [!UICONTROL Pivot Layout] (solo) Definisce il numero di elementi segnalati per una particolare metrica su un intervallo di date. Alcune metriche possono elencare centinaia di voci per una metrica, mentre altri potrebbero mostrare solo alcuni. For example, for the dimension [!UICONTROL Site Section], a number of entries of 25 indicates that the report shows the 25 most visited pages.

   Arrows allow you to change the [!UICONTROL Starting Rank] and [!UICONTROL Number of Entries] of the first data point in the sheet. By default, the [!UICONTROL Starting Rank] is set to 1 and the [!UICONTROL Number of Entries] to 10. Per determinate metriche, questi valori sono regolati da almeno uno a un massimo di 50,000. Each metric has its own ceiling on [!UICONTROL Number of Entries]. In questi campi non sono consentiti valori negativi o zero. If you choose a [!UICONTROL Starting Rank] as 15 and [!UICONTROL Number of Entries] as 10, data requests for the metric return the 10 most visited pages, where the first most visited page is number 15 in the list for the specific date range. Tutte le pagine più richieste classificate da 15 a 25 sono elencate in ordine decrescente.

   >[!NOTE]
   >
   >L'applicazione di filtri alle richieste esistenti causa modifiche nei dati mostrati. Suppose you mapped the top ten [!UICONTROL Pages] to cells $A$1 through $A$10, with 1 for [!UICONTROL Starting Rank] and 10 for [!UICONTROL Number of Entries]. If you change these values to show 1 for [!UICONTROL Starting Rank] and only 3 for [!UICONTROL Number of Entries], the data previously filling cells $A$4 through $A$10 will no longer appear.

1. To create a search expression, click **[!UICONTROL Add]**.

   ![Informazioni passo](assets/expressions_define_filter.png)

1. On the [!UICONTROL Define Filter] form, configure the conditions appropriate for your needs.

   ![select_ cell_ icon. png](assets/select_cell_icon.png): Consente di individuare una condizione definita nel valore di una cella.

   ** Aggiungi condizione: ** Aggiunge una condizione all'espressione. Non esiste alcun limite al numero di condizioni che è possibile aggiungere.

1. Fai clic su **[!UICONTROL OK]**.

   ![Informazioni passo](assets/choose_page_02.png)

1. On the [!UICONTROL Choose Page] form, click **[!UICONTROL Save]** to save the expression.
1. Fai clic su **[!UICONTROL OK]**.
