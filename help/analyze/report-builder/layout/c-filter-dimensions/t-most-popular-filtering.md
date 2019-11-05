---
description: Classificazione e filtri condizionali configurati mediante logica booleana con espressioni di ricerca AND/OR.
seo-description: Classificazione e filtri condizionali configurati mediante logica booleana con espressioni di ricerca AND/OR.
seo-title: Filtraggio più comune
solution: Analytics
title: Filtraggio più comune
topic: Generatore di report
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Filtraggio più comune

Classificazione e filtri condizionali configurati mediante logica booleana con espressioni di ricerca AND/OR.

La maggior parte dei filtri popolari sono filtri di espressione configurati utilizzando la logica booleana con condizioni AND/OR, ad esempio [!UICONTROL Page does not contain]*`<product name>`* con condizioni o gruppi di condizioni come [!UICONTROL Includes All], [!UICONTROL Includes Any]o [!UICONTROL Excludes All]. È possibile [salvare](/help/analyze/report-builder/layout/c-filter-dimensions/saved-filters.md) queste espressioni per altre richieste nella cartella di lavoro o in altre cartelle di lavoro.

**Per creare un filtro più popolare**

1. Create o modificate una richiesta e passate al [!UICONTROL Request Wizard: Step 2].

   ![Informazioni sul passaggio](assets/dimension_filter.png)

1. Fare clic sul [!UICONTROL Request Wizard: Step 2]collegamento accanto alla quota nella griglia, quindi scegliere **[!UICONTROL Filter]**.
1. Sul [!UICONTROL Choose Page] modulo, attivare **[!UICONTROL Most Popular]**, quindi configurare le seguenti opzioni:

   **** Classificazione iniziale: Il rango iniziale di una dimensione. Un valore predefinito pari a 1 indica l’elemento principale nell’elenco dei dati segnalati. Ad esempio, per la dimensione [!UICONTROL Page], un punto iniziale pari a 1 indica la singola pagina del sito più richiesta. È possibile specificare 10 o un altro valore come cella di rango iniziale, generando un rapporto che inizia con 10 come la più alta. Le metriche sono disposte in ordine decrescente, in modo che le voci con l'attività maggiore vengano riportate per prime nell'elenco. Se in una richiesta sono necessari più di 50.000 nomi di pagina, ma sono presenti migliaia di pagine su cui eseguire il rapporto, è possibile copiare la richiesta e modificare il rango iniziale per recuperare i dati appropriati in blocchi di 50.000.

   **** Numero di voci: ( [!UICONTROL Pivot Layout] solo) Definisce quanti elementi vengono segnalati per una particolare metrica in un intervallo di date. Alcune metriche possono elencare centinaia di voci per una metrica, mentre altre possono mostrarne solo alcune. Ad esempio, per la dimensione [!UICONTROL Site Section], un numero di voci pari a 25 indica che il rapporto mostra le 25 pagine più visitate.

   Le frecce consentono di modificare il punto [!UICONTROL Starting Rank] e [!UICONTROL Number of Entries] il primo del foglio. Per impostazione predefinita, l’ [!UICONTROL Starting Rank] opzione è impostata su 1 e l’opzione [!UICONTROL Number of Entries] su 10. Questi valori possono essere regolati da un minimo a un massimo di 50.000 per determinate metriche. Ogni metrica ha il proprio soffitto su [!UICONTROL Number of Entries]. In questi campi non sono consentiti valori negativi o zero. Se scegliete [!UICONTROL Starting Rank] come 15 e [!UICONTROL Number of Entries] come 10, le richieste di dati per la metrica restituiscono le 10 pagine più visitate, dove la prima pagina più visitata è il numero 15 nell’elenco per l’intervallo di date specifico. Tutte le pagine più richieste classificate tra il 15 e il 25 sono elencate in ordine decrescente.

   >[!NOTE]
   >
   >L'applicazione di filtri alle richieste esistenti causa modifiche nei dati presentati. Supponete di aver mappato i primi dieci [!UICONTROL Pages] alle celle da $A$1 a $A$10, con 1 per [!UICONTROL Starting Rank] e 10 per [!UICONTROL Number of Entries]. Se si modificano questi valori in modo da visualizzare 1 per [!UICONTROL Starting Rank] e solo 3 per [!UICONTROL Number of Entries], i dati che precedentemente riempivano le celle da $A$4 a $A$10 non saranno più visualizzati.

1. Per creare un'espressione di ricerca, fate clic su **[!UICONTROL Add]**.

   ![Informazioni sul passaggio](assets/expressions_define_filter.png)

1. Sul [!UICONTROL Define Filter] modulo, configurare le condizioni adatte alle proprie esigenze.

   ![select_cell_icon.png](assets/select_cell_icon.png): Consente di individuare una condizione definita nel valore di una cella.

   **** Aggiungi condizione: Aggiunge una condizione all'espressione. Non esiste alcun limite al numero di condizioni che è possibile aggiungere.

1. Fai clic su **[!UICONTROL OK]**.

   ![Informazioni sul passaggio](assets/choose_page_02.png)

1. Nel [!UICONTROL Choose Page] modulo fare clic su **[!UICONTROL Save]** per salvare l'espressione.
1. Fai clic su **[!UICONTROL OK]**.
