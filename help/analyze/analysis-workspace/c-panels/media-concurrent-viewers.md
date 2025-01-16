---
title: Pannello Visualizzatori simultanei di contenuti multimediali
description: Come utilizzare e interpretare il pannello Media Concurrent Viewers (Visualizzatori simultanei di contenuti) in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 29575b51-e319-4156-9834-aa0b671afb31
source-git-commit: ca1e86606454c2f906cef0cc1d1a9d1c67cedf0e
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 49%

---


# Pannello Visualizzatori simultanei di file multimediali {#media-concurrent-viewers-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_button"
>title="Visualizzatori simultanei di contenuti multimediali"
>abstract="Crea un pannello per analizzare il pubblico medio per minuto di un contenuto specifico o in un periodo di tempo specifico."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaconcurrentviewers_panel"
>title="Visualizzatori simultanei di contenuti multimediali"
>abstract="Analizza i visualizzatori simultanei nel tempo, visualizza il picco di concomitanza o suddividi e confronta.<br/><br>**Granularità**: seleziona il periodo di tempo in base al quale osservare i visualizzatori simultanei.<br/>**Numeri di riepilogo pannello**:<br/>opzione che consente di visualizzare i numeri di riepilogo con dettagli di data o ora per ogni riga. Il valore massimo mostra i dettagli del picco di concomitanza. Il valore minimo mostra i dettagli del punto inferiore.<br/>**Suddivisione serie (facoltativo)**: puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date. Visualizza fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*Questo articolo documenta il pannello Visualizzatori simultanei di contenuti multimediali in ![Adobe Analytics](/help/assets/icons/AdobeAnalytics.svg)**Adobe Analytics Analytics**.<br/>Consulta [Pannello Visualizzatori simultanei di contenuti multimediali](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/media-concurrent-viewers) per la versione ![CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg)**Customer Journey Analytics**di questo articolo.*

>[!ENDSHADEBOX]


>[!NOTE]
>
>Il pannello Pubblico medio per minuto è disponibile solo per i clienti che hanno acquistato il componente aggiuntivo Streaming Media Collection per Adobe Analytics.
>
>Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe o il team dell’account Adobe.
>

Il pannello **[!UICONTROL Media concurrent viewers]** consente di analizzare i visualizzatori simultanei nel tempo, con dettagli sul picco di concorrenza e con la possibilità di suddividerli e confrontarli.

Puoi analizzare i visualizzatori simultanei per capire dove si è verificato il picco di concorrenza o dove si è verificato un calo, così da fornire informazioni sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori. E per risolvere problemi o pianificare volumi o scala.

In Analysis Workspace, la metrica Visualizzatori simultanei è il numero di persone univoche che visualizzano i flussi multimediali in un momento specifico, indipendentemente dal numero di sessioni.


+++ Guarda una dimostrazione video di questa funzionalità.

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

+++

## Utilizzo

Per utilizzare un pannello **[!UICONTROL Media concurrent viewers]**:

1. Crea un pannello **[!UICONTROL Media concurrent viewers]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Accertati di selezionare una visualizzazione dati per il pannello i cui componenti sono configurati da Streaming Media Collection.

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.

### Input del pannello

Puoi configurare il pannello Visualizzatori simultanei di contenuti multimediali usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| **[!UICONTROL Panel date range]** | L’intervallo di date predefinito del pannello è Today (Oggi).  È possibile modificarlo per visualizzare uno o più mesi alla volta. <br> <br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto).  Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| **[!UICONTROL Granularity]** | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto).  Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| **[!UICONTROL Panel summary numbers]** | Per visualizzare i dettagli di data o ora per i visualizzatori simultanei, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. **[!UICONTROL Minimum]** mostra i dettagli del valore minimo.  Per impostazione predefinita il pannello mostra solo il valore massimo, ma puoi impostarlo sul valore minimo o su entrambi.<br><br>Se utilizzi i raggruppamenti, per ciascuno viene visualizzato un numero di riepilogo. |
| **[!UICONTROL Series breakdown]** | Facoltativamente, puoi suddividere la visualizzazione per filtri, dimensioni, elementi dimensionali o intervalli di date.<br>È possibile visualizzare fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello.<br>Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.<br>Per confrontare intervalli di date, trascina 2 o più intervalli di date nel filtro di raggruppamento per serie. |

