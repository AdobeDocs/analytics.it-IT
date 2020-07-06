---
description: Passaggi sull'esecuzione dei diversi tipi di rapporto.
title: Eseguire diversi tipi di rapporto
topic: Reports,Reports and analytics
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '2276'
ht-degree: 5%

---


# Eseguire diversi tipi di rapporto

Passaggi sull&#39;esecuzione dei diversi tipi di rapporto.


## Eseguire un report classifica {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In un rapporto con classifica, la tabella mostra le classificazioni delle pagine del rapporto in relazione alla metrica, in base al numero o alla percentuale. I report Ranked possono mostrare più metriche in uno stesso report.

<!-- 

t_reports_ranked.xml

 -->

1. Generate un rapporto, ad esempio [!UICONTROL Pages Report] ( **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**).
1. Nell’intestazione del rapporto, fai clic su **[!UICONTROL Ranked.]**
1. Per classificare il rapporto, fare clic sull&#39;intestazione di una colonna nella tabella.

   I rapporti con classifica possono contenere fino a 200 elementi elencati nella tabella (quali prodotti, categorie, pagine Web e così via) e dieci metriche (ricavi, ordini, viste e così via).

## Eseguire un report con tendenze {#task_F03B4E760B9E4EA29FC3F654E6316887}

I report con tendenze mostrano le metriche nel tempo. Puoi utilizzare questo tipo di report quando desideri sapere quali sono le prestazioni di un segmento da un periodo di tempo al successivo.

<!-- 

t_reports_trended.xml

 -->

La maggior parte dei report Conversione e Traffico dispone di una visualizzazione con tendenze. Utilizzando [!UICONTROL Calendar], puoi mostrare miglioramenti per suddivisioni temporali, compresi giorni di un mese, settimane di un anno, settimane di un trimestre, mesi di un anno e così via. I rapporti con tendenze mostrano le tendenze per una metrica singola (ricavi, ordini, viste e così via) fino a cinque elementi (come prodotti, categorie, pagine Web e così via).

**Per eseguire un report con tendenze**

1. Eseguite un rapporto di conversione o di traffico, ad esempio **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Alla voce **[!UICONTROL Report Type]**, fai clic su **[!UICONTROL Trended.]**

## Eseguire un rapporto sull&#39;imbuto di conversione {#task_B926A74AA6A641138C2986C1635120CB}

I rapporti sul funnel di conversione mostrano la percentuale di visitatori che hanno fatto avanzare un insieme di eventi per eseguire l&#39;azione desiderata. Ad esempio, potete vedere quanti visitatori hanno progredito dalla visita alla pagina Web, dall&#39;aggiunta di elementi al carrello e dall&#39;acquisto di un elemento. Questo rapporto mostra anche il numero di coloro che sono caduti lungo la strada.

<!-- 

t_reports_conversion_funnel.xml

 -->

Per eseguire questo rapporto, selezionare un rapporto, ad esempio un rapporto Pagine ( **[!UICONTROL Reports]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Tracking Code]** > **[!UICONTROL Campaign Conversion Funnel]**).

Per una descrizione, consulta Report [](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-conversion.html) conversione.

## Eseguire un rapporto di abbandono {#task_8FD97C8260464F9DA731A93DB8F80184}

Mostra [!UICONTROL Fallout Report] il numero di visitatori che hanno visitato una sequenza di pagine precedentemente specificata. Vengono inoltre visualizzati i tassi di conversione e di abbandono tra ciascun passaggio.

<!-- 

t_reports_fallout.xml

 -->

Scopri il nuovo pannello Analisi [](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) abbandono in  Analysis Workspace!

1. In [!UICONTROL Adobe Analytics], fate clic su **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Fallout]**.
1. On the [!UICONTROL Fallout Report] page, click **[!UICONTROL Launch the Fallout Report Builder]**.

   ![Risultato passaggio](assets/fallout_add_items.png)

1. Nella [!UICONTROL Define Checkpoints] pagina, specificate i punti di controllo da utilizzare per il rapporto.
1. Fai clic su **[!UICONTROL Run Report]** (Crea).

   ![Risultato passaggio](assets/fallout_report.png)

