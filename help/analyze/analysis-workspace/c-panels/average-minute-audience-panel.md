---
title: Pannello Pubblico medio per minuto
description: Come utilizzare e interpretare il pannello Pubblico medio per minuto in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: be8371ee-8bc6-4a99-8527-dd94eab8a7f9
source-git-commit: 9a29057e71627d4c77a1d039d7fd5b0ec9c0f447
workflow-type: tm+mt
source-wordcount: '1774'
ht-degree: 31%

---

# Pannello Pubblico medio per minuto del file multimediale {#media-average-minute-audience-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaminuteaverageaudience_button"
>title="Pubblico medio per minuto del file multimediale"
>abstract="Crea un pannello per analizzare il pubblico medio per minuto di un contenuto specifico o in un periodo di tempo specifico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaaverageminuteaudience_panel"
>title="Pubblico medio per minuto del file multimediale"
>abstract="Mostra le prestazioni di contenuti multimediali specifici o in un periodo di tempo personalizzato.<br/><br/>**Parametri generali **<br/>**Calcola metrica per**: seleziona la metrica da utilizzare per il pannello. Seleziona **Contenuto specifico** per analizzare il pubblico medio per minuto di un contenuto o evento specifico in base alla sua lunghezza. **Seleziona Periodo di tempo personalizzato** per analizzare il cambiamento del pubblico medio per minuto in un periodo di tempo personalizzato selezionato.<br/>**Dimensione di reporting**: seleziona questa opzione per creare rapporti in base a **Nome video** della dimensione **ID contenuto**. Disponibile solo quando hai selezionato Contenuto specifico come metrica.<br/>**Granularità**: seleziona la granularità per il reporting. Disponibile solo se hai selezionato Periodo di tempo personalizzato come metrica.<br/>**Filtra il contenuto per (facoltativo)**: seleziona uno spettacolo, una stagione, un episodio specifico oppure seleziona una dimensione personalizzata per filtrare il contenuto.<br/><br/>**Impostazioni avanzate **<br/>**Impostazioni tabella**: seleziona se visualizzare i valori di calcolo nella tabella.<br/>**Metrica tempo trascorso**: seleziona quale metrica del tempo trascorso desideri utilizzare per il calcolo del contenuto specifico. Disponibile solo quando hai selezionato Contenuto specifico come metrica."

<!-- markdownlint-enable MD034 -->

>[!BEGINSHADEBOX]

*Questo articolo documenta il pannello del pubblico medio per minuto in ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)**Customer Journey Analytics**.<br/>Consulta [Pannello del pubblico medio per minuto](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/average-minute-audience-panel) per la ![versione di Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg)**Adobe Analytics**di questo articolo.*

>[!ENDSHADEBOX]

>[!NOTE]
>
>Il pannello **[!UICONTROL Media average minute audience]** è disponibile solo per i clienti che hanno acquistato Streaming Media Collection per Adobe Analytics.
>
>Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe o il team dell’account Adobe.
>

In Analysis Workspace, il pubblico medio per minuto può fornire informazioni su

* il tempo impiegato per visualizzare un flusso multimediale specifico diviso per la durata del contenuto, oppure
* il tempo impiegato per la visualizzazione durante un periodo di tempo personalizzato con granularità selezionata.

Il pannello Pubblico medio per minuto consente di comprendere il consumo medio dei contenuti confrontando programmi di qualsiasi durata o genere. Ad esempio, puoi comprendere il consumo medio quando confronti una sitcom di 30 minuti con un evento sportivo di 3 ore.

Inoltre, puoi utilizzare il pannello Pubblico medio per minuto del file multimediale per confrontare o aggiungere questo pubblico medio per minuto digitale alle metriche medie per minuto della TV lineare.

Il pannello Pubblico medio per minuto fornisce i seguenti vantaggi rispetto alla metrica Pubblico medio per minuto:

* Supporta periodi di tempo personalizzati

* Consente di aggiornare la classificazione della durata dopo l’elaborazione delle viste (se la classificazione della durata non era presente o deve essere corretta)

  Se esegui questo aggiornamento quando utilizzi la metrica, la classificazione della durata non esiste (se la classificazione non era presente). Oppure la classificazione della durata non è aggiornata (se la classificazione era presente ma non corretta).

