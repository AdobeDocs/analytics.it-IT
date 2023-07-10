---
title: Schema del set di classificazione
description: Visualizza e modifica lo schema per un singolo set di classificazione.
exl-id: 0fc12a0c-c1cf-4159-9d8b-492ebcaa8ea1
feature: Classifications
source-git-commit: 6cc7f491340ec7c36252f7ae53de07b0ab8f3b6f
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 41%

---

# Schema

Visualizza le dimensioni di classificazione attualmente configurate per questo set di classificazione.

**[!UICONTROL Components]** > **[!UICONTROL Classification sets]** > **[!UICONTROL Sets]** > Fai clic sul nome del set di classificazione desiderato > **[!UICONTROL Schema]**

Sono disponibili i seguenti pulsanti:

<!--* **[!UICONTROL Add]**: Adds an empty row so that you can add a classification dimension to the schema.-->
* **[!UICONTROL Upload]**: carica manualmente i dati di classificazione per una o più dimensioni di classificazione. `JSON`, `CSV`, `TSV`, e `TAB` sono supportati. Il caricamento di un file valido mostra un’anteprima della tabella dei dati da classificare.
   * **[!UICONTROL File encoding]**: seleziona il file encoding corretto utilizzando questo menu a discesa. Le opzioni valide includono [!UICONTROL UTF-8] e [!UICONTROL Latin1].
   * **[!UICONTROL List delimiter]**: seleziona il delimitatore elenco corretto. Se utilizzi un file scaricato o un file modello, assicurati che il [!UICONTROL List delimiter] qui corrisponda al [!UICONTROL List delimiter] di quando il file è stato scaricato.
   * **[!UICONTROL Apply]**: salva i dati di classificazione caricati nel set di classificazione.

  ![Caricamento del set di classificazione](../../assets/classification-set-upload.png)

* **[!UICONTROL Download]**: scarica i valori chiave e le relative colonne di classificazione.
   * **[!UICONTROL Rows]**: numero massimo di righe da includere nel file di download.
   * **[!UICONTROL Download rows received between]**: selettore data calendario che consente di filtrare i valori chiave in base a quando vengono visualizzati nel rapporto. Se un valore chiave non è stato compreso in questo intervallo di date, non viene visualizzato nel file scaricato.
   * **[!UICONTROL Data returned]**: elenco a discesa che consente di filtrare i valori chiave inclusi nel file scaricato in base ai dati di classificazione associati.
      * **[!UICONTROL All classified values]**: include righe in cui i dati di classificazione sono inclusi in almeno una colonna.
      * **[!UICONTROL All unclassified values]**: include righe in cui mancano i dati di classificazione in almeno una colonna.
   * **[!UICONTROL File format]**: elenco a discesa che determina il formato del file di download. Le opzioni includono [!UICONTROL JSON], [!UICONTROL Comma separated values] e [!UICONTROL Excel tab separated values].
   * **[!UICONTROL File encoding]**: elenco a discesa che determina la codifica del file. Le opzioni includono [!UICONTROL UTF-8] e [!UICONTROL Latin1]. Si consiglia UTF-8.

  ![Download del set di classificazione](../../assets/classification-set-download.png)

* **[!UICONTROL Template]**: scarica un file modello. Questo file è simile al pulsante [!UICONTROL Download], ma non contiene dati di classificazione o valori chiave.
   * **[!UICONTROL File format]**: elenco a discesa che determina il formato del file modello. Le opzioni includono [!UICONTROL Comma separated values] e [!UICONTROL Excel tab separated values].
   * **[!UICONTROL File encoding]**: elenco a discesa che determina la codifica del file. Le opzioni includono [!UICONTROL UTF-8] e [!UICONTROL Latin1]. Si consiglia UTF-8.
   * **[!UICONTROL List delimiters]**: elenco a discesa che determina il delimitatore di elenco che separa le colonne di classificazione su ogni riga.

  ![Modello per set di classificazione](../../assets/classification-set-template.png)

* **[!UICONTROL Job history]**: collegamento che ti porta al [Gestione processi](../job-manager.md), mostra i processi solo per questo set di classificazione.
* **[!UICONTROL Automate]**: acquisisci automaticamente i dati dalle posizioni di archiviazione esterne.
   * **[!UICONTROL Location account]**: elenco a discesa che mostra gli account località esistenti configurati dalla tua organizzazione. Se la tua organizzazione non ha già configurato un account località, puoi configurarne uno selezionando [!UICONTROL **Crea un nuovo account**].

     Per informazioni sulla configurazione dell&#39;account di posizione, vedere [Configurare i percorsi di importazione cloud](/help/components/classifications/importer/configure-import-accounts.md).

   * **[!UICONTROL Location]**: elenco a discesa che mostra le posizioni esistenti configurate dalla tua organizzazione. Se la tua organizzazione non ha già configurato una posizione, puoi configurarne una selezionando [!UICONTROL **Crea una nuova posizione**].

     Per informazioni sulla configurazione di una posizione, consulta [Configurare i percorsi di importazione cloud](/help/components/classifications/importer/configure-import-accounts.md).

   * **[!UICONTROL Delimiter]**: delimitatore di colonna per i file caricati. Le opzioni includono [!UICONTROL Comma], [!UICONTROL Semicolon], [!UICONTROL Colon], [!UICONTROL Vertical bar], [!UICONTROL Space], [!UICONTROL Forward slash], [!UICONTROL Backward slash], [!UICONTROL Dash], o [!UICONTROL Underscore].

   * **[!UICONTROL Encoding]**: elenco a discesa che determina la codifica del file. Le opzioni includono [!UICONTROL UTF-8] e [!UICONTROL Latin1]. Si consiglia UTF-8.