Ecco un esempio del pannello configurato per la granularità **[!UICONTROL Minute]**, con **[!UICONTROL Maximum only]** numeri di riepilogo. E suddiviso per **[!UICONTROL Other]**, **[!UICONTROL Table]**, **[!UICONTROL Mobile Phone]**, **[!UICONTROL Gaming Console]**, **[!UICONTROL Media Player]**, **[!UICONTROL Set-top Box]**, **[!UICONTROL Television]**.

![La vista di raggruppamento per serie di visualizzatori simultanei di contenuti multimediali mostra 7 di 10 dimensioni, segmenti o intervalli di date.](assets/concurrent-viewers-series-breakdown.png)

### Output del pannello

Il pannello Visualizzatori simultanei di contenuti multimediali restituisce un grafico a linee e numeri di riepilogo che includono i dettagli del numero massimo e/o minimo di visualizzatori simultanei.  Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, seleziona ![Modifica pannello Visualizzatori simultanei di contenuti multimediali](/help/assets/icons/Edit.svg) per modificare e ricreare il pannello.

Se selezioni una suddivisione per serie, per ciascuna suddivisione viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![Output dei visualizzatori simultanei di contenuti multimediali.](assets/concurrent-viewers-output.png)

### Origine dati

L&#39;unica metrica che può essere utilizzata in questo pannello è **[!UICONTROL Concurrent viewers]**:

| Metrica | Descrizione |
|---|---|
| **[!UICONTROL Concurrent viewers]** | Il numero di persone univoche che visualizzano i flussi multimediali in un determinato momento, indipendentemente dal numero di sessioni. |

In questa visualizzazione non è disponibile una tabella a forma libera.  Per visualizzare l&#39;origine dati, scaricarla dal menu di scelta rapida della visualizzazione grafico a linee e selezionare **[!UICONTROL Download data as CSV]**.  Sono incluse le suddivisioni per serie di dati.

![Le opzioni di output dei visualizzatori simultanei evidenziano &quot;Scarica dati come CSV&quot;.](assets/concurrent-viewers-download-csv.png)

## Domande frequenti

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | La tabella a forma libera non è disponibile in questa vista. È possibile scaricare l&#39;origine dati dal menu di scelta rapida del grafico a linee e selezionare **[!UICONTROL Download data as CSV]**. |
| Perché la granularità è cambiata? | Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe.<br><br>Quando passi da un intervallo di date più ampio a uno più ridotto, la granularità viene aggiornata al dettaglio più basso consentito dopo la modifica dell&#39;intervallo di date. Per visualizzare una granularità maggiore, modifica il pannello e ricompila. |
| Come si confrontano nomi video, filtri, tipi di contenuto e altri? | Per confrontare questi elementi in una singola visualizzazione, trascina filtri, dimensioni o elementi dimensionali specifici nel filtro di raggruppamento per serie.<br><br>La visualizzazione è limitata a 10 raggruppamenti.  Per visualizzarne più di 10, è necessario utilizzare più pannelli. |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza i raggruppamenti di serie trascinando 2 o più intervalli di date.  Gli intervalli di date sovrascrivono l’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | Questo pannello consente solo la visualizzazione a linee per le serie temporali. |
| Posso eseguire il rilevamento delle anomalie? | No.  Il rilevamento delle anomalie non è disponibile per questo pannello. |
| Perché utilizzare persone univoche invece di sessioni attive? | L’utilizzo di persone univoche consente di rimuovere i picchi indesiderati in corrispondenza dei confini tra dati da visualizzare (dove le sessioni terminano e iniziano allo stesso momento). |
| Cosa significa avere visualizzatori simultanei con granularità maggiore del minuto? | Con una granularità maggiore di un minuto, i visualizzatori simultanei sono la somma dei visualizzatori simultanei univoci per tutti i minuti entro l’intervallo di tempo in questione. Ad esempio, i visualizzatori simultanei con granularità a livello di ora corrispondono alla somma dei visualizzatori simultanei univoci per tutti i minuti all’interno di quell’ora. |
| Il pannello Workspace mostra le stesse informazioni del rapporto Visualizzatori simultanei? | No.  In Analysis Workspace, la metrica Visualizzatori simultanei è definita come il numero di persone univoche che visualizzano il flusso multimediale in un momento specifico. Indipendentemente dal numero di sessioni.<br><br>Questa metrica è diversa dal reporting sui visualizzatori simultanei nella sezione Rapporti, che utilizza sessioni attive simultanee. L’utilizzo di persone univoche consente di rimuovere i picchi indesiderati in corrispondenza dei confini tra dati da visualizzare (dove le sessioni terminano e iniziano allo stesso momento). |