## Utilizzo

Per usare un pannello **[!UICONTROL Media average minute audience]**:

1. Crea un pannello **[!UICONTROL Media average minute audience]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Accertati di selezionare una visualizzazione dati per il pannello i cui componenti sono configurati da Streaming Media Collection.

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

### Input del pannello

Utilizza le impostazioni di input descritte in questa sezione per configurare il pannello Pubblico medio per minuto del file multimediale.

1. Configura le seguenti impostazioni di input:

   | Impostazione | Descrizione |
   |---------|------------|
   | **Intervallo date pannello** | L&#39;intervallo date predefinito del pannello è [!UICONTROL **Questo mese**]. È possibile modificarlo per visualizzare uno o più mesi alla volta. <br></br> Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
   | [!UICONTROL **Rilascia qui un segmento (o qualsiasi altro componente)**] | Come altri pannelli, questa impostazione filtra le selezioni in base ai segmenti creati. Questa impostazione è un ottimo modo per esaminare piattaforme specifiche, flussi live o altri segmenti multimediali comuni. |
   | [!UICONTROL **Calcola metrica per**] | Scegli se visualizzare il pubblico medio per minuto di [**[!UICONTROL Specific content]**](#specific-content). Oppure se desideri visualizzare il pubblico medio per minuto di un [**[!UICONTROL Custom time period]**](#custom-time-period).<br/><br/>Seleziona [!UICONTROL **Periodo di tempo personalizzato**]: <ul><li>Se la durata non è disponibile, oppure </li><li>se desideri visualizzare il pubblico medio per minuto di una serie temporale con più parti di contenuto, oppure</li><li>per contenuti senza una specifica durata assegnata (come durante un live stream o un evento)</li></ul></li></li></ul> <p>Questa impostazione modifica il flusso di lavoro e l’output del rapporto.</p> |

1. Continua con [Contenuto specifico](#specific-content) o [Periodo di tempo personalizzato](#custom-time-period), a seconda dell&#39;opzione scelta nell&#39;elenco a discesa [!UICONTROL **Calcola metrica per**].

#### Contenuto specifico

1. Se hai selezionato [!UICONTROL **Contenuto specifico**] nel menu a discesa [!UICONTROL **Calcola metrica per**] durante la [configurazione degli input del pannello](#panel-inputs), specifica le seguenti opzioni di configurazione:

   | Impostazione | Descrizione |
   |---------|------------|
   | [!UICONTROL **Dimensione di reporting**] | Quando selezioni un contenuto specifico, puoi selezionare l’output del rapporto in modo da utilizzare i campi ID contenuto o nome video per mostrare il contenuto e il pubblico medio per minuto associato. |
   | [!UICONTROL **Filtra contenuto per (facoltativo)**] | Scegli come filtrare il contenuto specifico, a seconda della visualizzazione desiderata o della struttura dei dati. <ul>[!UICONTROL **Spettacolo, stagione, episodio**]: visualizza gli spettacoli disponibili nel menu a discesa, che puoi filtrare utilizzando una ricerca (oppure trascinando e rilasciando il nome dello spettacolo dalla colonna sinistra). Puoi terminare la selezione per visualizzare tutte le stagioni dello spettacolo oppure filtrare per singole stagioni e poi per singoli episodi. Questa impostazione mostra i dati relativi a spettacoli, stagioni o episodi per il periodo di tempo selezionato.</li><li>[!UICONTROL **Dimensione personalizzata**]: se il nome dello spettacolo si trova in una dimensione personalizzata, puoi trovarlo eseguendo una ricerca nell&#39;elenco a discesa della dimensione (facoltativo) o utilizzando la ricerca nella colonna sinistra. L’elemento dimensionale si popola automaticamente in base a tale selezione e viene trattato come un episodio.</li><li>[!UICONTROL **Nessuno**]: mostra tutti i nomi video con dati del pubblico medio per minuto per la selezione scelta. Questa opzione è selezionata per impostazione predefinita.</li></ul> |

1. Continua con [Impostazioni avanzate contenuto specifico](#specific-content-advanced-settings) per configurare le impostazioni avanzate.

#### Impostazioni avanzate del contenuto specifico

1. Con [!UICONTROL **Contenuto specifico**] selezionato nel menu a discesa [!UICONTROL **Calcola metrica per**], selezionare [!UICONTROL **Mostra impostazioni avanzate**], quindi specificare le opzioni di configurazione seguenti:

   | Opzioni | Descrizione |
   |---------|------------|
   | **[!UICONTROL Table settings]** | L&#39;opzione predefinita **[!UICONTROL Show calculation values in table]** mostra il numeratore e il denominatore del pubblico medio per minuto come colonne precedenti nella tabella. Deselezionando questa opzione le due colonne vengono rimosse. La colonna del pubblico medio per minuto rimane nella tabella accanto al nome video o all’ID contenuto. |
   | **[!UICONTROL Time spent metric]** | È possibile scegliere l&#39;opzione predefinita **[!UICONTROL Content Time Spent]**, che include solo il tempo del contenuto. Oppure puoi scegliere di utilizzare **[!UICONTROL Media Time Spent]**, che include il contenuto e il tempo degli annunci insieme come calcolo del numeratore per il pubblico medio per minuto. |

1. Seleziona [!UICONTROL **Build**] per completare la creazione del pannello Pubblico medio per minuto.

1. Continua con [Output pannello](#panel-output) per informazioni su come utilizzare il pannello Pubblico medio per minuto del file multimediale.

#### Periodo di tempo personalizzato

1. Se hai selezionato [!UICONTROL **Periodo di tempo personalizzato**] nel menu a discesa [!UICONTROL **Calcola metrica per**] durante la [configurazione degli input del pannello](#panel-inputs), specifica le seguenti opzioni di configurazione:

   | Opzioni | Descrizione |
   |---------|------------|
   | **[!UICONTROL Granularity]** | La granularità predefinita è [!UICONTROL **5 minuti**], ma puoi scegliere una qualsiasi delle granularità utilizzate come denominatore per la serie temporale nel periodo di tempo selezionato. Ad esempio, selezionando dalle 12:00 alle 12:30 con una granularità di 5 minuti, viene restituito il pubblico medio per minuto nell’intera mezz’ora, nonché sei righe contenenti il pubblico medio per minuto per ogni periodo di 5 minuti. Queste righe vengono utilizzate come punti dati per il grafico delle serie temporali. |
   | [!UICONTROL **Filtra contenuto per (facoltativo)**] | Scegli come filtrare il contenuto specifico, a seconda della visualizzazione desiderata o della struttura dei dati. <ul>[!UICONTROL **Spettacolo, stagione, episodio**]: visualizza gli spettacoli disponibili nel menu a discesa, che puoi filtrare utilizzando una ricerca (oppure trascinando e rilasciando il nome dello spettacolo dalla colonna sinistra). Puoi terminare la selezione per visualizzare tutte le stagioni dello spettacolo oppure filtrare per singole stagioni e poi per singoli episodi. Questa impostazione mostra i dati relativi a spettacoli, stagioni o episodi per il periodo di tempo selezionato.</li><li>[!UICONTROL **Dimensione personalizzata**]: se il nome dello spettacolo si trova in una dimensione personalizzata, puoi trovarlo eseguendo una ricerca nell&#39;elenco a discesa della dimensione (facoltativo) o utilizzando la ricerca nella colonna sinistra. L’elemento dimensionale si popola automaticamente in base a tale selezione e viene trattato come un episodio.</li><li>[!UICONTROL **Nessuno**]: mostra tutti i nomi video con dati del pubblico medio per minuto per la selezione scelta. Questa opzione è selezionata per impostazione predefinita.</li></ul> |

1. Continua con [Impostazioni avanzate del periodo di tempo personalizzato](#custom-time-period-advanced-settings) per configurare le impostazioni avanzate.

#### Impostazioni avanzate del periodo di tempo personalizzato

1. Con [!UICONTROL **Periodo di tempo personalizzato**] selezionato nel menu a discesa [!UICONTROL **Calcola metrica per**], seleziona [!UICONTROL **Mostra impostazioni avanzate**], quindi specifica la seguente opzione di configurazione:

   | Opzione | Descrizione |
   |---------|------------|
   | **[!UICONTROL Table settings]** | L’impostazione predefinita visualizza i valori di calcolo nella tabella, la quale visualizza il numeratore e il denominatore del pubblico medio per minuto come colonne precedenti nella tabella. Deselezionando questa opzione le due colonne vengono rimosse, lasciando solo il pubblico medio per minuto accanto al periodo di tempo. |

1. Seleziona [!UICONTROL **Build**] per completare la creazione del pannello Pubblico medio per minuto.

1. Continua con [Output pannello](#panel-output) per informazioni su come utilizzare il pannello Pubblico medio per minuto del file multimediale.

### Output del pannello

L&#39;output del pannello varia a seconda che sia stato scelto [!UICONTROL **Contenuto specifico**] o [!UICONTROL **Periodo di tempo personalizzato**] nel menu a discesa [!UICONTROL **Calcola metrica per**] durante la [configurazione degli input del pannello](#panel-inputs).

#### Contenuto specifico

Il pannello Pubblico medio per minuto restituisce quanto segue:

* Pubblico medio per minuto totale dell’intera selezione
* Filtri e pubblico medio per minuto dei singoli video, visualizzati in una tabella
* Durata del contenuto e lunghezza del video (durata), se è stata selezionata tale impostazione avanzata

Per modificare e ricreare il pannello in qualsiasi momento, seleziona ![Modifica](/help/assets/icons/Edit.svg) in alto a destra.

![Vista predefinita](assets/specific-content-panel-output.png)

#### Origine dati del contenuto specifico

Il pannello Pubblico medio per minuto utilizza solo la metrica Pubblico medio per minuto per raccogliere i dati. Raggruppamenti o altre metriche non possono essere utilizzati nel pannello.

| Metrica | Descrizione |
|--------|-------------|
| **[!UICONTROL Average minute audience]** | Il tempo impiegato per visualizzare il flusso multimediale diviso per la lunghezza del video (durata) fornita tramite Classificazioni. |

#### Periodo di tempo personalizzato {#custom-time-period-output}

Il pannello Pubblico medio per minuto restituisce quanto segue:

* Il pubblico medio per minuto totale dell’intera selezione

* Pubblico medio per minuto massimo e minimo

* Grafico a linee che mostra il pubblico medio per minuto dell’intera selezione.

* Una tabella che mostra i filtri e il pubblico medio per minuto delle granularità, nonché la durata del contenuto e la granularità di ogni periodo di tempo

  Questa tabella viene visualizzata solo se è selezionata l&#39;opzione in Impostazioni avanzate denominata [!UICONTROL **Mostra valori di calcolo nella tabella**].

Per modificare e ricreare il pannello in qualsiasi momento, seleziona ![Modifica pannello Pubblico medio per minuto del contenuto multimediale](/help/assets/icons/Edit.svg) in alto a destra.


#### Origine dati del periodo di tempo personalizzato

Il pannello Pubblico medio per minuto utilizza solo la metrica Pubblico medio per minuto per raccogliere i dati. Raggruppamenti o altre metriche non possono essere utilizzati nel pannello.

| Metrica | Descrizione |
|---|---|
| **[!UICONTROL Average Minute Audience]** | Il tempo impiegato per visualizzare il flusso multimediale diviso per la selezione totale o per la granularità selezionata in minuti. |


>[!MORELIKETHIS]
>
> [Creare un pannello](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
> [Pannello Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md)
> [Pannello Tempo di riproduzione dei contenuti multimediali](media-playback-time-spent.md)
>


<!--

# Media average minute audience panel

>[!NOTE]
>
>The Media average minute audience panel is available only to customers who have purchased the Streaming Media Collection Add-on. 
>
>Contact your Adobe Sales Representative or Adobe Account Team to purchase the Streaming Media Collection Add-on. 

In Analysis Workspace, average minute audience is the time spent viewing your media stream divided by the duration of the content or the total selection of the period and selected granularity.

The Media average minute audience panel enables you to better understand average consumption of your content by comparing programs of any length or genre. For example, you can understand average consumption when comparing a 30-minute sitcom with a 3-hour sporting event.

In addition, you can use the Media average minute audience panel to compare or append this digital average minute audience to linear TV average minute metrics. 

The Media average minute audience panel provides the following benefits over the Average Minute Audience metric:

* Supports custom time periods

* Allows for updating the duration classification after views are processed (if it was not present or if it needs to be corrected)

  If you did this when using the metric, it either won't exist (if the classification wasn't present) or it will be out of date (if the classification was present but incorrect).

## Access the Media average minute audience panel

1. In Analysis Workspace, go to a report suite that has streaming media components enabled. 

1. In the left nav, select the **Panels** icon.

   ![Panels icon in left nav](assets/panels-icon.png)

1. Drag the [!UICONTROL **Media average minute audience**] panel onto the canvas in Analysis Workspace.

1. To configure the panel, continue with [Panel inputs](#panel-inputs).

## Panel inputs {#Input}

Use the input settings described in this section to configure the Media average minute audience panel.

1. Begin creating a Media average minute audience panel, as described in [Access the Media average minute audience panel](#access-the-media-average-minute-audience-panel).

1. Configure the following input settings:

   | Setting | Description |
   |---------|------------|
   | **Panel date range** | The panel date range default is [!UICONTROL **This month**]. You can edit it to view a single day or many months at a time. <br></br> This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range. |
   | [!UICONTROL **Drop a segment here (or any other component)**] | Like other panels, this setting filters your selections based on segments you've created. This is a great way to look at specific platforms, live streams, or other common media segments. |
   | [!UICONTROL **Calculate metric for**] | Choose whether you want to see the average minute audience for a specific piece of content, or if you want to see the average minute audience for a custom period of time:<ul><li>**Specific content:** This is available only if the duration has been updated using Classifications. If the duration is unavailable, or if you want to view the average minute audience for a time series with multiple pieces of content or content without a specific assigned duration (like during a live stream or event), then you should select [!UICONTROL **Custom time period**]. (Durations can be set using Classifications either before or after processing time.)</li><li>**Custom time period:** This is available regardless of whether the durations is made available using Classifications.</li></ul> <p>This setting changes the workflow and report output.</p>  |

1. Continue with [Specific content](#specific-content) or [Custom time period](#custom-time-period), depending on the option you chose in the [!UICONTROL **Calculate metric for**] drop-down menu.

### Specific content

1. If you selected [!UICONTROL **Specific content**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs), specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | [!UICONTROL **Reporting dimension**] | When you choose specific content, you can select the report output to use either the video name or content ID fields to show the content and its associated average minute audience for the time period selected. |
   | [!UICONTROL **Filter content by (optional)**] | Choose how to filter the specific content, depending on the view you want or the way your data is structured. <ul>[!UICONTROL **Show, season, episode**]: Displays your available shows in the drop-down, which you can filter using a search (or by dragging and dropping the show name from the left column). You can end your selection there to see all the seasons of your show, or you can filter by individual seasons and then by individual episodes. This setting shows the data for those shows, seasons, or episodes for the selected time period.</li><li>[!UICONTROL **Custom dimension**]: If your show name is under a custom dimension, you can find it either by searching in the dimension (optional) drop down or by using the left column search. The dimension item automatically populates based on that selection and is treated as an episode.</li><li>[!UICONTROL **None**]: Shows all the video names that have average minute audience data for the selection you've chosen. (This options is selected by default.)</li></ul>  |

1. Continue with [Specific content advanced settings](#specific-content-advanced-settings) to configure advanced settings. 

### Specific content advanced settings

1. With [!UICONTROL **Specific content**] selected in the [!UICONTROL **Calculate metric for**] drop-down menu, select [!UICONTROL **Show advanced settings**], then specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | Table settings | The default setting shows the calculation values in the table, which shows the numerator and denominator of the average minute audience as the preceding columns in the table. Deselecting this option removes those two columns, leaving only the average minute audience next to the video name or content ID. |
   | Time spent metric | You can choose the default content time spent, which includes only content time, or you can choose to use the media time spent, which includes content and ad time together as the numerator calculation for the average minute audience. |

1. Select [!UICONTROL **Build**] to finish creating the Media average minute audience panel.

1. Continue with [Panel output](#panel-output) for information about how to use the Media average minute audience panel.

### Custom time period

1. If you selected [!UICONTROL **Custom time period**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs), specify the following configuration options:

   | Setting | Description |
   |---------|------------|
   | Granularity | The default granularity is [!UICONTROL **5-Minute**], but you can choose any of the granularities that are used as the denominator for the time series within your overall time period selection made in the calendar selection. For example, selecting 12:00 pm to 12:30 pm with a 5-minute granularity returns the average minute audience over the full half hour as well as six rows with the average minute audience for each 5-minute period. These rows are used as the datapoints for the time series chart. |
   | [!UICONTROL **Filter content by (optional)**] | Choose how to filter the specific content, depending on the view you want or the way your data is structured. <ul>[!UICONTROL **Show, season, episode**]: Displays your available shows in the drop-down, which you can filter using a search (or by dragging and dropping the show name from the left column). You can end your selection there to see all the seasons of your show, or you can filter by individual seasons and then by individual episodes. This setting shows the data for those shows, seasons, or episodes for the selected time period.</li><li>[!UICONTROL **Custom dimension**]: If your show name is under a custom dimension, you can find it either by searching in the dimension (optional) drop down or by using the left column search. The dimension item automatically populates based on that selection and is treated as an episode.</li><li>[!UICONTROL **None**]: Shows all the video names that have average minute audience data for the selection you've chosen. (This options is selected by default.)</li></ul>  |

1. Continue with [Custom time period advanced settings](#custom-time-period-advanced-settings) to configure advanced settings. 

### Custom time period advanced settings

1. With [!UICONTROL **Custom time period**] selected in the [!UICONTROL **Calculate metric for**] drop-down menu, select [!UICONTROL **Show advanced settings**], then specify the following configuration option:

   | Setting | Description |
   |---------|------------|
   | Table settings | The default setting displays the calculation values in the table, which displays the numerator and denominator of the average minute audience as the preceding columns in the table. Deselecting this option removes those two columns leaving only the average minute audience next to the time period. |

1. Select [!UICONTROL **Build**] to finish creating the Media average minute audience panel.

1. Continue with [Panel output](#panel-output) for information about how to use the Media average minute audience panel.

## Panel output

The panel output differs depending on whether you chose [!UICONTROL **Specific content**] or [!UICONTROL **Custom time period**] in the [!UICONTROL **Calculate metric for**] drop-down menu when [configuring panel inputs](#panel-inputs).

### Specific content

The Media average minute audience panel returns the following:

* Total average minute audience for your entire selection
* Filters and average minute audience for the individual videos displayed in a table 
* Content time spent and video length (duration) if that advanced setting was selected

To edit and rebuild the panel at any time, select the Edit (pencil) icon in the top right.

![Default view](assets/specific-content-panel-output.png)

### Specific content data source

The Media average minute audience panel uses only the Average Minute Audience metric to gather data. Breakdowns or other metrics cannot be used in the panel.

| Metric | Description |
|--------|-------------|
| Average Minute Audience | The time spent viewing your media stream divided by the video length (duration) supplied via Classifications. |

### Custom time period {#custom-time-period-output}

The Media average minute audience panel returns the following:

* The total average minute audience for your entire selection

* The maximum and minimum average minute audience

* The line series graph showing the average minute audience over the entire selection.

* A table that shows the filters and average minute audience for the granularities, as well as the content time spent and granularity for each time period 

  This table displays only if the option under advanced settings called [!UICONTROL **Show calculation values in table**] is selected.

To edit and rebuild the panel at any time, select the Edit (pencil) icon in the top right.

![concurrent viewers output](assets/custom-time-period-panel-output.png)

### Custom time period data source

The Media average minute audience panel uses only the Average Minute Audience metric to gather data. Breakdowns or other metrics cannot be used in the panel.

|Metric|Description|
|---|---|
|Average Minute Audience| The time spent viewing your media stream divided by the total selection or selected granularity in minutes.|

-->