---
description: Filtri di classificazione e filtri condizionali configurati utilizzando la logica booleana con espressioni di ricerca AND/OR.
title: Filtraggio più comune
uuid: 558fa592-41be-4e66-8705-81262afe1fc7
feature: Report Builder
role: User, Admin
exl-id: 31587740-6caa-40cb-bb24-d7a15181f642
source-git-commit: e7346b11a7d3eb4c18ec02df6c8a07574e02a2b4
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 2%

---

# Filtraggio più comune

Filtri di classificazione e filtri condizionali configurati utilizzando la logica booleana con espressioni di ricerca AND/OR.

I filtri più popolari sono filtri di espressione configurati utilizzando una logica booleana con condizioni AND/OR, ad esempio [!UICONTROL Page does not contain]*`<product name>`*con condizioni o gruppi di condizioni come [!UICONTROL Includes All], [!UICONTROL Includes Any]oppure [!UICONTROL Excludes All]. È possibile [save](/help/analyze/report-builder/layout/c-filter-dimensions/saved-filters.md) queste espressioni per altre richieste in questa cartella di lavoro o in altre cartelle di lavoro.

**Per creare un filtro più popolare**

1. Crea o modifica una richiesta e passa alla [!UICONTROL Request Wizard: Step 2].

   ![Informazioni sul passaggio](/help/admin/admin/assets/filter.png)

1. Sulla [!UICONTROL Request Wizard: Step 2], fai clic sul collegamento accanto alla dimensione nella griglia, quindi scegli **[!UICONTROL Filter]**.
1. Sulla [!UICONTROL Choose Page] modulo, abilita **[!UICONTROL Most Popular]**, quindi configura le seguenti opzioni:

   **Classificazione iniziale:** La classificazione iniziale di una dimensione. Una classificazione predefinita pari a 1 indica la voce principale nell’elenco dei dati segnalati. Ad esempio, per la dimensione [!UICONTROL Page], un punto iniziale pari a 1 indica la singola pagina più richiesta del sito. Puoi specificare 10 o un altro valore come cella di rango iniziale, in modo da generare un rapporto che inizia con 10 come la cella di rango più alta. Le metriche sono organizzate in ordine decrescente, in modo che le voci con l’attività maggiore vengano riportate per prime nell’elenco. Se in una richiesta sono necessari più di 50.000 nomi di pagina, ma sono presenti migliaia di pagine su cui eseguire il rapporto, puoi copiare la richiesta e modificare il rango iniziale per recuperare i dati appropriati in blocchi di 50.000.

   **Numero di voci:** ( [!UICONTROL Pivot Layout] Solo) Definisce quanti elementi vengono segnalati per una particolare metrica in un intervallo di date. Alcune metriche possono elencare centinaia di voci per una metrica, mentre altre possono mostrarne solo alcune. Ad esempio, per la dimensione [!UICONTROL Site Section], un numero di voci pari a 25 indica che il rapporto mostra le 25 pagine più visitate.

   Le frecce consentono di modificare le [!UICONTROL Starting Rank] e [!UICONTROL Number of Entries] del primo punto dati del foglio. Per impostazione predefinita, la [!UICONTROL Starting Rank] è impostato su 1 e il [!UICONTROL Number of Entries] a 10. Questi valori sono regolabili da almeno uno a un massimo di 50.000 per determinate metriche. Ogni metrica ha il proprio massimale [!UICONTROL Number of Entries]. In questi campi non sono consentiti valori negativi o zero. Se scegli una [!UICONTROL Starting Rank] 15 e [!UICONTROL Number of Entries] come 10, le richieste di dati per la metrica restituiscono le 10 pagine più visitate, dove la prima pagina più visitata è il numero 15 nell’elenco per l’intervallo di date specifico. Tutte le pagine più richieste classificate tra il 15° e il 25° sono elencate in ordine decrescente.

   >[!NOTE]
   >
   >L’applicazione di filtri alle richieste esistenti causa modifiche nei dati presentati. Supponiamo che tu abbia mappato i primi dieci [!UICONTROL Pages] alle celle da $A$1 a $A$10, con 1 per [!UICONTROL Starting Rank] e 10 per [!UICONTROL Number of Entries]. Se modifichi questi valori, mostra 1 per [!UICONTROL Starting Rank] e solo 3 per [!UICONTROL Number of Entries], i dati che precedentemente riempivano le celle da $A$4 a $A$10 non verranno più visualizzati.

1. Per creare un’espressione di ricerca, fai clic su **[!UICONTROL Add]**.

   ![Informazioni sul passaggio](assets/expressions_define_filter.png)

1. Sulla [!UICONTROL Define Filter] configurare le condizioni appropriate per le tue esigenze.

   ![select_cell_icon.png](assets/select_cell_icon.png): Consente di individuare una condizione definita nel valore di una cella.

   **Aggiungi condizione:** Aggiunge una condizione all’espressione. Non esiste alcun limite al numero di condizioni che è possibile aggiungere.

1. Fai clic su **[!UICONTROL OK]**.

   ![Informazioni sul passaggio](assets/choose_page_02.png)

1. Sulla [!UICONTROL Choose Page] modulo, fai clic su **[!UICONTROL Save]** per salvare l’espressione.
1. Fai clic su **[!UICONTROL OK]**.
