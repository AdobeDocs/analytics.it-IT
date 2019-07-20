---
description: Passaggi per eseguire i diversi tipi di rapporti.
seo-description: Passaggi per eseguire i diversi tipi di rapporti.
seo-title: Eseguire diversi tipi di rapporti
solution: Analytics
title: Eseguire diversi tipi di rapporti
topic: Report, reporting e analisi
uuid: f 59 ab 2 a 1-e 916-46 e 8-bb 5 b-e 6361 ba 00 dda
translation-type: tm+mt
source-git-commit: ad6ba22acf6996aa038c5a3252cae8bddbf0b36a

---


# Eseguire diversi tipi di rapporti

Passaggi per eseguire i diversi tipi di rapporti.


## Run a ranked report {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In un report classifica, la tabella mostra le classificazioni delle pagine del report in relazione alla metrica, in base a numero o percentuale. I report Ranked possono mostrare più metriche in uno stesso report.

<!-- 

t_reports_ranked.xml

 -->

1. Generate a report, such as a [!UICONTROL Pages Report] ( **[!UICONTROL Reports]** &gt; **[!UICONTROL Site Content]** &gt; **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. Per classificare il rapporto, fai clic sull'intestazione di una colonna nella tabella.

   I rapporti classificati possono contenere fino a 200 elementi elencati nella tabella (come prodotti, categorie, pagine Web e così via) e dieci metriche (entrate, ordini, viste e così via).

## Run a trended report {#task_F03B4E760B9E4EA29FC3F654E6316887}

I report con tendenze mostrano le metriche nel tempo. Puoi utilizzare questo tipo di report quando desideri sapere quali sono le prestazioni di un segmento da un periodo di tempo al successivo.

<!-- 

t_reports_trended.xml

 -->

Per la maggior parte dei rapporti Conversione e Traffico è disponibile una visualizzazione con tendenze. Using the [!UICONTROL Calendar], you can show improvement for any time period breakdowns, including days of a month, weeks of a year, weeks of a quarter, months of a year, and so on. I report con tendenze mostrano tendenze per una singola metrica (entrate, ordini, visualizzazioni e così via) fino a cinque elementi (come prodotti, categorie, pagine Web e così via).

**Per eseguire un rapporto con tendenze**

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** &gt; **[!UICONTROL Site Content]** &gt; **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

## Run a Conversion Funnel report {#task_B926A74AA6A641138C2986C1635120CB}

I rapporti Funnel di conversione mostrano la percentuale di visitatori che hanno inoltrato un set di eventi per eseguire un'azione desiderata. Ad esempio, potete vedere quanti visitatori avanzano dalla visita della pagina Web, tramite l'aggiunta di elementi a un carrello e l'acquisto di un elemento. Questo rapporto mostra anche il numero che si è abbandonato lungo la strada.

<!-- 

t_reports_conversion_funnel.xml

 -->

To run this report, select a report, such as a Pages report ( **[!UICONTROL Reports]** &gt; **[!UICONTROL Campaigns]** &gt; **[!UICONTROL Tracking Code]** &gt; **[!UICONTROL Campaign Conversion Funnel]**).

See [Conversion Reports](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=reports_conversion) for a description.

## Run a Fallout report {#task_8FD97C8260464F9DA731A93DB8F80184}

The [!UICONTROL Fallout Report] shows the number of visitors who visited a pre-specified sequence of pages. Mostra inoltre i tassi di conversione e abbandono tra i passaggi.

<!-- 

t_reports_fallout.xml

 -->

Check out the new [Fallout Analysis](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/fallout_flow.html) panel in Analysis Workspace!

1. In [!UICONTROL Adobe Analytics], click **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Fallout]**.
1. On the [!UICONTROL Fallout Report] page, click **[!UICONTROL Launch the Fallout Report Builder]**.

   ![Risultato passaggio](assets/fallout_add_items.png)

