---
title: Pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali)
description: Come utilizzare e interpretare il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) in Analysis Workspace.
feature: Panels
role: User, Admin
exl-id: 9268baf7-b50b-4c09-a722-7bfcd4172f15
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '1148'
ht-degree: 57%

---

# Pannello Tempo trascorso per la riproduzione di file multimediali {#media-playback-time-spent-panel}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_button"
>title="Tempo trascorso su contenuti multimediali"
>abstract="Crea un pannello per analizzare il consumo video nel tempo, con vari livelli di granularità e con la possibilità di suddividerli e confrontarli."

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_mediaplaybacktimespent_panel"
>title="Tempo trascorso su contenuti multimediali"
>abstract="Analizza il consumo video nel tempo, seleziona varie granularità, suddividi e confronta.<br/><br/>**Granularità**: seleziona il periodo di tempo in base al quale osservare i visualizzatori simultanei.<br/>**Numeri di riepilogo pannello (facoltativo)**: opzione per visualizzare i numeri di riepilogo con dettagli di data o ora per ogni riga. Il valore massimo mostra i dettagli del picco del tempo di riproduzione trascorso. Il valore minimo mostra i dettagli del punto inferiore. Somma mostra i dettagli della somma totale del tempo di riproduzione trascorso.<br/>**Suddivisione serie (facoltativo)**: puoi suddividere la visualizzazione per segmenti, dimensioni, elementi dimensionali o intervalli di date. Visualizza fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello.<br/>**Formato ora**: opzione per la visualizzazione del formato ora, in ore o minuti."

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