>[!MORELIKETHIS]
>
>* [Descrizione rapporto di fallout](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-fallout.html)


## Eseguire un rapporto sul flusso di pagina {#task_133E8B87C3F04DA0A42D10CBA499305B}

I rapporti sul flusso di pagina mostrano l’ordine in cui i visitatori accedono alle pagine e si spostano nel sito. Questo rapporto aiuta a rispondere

Scopri la nuova visualizzazione [](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) Flusso in  Analysis Workspace!

Eseguire un rapporto [Percorsi](https://docs.adobe.com/content/help/it-IT/analytics/components/variables/dimensions-reports/reports-paths.html) .

Ad esempio, fare clic su **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Next Page Flow]**.

![](assets/page_flow.png)

Il rapporto viene letto da sinistra a destra, a partire dalla pagina selezionata. Le pagine visualizzate dopo la pagina selezionata sono illustrate come un ramo che si estende a destra.

La percentuale di visualizzazione di ogni pagina successiva viene visualizzata accanto al nome della pagina. La larghezza della linea collegata a ciascuna pagina successiva rappresenta questa percentuale relativa.

**[!UICONTROL Path Views]**: Indica il numero di volte in cui è stata visualizzata una pagina, se vincolata ai percorsi visualizzati.

Ad esempio, la pagina dell&#39;Informativa sulla privacy potrebbe avere 10.000 visualizzazioni totali di pagina, ma solo 500 di queste si sono verificate immediatamente dopo la pagina principale. Viene quindi utilizzato il termine visualizzazione percorso.

La percentuale relativa è rappresentata dalla larghezza relativa della linea. Per impostazione predefinita, questo rapporto mostra cinque rami di secondo livello e cinque rami di terzo livello. È possibile espandere il numero di rami per visualizzare fino a dieci rami di secondo livello e cinque rami di terzo livello. In questo modo l&#39;altezza del rapporto aumenta e molto probabilmente richiede lo scorrimento per visualizzare l&#39;intero grafico.

## Eseguire un rapporto Funnel {#task_2BBF6FACD48F479E8B2EE458919941CB}

Potete selezionare eventi di successo e aggiungerli a un [!UICONTROL Purchase Conversion Funnel] rapporto o a un [!UICONTROL Product Conversion Funnel] rapporto.

<!-- 

t_reports_funnel.xml

 -->