1. On the [!UICONTROL Define Checkpoints] page, specify the checkpoints that you want to use for the report.
1. Fai clic su **[!UICONTROL Run Report]**.

   ![Risultato passaggio](assets/fallout_report.png)

>[!MORE_ LIKE_ THIS]
>
>* [Descrizione rapporto Abbandono](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=reports_fallout)


## Run a Page Flow report {#task_133E8B87C3F04DA0A42D10CBA499305B}

I rapporti sul flusso di pagina mostrano l'ordine in cui i visitatori accedono alle pagine e navigano nel sito. Questo rapporto aiuta a rispondere

<!-- 

t_reports_page_flow.xml

 -->

Check out the new [Flow visualization](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html) in Analysis Workspace!

Run a [Paths](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=reports_paths) report.

For example, click **[!UICONTROL Reports]** &gt; **[!UICONTROL Paths]** &gt; **[!UICONTROL Pages]** &gt; **[!UICONTROL Next Page Flow]**.

![](assets/page_flow.png)

Leggi il rapporto da sinistra a destra, a partire dalla pagina selezionata. Le pagine visualizzate dopo la pagina selezionata sono illustrate come un ramo che si estende a destra.

Accanto al nome della pagina viene visualizzata la percentuale di visualizzazione di ciascuna pagina successiva. La larghezza della riga collegata a ogni pagina successiva rappresenta questa percentuale relativa.

**[!UICONTROL Path Views]**: Indica quante volte è stata visualizzata una pagina, se vincolata ai percorsi visualizzati.

Ad esempio, la pagina Informativa sulla privacy potrebbe avere 10,000 visualizzazioni di pagina totali, ma solo il 500 di tali visualizzazioni si è verificato subito dopo la home page. Pertanto, viene utilizzata la visualizzazione percorso.

La percentuale relativa è rappresentata dalla larghezza relativa della linea. Per impostazione predefinita, questo rapporto visualizza cinque rami di livello 2 e cinque rami di terze parti. Potete espandere il numero di rami per visualizzare fino a dieci rami di livello 2 e cinque rami di terze parti. In questo modo, l'altezza del rapporto aumenta e molto probabilmente richiede lo scorrimento per visualizzare l'intero grafico.

## Run a Funnel report {#task_2BBF6FACD48F479E8B2EE458919941CB}

You can select success events and add them to a [!UICONTROL Purchase Conversion Funnel] report or a [!UICONTROL Product Conversion Funnel] report.

<!-- 

t_reports_funnel.xml

 -->