_Questo articolo documenta il pannello Tempo di riproduzione trascorso in_ ![AdobeAnalytics](/help/assets/icons/AdobeAnalytics.svg) _**Adobe Analytics**._<br/>_Consulta il [pannello Tempo di riproduzione dei contenuti multimediali](https://experienceleague.adobe.com/en/docs/analytics/analyze/analysis-workspace/panels/media-playback-time-spent)) per la_ ![versione di CustomerJourneyAnalytics](/help/assets/icons/CustomerJourneyAnalytics.svg) _**versione del Customer Journey Analytics** di questo articolo._

>[!ENDSHADEBOX]


>[!NOTE]
>
>Il pannello Pubblico medio per minuto è disponibile solo per i clienti che hanno acquistato il componente aggiuntivo Streaming Media Collection per Adobe Analytics.
>Per ulteriori informazioni, contatta il tuo rappresentante commerciale Adobe o il team dell’account Adobe.
>

Il pannello **[!UICONTROL Media playback time spent]** consente di analizzare le riproduzioni nel tempo, con dettagli sul picco di concorrenza e con la possibilità di suddividerli e confrontarli.

In Analysis Workspace, il tempo di riproduzione trascorso è la quantità di tempo impiegata per visualizzare i flussi multimediali in un determinato momento. Include pausa, buffer e tempo di avvio.

I clienti che hanno acquistato il componente aggiuntivo Streaming Media Collection possono analizzare il tempo di riproduzione trascorso per ottenere informazioni approfondite sulla qualità dei contenuti e sul coinvolgimento dei visualizzatori. e per risolvere problemi o pianificare volumi o scala.

Il tempo di riproduzione trascorso può aiutarti a comprendere:

* Dove si è verificato il picco di concorrenza.

* Dove si è verificato il calo.

>[!BEGINSHADEBOX]

Per un video demo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Pannello Tempo di riproduzione trascorso](https://video.tv.adobe.com/v/338699?quality=12&learn=on){target="_blank"}.

>[!ENDSHADEBOX]

## Utilizzo

Per utilizzare un pannello **[!UICONTROL Media playback time spent]**:

1. Crea un pannello **[!UICONTROL Media playback time spent]**. Per informazioni su come creare un pannello, consulta [Creare un pannello](panels.md#create-a-panel).

1. Accertati di selezionare una visualizzazione dati per il pannello i cui componenti sono configurati da Streaming Media Collection.

1. Specifica l’[input](#panel-input) per il pannello.

1. Osserva l’[output](#panel-output) per il pannello.


### Input del pannello

Puoi configurare il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) usando le seguenti impostazioni di input:

| Impostazione | Descrizione |
|---|---|
| Panel date range (Intervallo date del pannello) | L’intervallo di date predefinito del pannello è Today (Oggi). È possibile modificarlo per visualizzare uno o più mesi alla volta.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Granularity (Granularità) | L’impostazione predefinita della granularità è Minuto.<br>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe. |
| Panel summary numbers (Numeri di riepilogo del pannello) | Per visualizzare i dettagli di data o ora per il tempo di riproduzione trascorso, è disponibile un numero di riepilogo. Il valore Maximum (Massimo) mostra i dettagli del picco di concorrenza. Il valore Minimum (Minimo) mostra i dettagli del valore più basso. Somma effettua la somma del tempo totale di riproduzione trascorso per la selezione. Per impostazione predefinita, il pannello mostra solo il valore Maximum (Massimo), ma puoi impostarlo su Minimum (Minimo), Sum (Somma) o qualsiasi combinazione dei tre.<br>Se utilizzi i raggruppamenti, per ciascuno viene visualizzato un numero di riepilogo. |
| Raggruppamento per serie | Facoltativamente, puoi suddividere la visualizzazione per filtri, dimensioni, elementi dimensionali o intervalli di date.<p>- È possibile visualizzare fino a 10 righe alla volta. I raggruppamenti sono limitati a un singolo livello.</p><p>- Quando si trascina una dimensione, gli elementi dimensionali principali vengono selezionati automaticamente in base all’intervallo di date del pannello selezionato.</p>- Per confrontare intervalli di date, trascina 2 o più intervalli di date nel filtro di raggruppamento per serie. |
| Formato ora | È possibile visualizzare il tempo di riproduzione trascorso in `Hours:Minutes:Seconds` (impostazione predefinita) o in `Minutes` (visualizzato in numeri interi, arrotondato a 0,5). |
| Visualizzazione della sequenza di date | Se hai inserito almeno due filtri di intervallo di date come raggruppamenti di serie, puoi selezionare l’opzione per sovrapporre (impostazione predefinita) o sequenziale. Sovrapponi visualizza le linee con un inizio comune dell&#39;asse X in modo che vengano eseguite in parallelo, mentre sequenziale visualizza le linee con il loro inizio specifico dell&#39;asse X. Se i dati sono allineati (ad esempio, il filtro 1 termina alle 20:44 e il filtro 2 inizia alle 20:45), le linee vengono visualizzate in sequenza. |


![Tempo predefinito trascorso dal playbook multimediale.](assets/mpts_default_view.png)

### Output del pannello

Il pannello Media Playback Time Spent (Tempo di riproduzione dei contenuti multimediali) restituisce un grafico a linee e numeri di riepilogo che include dettagli relativi al tempo di riproduzione massimo, minimo e/o totale trascorso. Nella parte superiore del pannello viene visualizzata una riga di riepilogo per ricordarti le impostazioni del pannello selezionate.

In qualsiasi momento, seleziona ![Modifica pannello Tempo di riproduzione dei contenuti multimediali](/help/assets/icons/Edit.svg) per modificare e ricreare il pannello.

Se selezioni la suddivisione per serie, per ciascuna suddivisione viene visualizzata una linea sul grafico a linee e un numero di riepilogo:

![L&#39;output del tempo di riproduzione dei contenuti multimediali mostra un grafico a linee e un riepilogo.](assets/mpts_outputs1.png)

### Origine dati

L’unica metrica che può essere utilizzata in questo pannello è Playback Time Spent (Tempo di riproduzione trascorso).

| Metrica | Descrizione |
|---|---|
| Tempo di riproduzione trascorso | Totale `hours:minutes:seconds` (o `minutes`) del contenuto visualizzato durante la granularità selezionata, inclusi pausa, buffer e tempo di avvio. |

## Domande frequenti

| Domanda | Risposta |
|---|---|
| Dov’è la tabella a forma libera? Come posso visualizzare l’origine dati? | <p></p><p>La tabella a forma libera non è disponibile in questa vista. Per scaricare l’origine dati, dal menu di scelta rapida nel grafico a linee seleziona l’opzione per scaricare il file CSV.</p> |
| <p>Perché la granularità è cambiata?</p> | <p>Questa visualizzazione è limitata a 1440 righe di dati (ad esempio, 24 ore con granularità al minuto). Se una combinazione di intervallo di date e granularità genera più di 1440 righe, la granularità viene aggiornata automaticamente in modo che l’intervallo di date completo possa rientrare entro questo limite di righe.</p><p></p><p>Quando passi da un intervallo di date più ampio a uno più ridotto, la granularità viene aggiornata al dettaglio più basso consentito dopo la modifica dell’intervallo di date. Per visualizzare una granularità maggiore, modifica il pannello e ricompila.</p> |
| <p></p><p>Come si confrontano nomi video, filtri, tipi di contenuto e altro ancora?</p> | <p>Per confrontare questi elementi in una singola visualizzazione, trascina filtri, dimensioni o elementi dimensionali specifici nel filtro di raggruppamento per serie.</p><p></p><p>La visualizzazione è limitata a 10 raggruppamenti. Per visualizzarne più di 10, è necessario utilizzare più pannelli.</p> |
| Come si confrontano gli intervalli di date? | Per confrontare intervalli di date diversi in una singola visualizzazione, utilizza i raggruppamenti di serie trascinando 2 o più intervalli di date. Questi intervalli di date hanno la precedenza sull’intervallo del pannello. |
| Come posso modificare il tipo di visualizzazione? | <p></p><p>Questo pannello consente solo la visualizzazione a linee per le serie temporali.</p> |
| Posso eseguire il rilevamento delle anomalie? | <p></p><p>No. Il rilevamento delle anomalie non è disponibile per questo pannello.</p> |


>[!MORELIKETHIS]
>
>[Creare un pannello](/help//analyze/analysis-workspace/c-panels/panels.md#create-a-panel)
>[Pannello del pubblico medio per minuto del file multimediale](average-minute-audience-panel.md)
>[Pannello Visualizzatori simultanei di contenuti multimediali](media-concurrent-viewers.md)
>

<!--
# Media Playback Time Spent panel

In Analysis Workspace, Playback Time Spent is the amount of time spent viewing your media streams at a specific point in time. It includes pause, buffer, and time to start.

The Media Playback Time Spent panel enables analysis of playback over time, with details on peak concurrency and the ability to break down and compare. 

Customers who have purchased the Streaming Media Collection Add-on can analyze playback time spent to gain valuable insight into the quality of content and viewer engagement, and to help when troubleshooting or planning for volume or scale.

Playback Time Spent can help you understand:

* Where peak concurrency occurred

* Where drop-offs occurred 

Following is a video overview of this panel:

>[!VIDEO](https://video.tv.adobe.com/v/338699)

## Use the Media Playback Time Spent panel

1. Go to a report suite with streaming media components enabled. 
1. Select the panel icon on the far-left, then drag the panel into your Analysis Workspace project.
1. Continue with the following sections to customize the Media Playback Time Spent panel

   * [Panel Inputs](#panel-inputs)
   * [Panel Output](#panel-output)

## Panel Inputs {#Input}

You can configure the Media Playback Time Spent panel using these input settings:

|Setting|Description|
|---|---|
|Panel date range|The panel date range default is Today. You may edit it to view a single day or many months at a time.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Granularity|The granularity default is Minute.<br>This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity is automatically updated to accommodate the full date range.|
|Panel summary numbers|To see date or time details for playback time spent, a summary number is available. The Maximum shows details for peak concurrency. The Minimum shows details for the trough. Sum adds up the total playback time spent for the selection. The panel default shows Maximum only, but you can change it to show Minimum, Sum, or any combination of the three.<br>If you are using breakdowns, a summary number is displayed for each.|
|Series breakdown|Optionally, you can break down your visualization by segments, dimensions, dimension items, or date ranges.<p>- You may view up to 10 lines at a time. Breakdowns are limited to a single level.</p><p>- When dragging a dimension, the top dimension items will be automatically selected based on the selected panel date range.</p>- To compare date ranges, drag 2 or more date ranges into the series breakdown filter.|
|Time format|You can view the playback time spent in either `Hours:Minutes:Seconds` (default) or in `Minutes` (which is displayed in whole numbers, rounded up at .5). |
|Date sequence display|If you've placed at least two date range segments as series breakdowns you'll see the option to select either overlay (default) or sequential. Overlay will display the lines with a common x-axis start so that they run in parallel, while sequential will display the lines with their specific x-axis start. If the data lines up (for example, segment 1 ends at 8:44 pm and segment 2 starts at 8:45 pm), then the lines will show in sequence. |

## Default view

![Default view](assets/mpts_default_view.png)

## Panel Output {#Output}

The Media Playback Time Spent panel returns a line chart and summary numbers to include details for the maximum, minimum, and/or sum of playback time spent. At the top of the panel, a summary line is provided to remind you of the panel settings you selected.

At any time, you can edit and rebuild the panel by clicking the edit pencil on the top right.

If you selected series breakdown, a line on the line chart and a summary number is displayed for each:

![media playback time spent output](assets/mpts_outputs1.png)

### Data Source

The only metric that can be used in this panel is Playback Time Spent.

|Metric|Description|
|---|---|
|Playback Time Spent|Total `hours:minutes:seconds` (or `minutes`) of content viewed during the selected granularity including pause, buffer, and time to start.|

## FAQs

|Question|Answer|
|---|---|
|Where is the Freeform table? How can I see the data source?|The Freeform table is not available in this view. You can download the data source by right-clicking on the line chart and downloading the CSV ﬁle.|
|Why did my granularity change?|This visualization is limited to 1440 rows of data (for example, 24-hours at minute-level granularity). If a date range and granularity combination results in more than 1440 rows, the granularity will be automatically updated to accommodate the full date range. <p>When changing from a larger date range to a smaller one, the granularity will be updated to the lowest detail allowable once the date range is changed. To view a higher granularity, edit the panel and rebuild.</p>|
| How do I compare video names, segments, content types, etc?| To compare these in a single visualization, drag segments, dimensions, or speciﬁc dimension items in the series breakdown ﬁlter.The view is limited to 10 breakdowns. To view more than 10, you must use multiple panels.|
|How do I compare date ranges?|To compare date ranges in a single visualization, use the series breakdowns by dragging 2 or more date ranges. These date ranges will override the panel date range.|
|How do I change the visualization type?|This panel only allows for the line visualization for the time series.|
|Can I run anomaly detection?|No. Anomaly detection is not available for this panel.|

-->