<!-- For more information about Media Concurrent Viewers, visit [MA doc page]( https://url). -->


>[!MORELIKETHIS]
>
>[Creare un pannello](/help/analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Pannello Tempo di riproduzione dei contenuti multimediali](media-playback-time-spent.md)
>[Pannello del pubblico medio per minuto del file multimediale](average-minute-audience-panel.md)
>
<!--
# Media Concurrent Viewers panel

Customers who have purchased the Streaming Media Collection Add-on can analyze concurrent viewers to understand where peak concurrency occurred or where drop-offs happened to provide valuable insight into the quality of content and viewer engagement, and to help with troubleshooting or planning for volume or scale.

In Analysis Workspace, Concurrent Viewers is the number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.

The Media Concurrent Viewers panel enables analysis of concurrent viewers over time, with details on peak concurrency and the ability to break down and compare.  To access the Media Concurrent Viewers panel, navigate to a report suite with streaming media components enabled. Then, click the panel icon on the far-left and drag the panel into your Analysis Workspace project.

Here is a video overview of this panel:

>[!VIDEO](https://video.tv.adobe.com/v/330177/?quality=12)

## Panel Inputs {#Input}

You can configure the Media Concurrent Viewers panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today.  You may edit it to view a single day or many months at a time. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute. <br> <br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers| To see date or time details for concurrent viewers, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough.  The panel default shows Maximum only, but you can change it to show Minimum or both Maximum and Minimum.<br><br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown| Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges. <br><br>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.<br><br>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.<br><br>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|

### Default view

![Default view](assets/concurrent-viewers-default.png)


### Series breakdown view

![series breakdown view](assets/concurrent-viewers-series-breakdown.png)

## Panel Output {#Output}

The Media Concurrent Viewers panel returns a line chart and summary numbers to include details for the maximum and/or minimum concurrent viewers.  At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![concurrent viewers output](assets/concurrent-viewers-output.png)

### Data Source

The only metric that can be used in this panel is Concurrent Viewers:

|Metric|Description|
|---|---|
|Concurrent Viewers| Number of unique visitors viewing your media stream(s) at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted 'spikes' at show boundaries (where sessions are ending and starting at the same time).|

A Freeform table is not available in this view.  In order to view the data source, you may right-click on the line chart and download as a .csv file.  Series breakdowns will be included.


![concurrent viewers output](assets/concurrent-viewers-download-csv.png)

## FAQs {#FAQ}

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?| The Freeform table is not available in this view.  You can download the data source by right-clicking on the line chart and downloading the CSV file.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity).  If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range.<br><br>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.|
|How do I compare video names, segments, content types, etc?|To compare these in a single visualization, drag segments, dimensions, or specific dimension items in the series breakdown filter.<br><br>The view is limited to 10 breakdowns.  To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges.  These date ranges will override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No.  Anomaly detection is not available for this panel.|
|Why use unique visitors instead of active sessions?|Using unique visitors enables removal of unwanted spikes at show boundaries (where sessions are ending and starting at the same time).|
|What does it mean to have concurrent viewers at higher granularity than minute?|With a granularity larger than a minute, concurrent viewers is the sum of unique concurrent viewers for all minutes within that time range.  For example, at hour-level granularity concurrent viewers is the sum of unique concurrent viewers for all minutes within the hour.|
|Does the workspace panel show the same information as the Concurrent Viewers Report?|No.  In Analysis Workspace, Concurrent viewers is defined as the number of unique visitors viewing your media stream at a specific point in time, regardless of the number of sessions.<br><br>This is different than Concurrent Viewer reporting in the Reports section, which uses Concurrent Active Sessions.  Using unique visitors accounts for removal of unwanted spikes at show boundaries—where sessions are ending and starting at the same time.|

-->