1. Click **[!UICONTROL Reports]** &gt; **[!UICONTROL Products]** &gt; [Products Conversion Funnel](https://marketing.adobe.com/resources/help/en_US/reference/index.html?f=reports_conversion_funnel).

## Run a marketing channel report {#task_64ADED5CC75248319E06E3E029B47F78}

La generazione di rapporti sul canale di marketing fornisce una panoramica della prima allocazione del canale e dell'ultimo contatto, con metriche di reporting standard come entrate, ordini e costi. Questi report ti consentono di analizzare quante entrate vengono generate da ogni canale.

<!-- 

t_reports_marketing_channel.xml

 -->

See the [Marketing Channel](https://marketing.adobe.com/resources/help/en_US/mchannel/index.html) help system for more information.

## Run an Anomaly Detection report {#task_4808C96327354D789C075823F5C3A049}

Descrive come interpretare i grafici Riepilogo e Singoli metriche in Rilevamento anomalie.

<!-- 

t_anomaly_view.xml

 -->

Check out the new [Anomaly Detection and Contribution Analysis](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/anomaly_detection.html) features in Analysis Workspace!

**[!UICONTROL Reports]** &gt; **[!UICONTROL Site Metrics]** &gt; **[!UICONTROL Anomaly Detection]** .

>[!NOTE]
>
>Puoi anche eseguire Rilevamento anomalie da Progetti Analysis Workspace. [Altro...](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/anomaly_detection.html)

For information on setting up Anomaly Detection, refer to the [Reference Guide](https://marketing.adobe.com/resources/help/en_US/sc/user/index.html#Setting_up_Anomaly_Detection).

Il rilevamento delle anomalie mostra due tipi di grafici: Un grafico di riepilogo e singoli grafici di metrica. I singoli grafici di metrica vengono visualizzati solo se per tale metrica sono stati rilevati almeno un'anomalia.

<table id="table_88163CD8FC164342855D90D01F9C581A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tipo di grafico </p> </th> 
   <th colname="col2" class="entry"> <p>Azione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Grafico riepilogo </p> <p><img placement="break"  src="assets/ad_summary_chart.png" width="570px" id="image_1CD4C4770BAA43C4AD7CBB824AD41338" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_D26DA3024CD7468291369F549557B28A"> 
      <li id="li_1C22B6E02FFB479FB71EFAD89EB37A4E">Ogni casella rappresenta un'anomalia, tracciata al giorno, corrispondente a una metrica di seguito. </li> 
      <li id="li_8FC587D3FF4E452D83263CC7A10B6675">Verde indica anomalie sopra la linea delle tendenze, blu sotto la linea delle tendenze. </li> 
      <li id="li_25135AB691BF443599AF2A3A60E2E71A">Indica l'intensità dell'anomalia: Maggiore è l'anomalia, più scuro è il colore del punto dati e più lontano dalla linea delle tendenze. </li> 
      <li id="li_0C42AFA8897D420D8AB1A5D0F65B3B3A">Facendo clic su singole anomalie, la singola mappa metrica dell'anomalia (sotto il grafico riepilogo) viene visualizzata in alto. </li> 
      <li id="li_85C0F426952547B5A75D6BD31DE19CA5">I valori percentuali di deviazione (a sinistra del grafico) vengono calcolati come segue: 
       <ul id="ul_BEC0A88BFFAC4CF78BC9885FEB749694"> 
        <li id="li_1BAB2F50482745B69937DFAF1E09982E">Se i limiti superiori e il valore previsto sono identici, la deviazione % è 100% </li> 
        <li id="li_CA48064F5788448C8646CCE196161237">In caso contrario, la deviazione % è ((valore effettivo - valore superiore vincolato)/(valore superiore vincolato - valore previsto) * 100 </li> 
        <li id="li_4090357A0D214BC7B1C3DE0615875554">Se i limiti inferiori e il valore previsto sono identici, la deviazione % è -100% </li> 
        <li id="li_EF694E1A4E874ECD94E1E8F7302E494F">In caso contrario, la deviazione % è ((valore associato inferiore - valore effettivo)/(valore previsto - valore associato inferiore) * -100 </li> 
       </ul> </li> 
      <li id="li_5C05EF7023484CC993E96D63E842B65C">Clicking <span class="uicontrol"> Show Segments </span> brings up the segment rail that lets you apply segments to an anomaly detection report. <a href="https://marketing.adobe.com/resources/help/en_US/analytics/segment/" format="http" scope="external"> Ulteriori informazioni </a> sulla segmentazione. </li> 
      <li id="li_1B41CABF13D1407886C68EE3BC201E60">Clicking <span class="uicontrol"> Edit Metrics </span>lets you select and unselect metrics for which you want to detect anomalies. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grafico metrica singolo </p> <p><img placement="break"  src="assets/metric_report.png" width="570px" id="image_5BBECFD91CF14478AA4761E6256BBCB9" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_739C5687013743A29B63089FDA763F45"> 
      <li id="li_456A0BDA4D4E46CE9CC1C3DBAA1E2220">Visualizza punti dati anomali per singole metriche con tendenze (comprese le metriche calcolate) come dots. </li> 
      <li id="li_89FD847C65F04F48BCA7CD38D0EC51CD">Mostra l'anomalia più recente in alto e in base al numero di anomalie. </li> 
      <li id="li_98B97A9706DE4455B8D8850904CBDE03">Visualizza una linea piena per indicare dati effettivi raccolti. Questo confronto viene confrontato con le previsioni e il margine dell'errore per determinare se i punti dati sono anomali. </li> 
      <li id="li_0EEA38DDDC344BF3879430E67D74EB72">Visualizza una linea punteggiata che rappresenta una previsione basata sui dati storici (ovvero, il periodo di formazione). </li> 
      <li id="li_035BD2725D004AEDB630BF8DFF4DA4F3">Visualizza intervalli/intervalli di confidenza superiori e inferiori di 95% in una ombreggiatura grigia. </li> 
      <li id="li_021A3D1F2EDB4319B9B39620EF1C038A">Consente di comprimere ed espandere singoli rapporti facendo clic sulle frecce verso l'alto o il basso accanto al nome della metrica. </li> 
      <li id="li_722E4B9FC21047AC96D7B143197E293D">Modifica l'ordine in cui i grafici delle metriche appaiono reagendo alle analisi approfondite nel rapporto Panoramica (vedi sopra) </li> 
      <li id="li_A2441169B185475AA68A64F81E6E40B8">Consente di filtrare i grafici utilizzando termini di ricerca, ad esempio "pagina" per tutte le metriche relative alla pagina. </li> 
      <li id="li_F1BBBFCA8E2A43C29658E4FCAA36C904">Consente di visualizzare tutte le metriche definite o solo quelle con anomalie. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Setting up Anomaly Detection {#task_AF347B34F56E44A6AE70E019B6EB2F08}

Passaggi per selezionare suite di rapporti, metriche e periodi di formazione/visualizzazione per il rilevamento delle anomalie.

<!-- 

t_anomaly_config.xml

 -->

L'impostazione Rilevamento anomalie viene impostata indipendentemente per ogni suite di rapporti.

1. **[!UICONTROL Analytics > Reports > Site Metrics > Anomaly Detection]** Passa a.
1. Selezionate la suite di rapporti per la quale desiderate tenere traccia del rilevamento delle anomalie giornaliere. Per visualizzare un elenco delle suite di rapporti, fai clic sul menu a discesa Selettore suite di rapporti.
1. To select the metrics and/or define filtered metrics, click **[!UICONTROL Edit Metrics]**at the top right of the screen:  ![](assets/metrics_icon.png).

   Puoi scegliere le metriche dall'elenco (comprese le metriche calcolate) di tutte le metriche o da un elenco di metriche tracciate. Potete anche filtrare con termini specifici per limitare l'elenco. 1. Once the report has been generated, define the **[!UICONTROL Training Period]**and the **[!UICONTROL View Period]** for anomaly detection. (Pensate al periodo di formazione come "periodo di apprendimento" per l'algoritmo.)

   ![](assets/view_training_periods.png)

   Nota bene:

* Il periodo di formazione termina subito prima dell'inizio del periodo di visualizzazione.
* Il valore predefinito per entrambi è 30 giorni e può essere esteso a 60 o 90 giorni.
* L'estensione del periodo di formazione consente di inserire i dati in un contesto più ampio e di ridurre le dimensioni di un'anomalia.

   Il rapporto delle metriche Rilevamento anomalie viene aggiornato ogni volta che si modifica un parametro.
1. (Optional) Apply segments to the report by clicking **[!UICONTROL Show Segments]** and selecting one or more existing segments or creating a new segment and applying it.

   ![](assets/ad_top_menu.png)

   See the [Analytics Segmentation Guide](https://marketing.adobe.com/resources/help/en_US/analytics/segment/) for more information on creating and managing segments. 1. (Facoltativo) Preferite o contrassegnate il rapporto.
1. (Facoltativo) Modificate la data di fine del periodo di visualizzazione. Il valore predefinito è ieri.
1. Ora potete iniziare a interpretare il rapporto. [Visualizzazione dei grafici Rilevamento anomalie](../../analyze/reports-analytics/t-running-report-types.md#task_4808C96327354D789C075823F5C3A049).

## Run a Real-Time report {#task_5D25929C918E40B18965222FA94176B0}

Descrive come visualizzare e interpretare i rapporti in tempo reale.

<!-- 

reports_realtime.xml

 -->

**[!UICONTROL Reports > Site Metrics > Real-Time]** .

Il reporting in tempo reale offre due rapporti principali: un rapporto panoramica e un rapporto dettagliato. Ciascuno è composto da diversi reportlet.

For information on configuring real-time reports, see the [Analytics Reference Guide](https://marketing.adobe.com/resources/help/en_US/reference/index.html#RealTime_Reports_Configuration).

1. Take a look at the **[!UICONTROL Overview]** report and its components:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Componente interfaccia utente </th> 
   <th class="chdeschd"> Descrizione </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleziona suite di rapporti</strong></td> 
   <td class="chdesc stentry"> Mostra la suite di rapporti che copre questo rapporto in tempo reale. To change the report suite, see <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=t_realtime_admin" format="http" scope="external"> Real-Time Reports Configuration </a>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Passaggio tra i rapporti</strong></td> 
   <td class="chdesc stentry"> Consente di passare ai rapporti impostati (massimo 3). </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleziona intervallo di tempo</strong></td> 
   <td class="chdesc stentry"> Consente di scegliere l'intervallo di tempo complessivo da utilizzare per tutti i minirapporti nel rapporto. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Configurare i rapporti</strong></td> 
   <td class="chdesc stentry"> Questo collegamento all'icona a forma di ingranaggio è visibile solo se hai diritti di amministratore. Clicking it takes you to the Report Suite Manager under <span class="ignoretag"> <span class="uicontrol"> Admin Tools </span>  &gt; <span class="uicontrol"> Report Suites </span>  &gt; <span class="uicontrol"> Edit Settings </span>  &gt; <span class="uicontrol"> Real-Time </span> </span>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Visualizzazione a schermo intero</strong></td> 
   <td class="chdesc stentry"> L'icona Visualizzazione schermo intero è visibile solo se il monitor ha proporzioni specifiche (16:9 o 16:10) E se il browser lo supporta. Note that you cannot interact with the screen while it is in full-screen mode (press <span class="uicontrol"> Esc </span> to exit). La modalità a schermo intero non viene disattivata. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet traffico sito</strong></td> 
   <td class="chdesc stentry"> I dati della linea blu delle tendenze mostrano il totale del traffico per il sito globale. L'asse X utilizza le etichette letterali (15 minuti fa, 10 minuti fa) tranne il valore corrente, visualizzato come espressione in tempo reale. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet totale sito</strong></td> 
   <td class="chdesc stentry"> Mostra un conteggio del Totale del sito per la metrica selezionata per il report in tempo reale per l'ultimo N minuti. " N "è configurabile tramite il selettore Intervallo ora. <p>Il colore e la direzione della freccia si basano sul seguente algoritmo: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Guadagno significativo (freccia Su): &gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Guadagno (freccia Su): tra 5% e 100% </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Flat (freccia destra): tra 5% e -5% </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Perdita (freccia Giù destra): tra -5% e -100% </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Perdita significativa (freccia Giù): &lt; -100% </li> 
      </ul> </p> <p>Se il totale del sito è riportato in «istanze», queste istanze riflettono la dimensione nel minirapporto principale. Se esiste un nome specifico per l'istanza (ad esempio "Visualizzazioni pagina",) il rapporto totale sul sito stesso. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet principale</strong></td> 
   <td class="chdesc stentry"> Report per la dimensione primaria del report in tempo reale e per la relativa metrica. Mostra una linea di tendenza per quell'elemento per l'intervallo di tempo selezionato. Il totale della metrica rappresenta la somma per la linea di tendenza completa. La freccia indica se l'elemento sta ottenendo, ottenendo, semplice, perdendo o perdendo fortemente. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Finestra di dialogo Ricerca</strong></td> 
   <td class="chdesc stentry"> La ricerca interessa tutti i minirapporti. La ricerca viene mantenuta mentre viene visualizzato il rapporto. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Ordina per… Most Popular/Gainers/Losers</strong></td> 
   <td class="chdesc stentry"> You can toggle to sort by <span class="uicontrol"> Most Popular </span>(default), <span class="uicontrol"> Gainers </span> (dimensions showing the most growth), and <span class="uicontrol"> Losers </span> (dimensions that are on a downward trajectory.) <p>Di seguito viene illustrata la formula utilizzata per determinare i gainer o i lochi: Real-Time looks (Tempo reale) è il primo campione e l'esempio successivo e esegue un semplice calcolo «% change». Pertanto, se è selezionato «Ultimi 15 minuti» e n rappresenta il minuto corrente, n -1 viene confrontato con n -15. In tempo reale non è possibile attribuire alcuna ponderazione. Il minuto corrente viene ignorato perché non è completo e probabilmente genera un falso % change. </p> <p>Questa formula è coerente in tutte le metriche utilizzate nel report in tempo reale. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet secondario 1</strong></td> 
   <td class="chdesc stentry"> Mostra rapporti in tempo reale per la seconda dimensione del report provisioning e per la metrica. <p>Il minirapporto secondario 1 mostra le prime 4 categorie, Il 5 è un'aggregazione di tutti i valori rimanenti. Per ogni categoria viene fornita la visualizzazione grezza della categoria. Inoltre, il totale di tutte le categorie viene visualizzato al centro. </p> <p> Quando si passa il mouse su una sezione viene evidenziata la categoria associata, e sotto l'anello viene visualizzata la linea della tendenza della categoria. </p> <p> Quando si passa il mouse su un elemento di riga, l'elemento della linea viene evidenziato e la sezione associata viene visualizzata sotto l'anello. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet secondario 2</strong></td> 
   <td class="chdesc stentry"> Mostra rapporti in tempo reale per la terza dimensione del report provisioning e per la metrica. Quando si passa il mouse sopra l'etichetta dell'elemento l'etichetta viene visualizzata a destra e viene visualizzata una linea di tendenze per l'elemento rilasciato. </td> 
   </tr> 
   </table>

1. Click a list item in the Primary Reportlet to launch the **[!UICONTROL Details]** view for that list item:  ![](assets/rtr_detail_report.png)

   | **Reportlet tendenza elemento** | Mostra la linea di tendenza dell'elemento selezionato nel report Panoramica per l'ultimo N minuti. N è configurabile mediante il selettore Intervallo ora. |
   |---|---|
   | **Reportlet totale elemento** | Mostra un conteggio totale delle metriche per l'elemento selezionato nel report Panoramica per l'ultimo N minuti. N è configurabile mediante il selettore Intervallo ora. |
   | **Reportlet secondario correlato 1** | Questo minirapporto è molto simile a quello di Secondaria 1. L'unica differenza è rappresentata dall'origine dati utilizzata per compilare il rapporto: in questo esempio mostra la correlazione (o suddivisione) tra una pagina specifica (quella selezionata nel minirapporto principale del rapporto Panoramica) e le istanze visualizzate. |
   | **Reportlet secondario correlato 2** | Questo minirapporto è molto simile a quello di Secondaria 2. L'unica differenza è rappresentata dall'origine dati utilizzata per compilare il rapporto: in questo esempio mostra la correlazione (o suddivisione) tra una pagina specifica (quella selezionata nel minirapporto principale del rapporto Panoramica) e la dimensione della lingua. |