1. Fate clic su **[!UICONTROL Reports]** > **[!UICONTROL Products]** > [Products Conversion Funnel (Funnel di conversione prodotti)](https://docs.adobe.com/content/help/en/analytics/components/variables/dimensions-reports/reports-conversion-funnel.html).

## Eseguire un report canale di marketing {#task_64ADED5CC75248319E06E3E029B47F78}

Il reporting sul canale di marketing fornisce una panoramica dell&#39;allocazione dei canali di primo e ultimo contatto, con metriche di reporting standard come entrate, ordini e costi. Questi rapporti consentono di analizzare il fatturato generato da ogni canale.

<!-- 

t_reports_marketing_channel.xml

 -->

Per ulteriori informazioni, consulta il sistema di aiuto [Marketing Channel](/help/components/c-marketing-channels/analyze-mc.md) .

## Eseguire un rapporto Rilevamento anomalie {#task_4808C96327354D789C075823F5C3A049}

Descrive come interpretare i grafici Riepilogo e Metrica singola in Rilevamento anomalie.

<!-- 

t_anomaly_view.xml

 -->

Scopri le nuove funzioni [Rilevamento anomalie e Analisi](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html) contributi di  Analysis Workspace!

**[!UICONTROL Reports]** > **[!UICONTROL Site Metrics]** > **[!UICONTROL Anomaly Detection]** .

>[!NOTE]
>
>È inoltre possibile eseguire il rilevamento delle anomalie direttamente  progetti Analysis Workspace. [Altro...](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html)

Per informazioni sulla configurazione del rilevamento delle anomalie, fare riferimento alla Guida di [riferimento](https://docs.adobe.com/content/help/en/analytics/analyze/reports-analytics/getting-started.html#Setting_up_Anomaly_Detection).

Il rilevamento delle anomalie mostra due tipi di grafici: Un grafico di riepilogo e singoli grafici di metriche. I singoli grafici delle metriche vengono visualizzati solo se per tale metrica è stata rilevata almeno un’anomalia.

<table id="table_88163CD8FC164342855D90D01F9C581A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Tipo di grafico </p> </th> 
   <th colname="col2" class="entry"> <p>Cosa fa </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Riepilogo </p> <p><img placement="break"  src="assets/ad_summary_chart.png" width="570px" id="image_1CD4C4770BAA43C4AD7CBB824AD41338" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_D26DA3024CD7468291369F549557B28A"> 
      <li id="li_1C22B6E02FFB479FB71EFAD89EB37A4E">Ogni casella rappresenta un'anomalia, tracciata ogni giorno, che corrisponde a una metrica sottostante. </li> 
      <li id="li_8FC587D3FF4E452D83263CC7A10B6675">Il verde indica anomalie sopra la linea di tendenza, il blu sotto la linea di tendenza. </li> 
      <li id="li_25135AB691BF443599AF2A3A60E2E71A">Indica l'intensità dell'anomalia: Maggiore è l’anomalia, più scuro è il colore del punto dati e più lontano dalla linea di tendenza. </li> 
      <li id="li_0C42AFA8897D420D8AB1A5D0F65B3B3A">Facendo clic sulle singole anomalie, il grafico delle singole metriche di quell'anomalia (sotto il grafico di riepilogo) viene visualizzato in alto. </li> 
      <li id="li_85C0F426952547B5A75D6BD31DE19CA5">I valori percentuali di deviazione (a sinistra del grafico) sono calcolati come segue: 
       <ul id="ul_BEC0A88BFFAC4CF78BC9885FEB749694"> 
        <li id="li_1BAB2F50482745B69937DFAF1E09982E">Se i limiti superiori e il valore previsto sono uguali, la deviazione % è 100% </li> 
        <li id="li_CA48064F5788448C8646CCE196161237">In caso contrario, la deviazione % è ((valore effettivo - valore associato superiore) / (valore associato superiore - valore previsto) * 100 </li> 
        <li id="li_4090357A0D214BC7B1C3DE0615875554">Se i limiti inferiori e il valore previsto sono uguali, la deviazione % è -100% </li> 
        <li id="li_EF694E1A4E874ECD94E1E8F7302E494F">In caso contrario, la deviazione % è ((valore associato inferiore - valore effettivo) / (valore previsto - valore associato inferiore) * -100 </li> 
       </ul> </li> 
      <li id="li_5C05EF7023484CC993E96D63E842B65C">Facendo clic su <span class="uicontrol"> Mostra segmenti </span> viene visualizzata la barra laterale del segmento che consente di applicare segmenti a un rapporto di rilevamento delle anomalie. <a href="https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html"  > Ulteriori informazioni </a> sulla segmentazione. </li> 
      <li id="li_1B41CABF13D1407886C68EE3BC201E60">Facendo clic su <span class="uicontrol"> Modifica metriche </span>puoi selezionare e deselezionare le metriche per le quali desideri rilevare delle anomalie. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Grafico singolo </p> <p><img placement="break"  src="assets/metric_report.png" width="570px" id="image_5BBECFD91CF14478AA4761E6256BBCB9" /> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_739C5687013743A29B63089FDA763F45"> 
      <li id="li_456A0BDA4D4E46CE9CC1C3DBAA1E2220">Visualizza punti dati anomali per singole metriche con tendenze (comprese le metriche calcolate) sotto forma di punti. </li> 
      <li id="li_89FD847C65F04F48BCA7CD38D0EC51CD">Mostra l’anomalia più recente in alto e, in secondo luogo, classifica per numero di anomalie. </li> 
      <li id="li_98B97A9706DE4455B8D8850904CBDE03">Visualizza una linea continua per indicare i dati effettivi attualmente raccolti. Questo viene confrontato con la previsione e il margine di errore per determinare se i punti dati sono anomali. </li> 
      <li id="li_0EEA38DDDC344BF3879430E67D74EB72">Visualizza una linea tratteggiata che rappresenta una previsione basata su dati storici (ovvero il periodo di formazione). </li> 
      <li id="li_035BD2725D004AEDB630BF8DFF4DA4F3">Visualizza intervalli/limiti di confidenza superiori e inferiori al 95% in un'ombreggiatura grigia. </li> 
      <li id="li_021A3D1F2EDB4319B9B39620EF1C038A">Consente di comprimere ed espandere i singoli rapporti facendo clic sulle frecce verso l’alto o il basso accanto al nome della metrica. </li> 
      <li id="li_722E4B9FC21047AC96D7B143197E293D">Modifica l’ordine in cui i grafici delle metriche vengono visualizzati reagendo alle analisi approfondite nel rapporto della panoramica (vedi sopra). </li> 
      <li id="li_A2441169B185475AA68A64F81E6E40B8">Consente di filtrare i grafici utilizzando termini di ricerca, ad esempio "pagina" per tutte le metriche relative alle pagine. </li> 
      <li id="li_F1BBBFCA8E2A43C29658E4FCAA36C904">Consente di visualizzare tutte le metriche definite o solo quelle con anomalie. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Impostazione del rilevamento delle anomalie {#task_AF347B34F56E44A6AE70E019B6EB2F08}

Passaggi per selezionare suite di rapporti, metriche e periodi di formazione/visualizzazione per il rilevamento delle anomalie.

<!-- 

t_anomaly_config.xml

 -->

Potete impostare il rilevamento delle anomalie in modo indipendente per ogni suite di rapporti.

1. Passa a  **[!UICONTROL Analytics > Reports > Site Metrics > Anomaly Detection]** .
1. Selezionate la suite di rapporti per la quale desiderate tenere traccia del rilevamento giornaliero delle anomalie. Per visualizzare un elenco di suite di rapporti, fai clic sul menu a discesa del selettore Suite di rapporti.
1. Per selezionare le metriche e/o definire le metriche filtrate, fai clic **[!UICONTROL Edit Metrics]** in alto a destra nella schermata:  ![](assets/metrics_icon.png).

   Puoi scegliere le metriche dall&#39;elenco (comprese le metriche calcolate) di tutte le metriche o da un elenco di metriche tracciate. Potete anche filtrare l’elenco in base a termini specifici. 1. Una volta generato il rapporto, definisci il **[!UICONTROL Training Period]** e il **[!UICONTROL View Period]** metodo di rilevamento delle anomalie. (Pensate al periodo di formazione come al &quot;periodo di apprendimento&quot; per l’algoritmo.)

   ![](assets/view_training_periods.png)

   Nota bene:

* Il periodo di formazione termina immediatamente prima dell&#39;inizio del periodo di visualizzazione.
* Il valore predefinito per entrambi è 30 giorni e potete estenderlo a 60 o 90 giorni.
* Estendendo il periodo di formazione i dati vengono inseriti in un contesto più ampio e possono ridurre le dimensioni di un’anomalia.

   Il rapporto sulle metriche di rilevamento delle anomalie viene aggiornato ogni volta che si modifica un parametro.
1. (Facoltativo) Per applicare segmenti al rapporto, fai clic su **[!UICONTROL Show Segments]** e seleziona uno o più segmenti esistenti o crea un nuovo segmento e applicalo.

   ![](assets/ad_top_menu.png)

   Per ulteriori informazioni sulla creazione e la gestione dei segmenti, consulta la [Guida](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/seg-home.html) alla segmentazione di Analytics. 1. (Facoltativo) Preferito o segnalibro per il rapporto.
1. (Facoltativo) Modificare la data di fine del periodo di visualizzazione. Il valore predefinito è ieri.
1. È ora possibile iniziare a interpretare il rapporto. [Visualizzazione dei grafici](/help/analyze/reports-analytics/t-running-report-types.md#task_4808C96327354D789C075823F5C3A049)di rilevamento delle anomalie.

## Eseguire un rapporto in tempo reale {#task_5D25929C918E40B18965222FA94176B0}

Descrive come visualizzare e interpretare i rapporti in tempo reale.

<!-- 

reports_realtime.xml

 -->

**[!UICONTROL Reports > Site Metrics > Real-Time]** .

Il reporting in tempo reale offre due report principali: un report di panoramica e un report dettagliato. Ciascuno di essi è costituito da una serie di minirapporti.

Per informazioni sulla configurazione di rapporti in tempo reale, consulta la [Guida](https://docs.adobe.com/content/help/en/analytics/landing/home.html#RealTime_Reports_Configuration)di riferimento di Analytics.

1. Guardate il **[!UICONTROL Overview]** rapporto e i suoi componenti:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Componente interfaccia </th> 
   <th class="chdeschd"> Descrizione </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleziona suite di rapporti</strong></td> 
   <td class="chdesc stentry"> Mostra la suite di rapporti cui si riferisce il rapporto in tempo reale. Per modificare la suite di rapporti, vedi <a href="https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/real-time-reports/t-realtime-admin.html"  > Real-Time Reports Configuration </a>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Passa tra i rapporti</strong></td> 
   <td class="chdesc stentry"> Consente di passare ai rapporti impostati (massimo 3). </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleziona intervallo di tempo</strong></td> 
   <td class="chdesc stentry"> Consente di scegliere l'intervallo di tempo complessivo da utilizzare per tutti i minirapporti del rapporto. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Configurare i rapporti</strong></td> 
   <td class="chdesc stentry"> Questo collegamento dell'icona a forma di ingranaggio è visibile solo se disponete dei diritti di amministratore. Fai clic su di esso per accedere al Gestore delle suite di rapporti in <span class="ignoretag"> Strumenti di amministrazione <span class="uicontrol"> &gt; </span> Suite di rapporti <span class="uicontrol"> &gt; </span> Modifica impostazioni <span class="uicontrol"> &gt; </span> Real-Time <span class="uicontrol"> </span> </span>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Visualizzazione a schermo intero</strong></td> 
   <td class="chdesc stentry"> L’icona della visualizzazione a schermo intero è visibile solo se il monitor ha proporzioni specifiche (16:9 o 16:10) E se il browser lo supporta. Non è possibile interagire con lo schermo in modalità a schermo intero (premere <span class="uicontrol"> Esc </span> per uscire). La modalità a schermo intero non si interrompe. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Report sul traffico del sito</strong></td> 
   <td class="chdesc stentry"> I dati blu della linea di tendenza mostrano il totale del traffico per il sito complessivo. L'asse X utilizza etichette letterali (15 minuti fa, 10 minuti fa) tranne che per il valore corrente, che viene visualizzato come espressione in tempo reale. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Report Totale sito</strong></td> 
   <td class="chdesc stentry"> Mostra un conteggio del totale del sito per la metrica selezionata del report in tempo reale per gli ultimi N minuti. "N" è configurabile tramite il selettore Intervallo di tempo. <p>Il colore e la direzione della freccia si basano sul seguente algoritmo: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Guadagno significativo (freccia su): &gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Guadagno (freccia su destra): tra il 5 % e il 100 % </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Piatta (freccia destra): tra 5% e -5% </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Perdita (freccia giù destra): tra -5% e -100% </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Perdita significativa (freccia Giù): &lt; -100% </li> 
      </ul> </p> <p>Se il totale del sito è riportato in "istanze", queste istanze riflettono la dimensione nel minirapporto principale. Se esiste un nome specifico per l’istanza (ad esempio "Visualizzazioni pagina"), il totale del sito riporta tale nome. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Report principale</strong></td> 
   <td class="chdesc stentry"> Report per la dimensione principale del report in tempo reale e per la relativa metrica. Mostra una linea di tendenza per l'elemento per l'intervallo di tempo selezionato. Il totale della metrica rappresenta la somma per l'intera linea di tendenza. La freccia indica se l'elemento sta guadagnando, guadagnando, piatta, perdendo o fortemente perdendo. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Finestra di dialogo Ricerca</strong></td> 
   <td class="chdesc stentry"> La ricerca interessa tutti i minirapporti. La ricerca persiste quando si visualizza il rapporto. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Ordina per... Più popolari/Gainer/Perdite</strong></td> 
   <td class="chdesc stentry"> Potete impostare l’ordinamento per <span class="uicontrol"> Più popolare </span>(impostazione predefinita), <span class="uicontrol"> Gainer </span> (dimensioni che mostrano la maggior crescita) e <span class="uicontrol"> Perdite </span> (dimensioni che si trovano su una traiettoria verso il basso). <p>Di seguito è riportata la formula utilizzata per determinare gli utili o i perdenti: In tempo reale esamina il primo esempio e il successivo all'ultimo ed esegue un semplice calcolo di "% change". Quindi se è selezionata l'opzione "Ultimi 15 minuti" e n rappresenta il minuto corrente, n-1 viene confrontato con n-15. In tempo reale non viene attualmente applicata alcuna ponderazione. Il minuto corrente viene ignorato perché non è completo e potrebbe generare una modifica percentuale errata. </p> <p>Questa formula è coerente tra tutte le metriche utilizzate nel report in tempo reale. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Report secondario 1</strong></td> 
   <td class="chdesc stentry"> Presenta report in tempo reale per la dimensione del secondo report con provisioning e per la metrica. <p>Il rapporto secondario 1 mostra le prime quattro categorie; il quinto è un'aggregazione di tutti i valori rimanenti. Per ogni categoria, viene fornita la visualizzazione non elaborata totale di tale categoria. Inoltre, il totale per tutte le categorie è riportato al centro. </p> <p> Quando si passa il puntatore del mouse su una sezione viene evidenziata la categoria associata e viene visualizzata la linea di tendenza della categoria sotto la ciambella. </p> <p> Quando si passa il puntatore del mouse su un elemento di riga, l'elemento di riga più la sezione associata viene evidenziato e la linea di tendenza della categoria viene visualizzata sotto l'elemento di ciambella. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Report secondario 2</strong></td> 
   <td class="chdesc stentry"> Presenta report in tempo reale per la dimensione del terzo rapporto con provisioning e per la metrica. Quando si passa il puntatore del mouse sopra l'etichetta dell'elemento, l'etichetta viene scivolata a destra e viene visualizzata una linea di tendenza per l'elemento sul quale si trova il puntatore del mouse. </td> 
   </tr> 
   </table>

1. Fate clic su una voce di elenco nel minirapporto principale per avviare la **[!UICONTROL Details]** visualizzazione della voce di elenco:  ![](assets/rtr_detail_report.png)

   | **Report tendenze articolo** | Mostra la linea di tendenza dell’elemento selezionato nel rapporto Panoramica per gli ultimi N minuti. N è configurabile tramite il selettore Intervallo di tempo. |
   |---|---|
   | **Report Totale articolo** | Mostra un conteggio totale delle metriche per l&#39;elemento selezionato nel report Panoramica per gli ultimi N minuti. N è configurabile tramite il selettore Intervallo di tempo. |
   | **Report secondario 1 correlato** | Questo rapporto è molto simile al report secondario 1. L&#39;unica differenza è l&#39;origine dati utilizzata per compilare il report: in questo esempio, mostra la correlazione (o suddivisione) tra una pagina specifica (quella selezionata nel minirapporto principale del rapporto Panoramica) e le istanze visualizzate. |
   | **Report secondario correlato 2** | Questo rapporto è molto simile al report secondario 2. L&#39;unica differenza è l&#39;origine dati utilizzata per compilare il report: in questo esempio, mostra la correlazione (o suddivisione) tra una pagina specifica (quella selezionata nel minirapporto principale del rapporto Panoramica) e la dimensione della lingua. |
