---
description: Passaggi per l’esecuzione dei diversi tipi di rapporto.
title: Eseguire diversi tipi di rapporto
uuid: f59ab2a1-e916-46e8-bb5b-e6361ba00dda
feature: Reports & Analytics Basics
role: User, Admin
exl-id: 2e8cac1b-d133-4095-b5db-886ce0566b82
source-git-commit: 2bb3cc1ce46fc8e5f7e15291401fce1c4d8cb839
workflow-type: tm+mt
source-wordcount: '1036'
ht-degree: 3%

---

# Eseguire diversi tipi di rapporto

{{ra-eol}}

In Analysis Workspace puoi eseguire molti tipi diversi di rapporti. Di seguito sono riportati alcuni esempi.

Per un elenco completo dei tipi di rapporto predefiniti disponibili, consulta [Utilizzare rapporti predefiniti](/help/analyze/analysis-workspace/reports/use-reports.md)

<!-- How do you do a Ranked Report in Workspace?

## Run a ranked report {#task_C570BA4A213F4F2EB7B30E012934BE7D}

In a ranked report, the table shows the rankings of the report pages in relation to the metric, according to number or percentage. Ranked reports can display multiple metrics in a report.

1. Generate a report, such as a [!UICONTROL Pages Report] ( [!UICONTROL **Workspace**] > **[!UICONTROL Engagement]** > **[!UICONTROL Pages]**).
1. In the report header, click **[!UICONTROL Ranked.]**
1. To rank the report, click a column heading in the table.

   Ranked reports can have up to 200 items listed in the table (such as products, categories, web pages, and so on) and ten metrics (revenue, orders, views, and so on).

-->

<!-- Can you do a Trended report? 

## Run a trended report {#task_F03B4E760B9E4EA29FC3F654E6316887}

Trended reports display metrics over time. You use this report type when you want to see how a segment performs from one time period to the next.

Most Conversion and Traffic reports have a Trended view available. Using the [!UICONTROL Calendar], you can show improvement for any time period breakdowns, including days of a month, weeks of a year, weeks of a quarter, months of a year, and so on. Trended reports show trends for a single metric (revenue, orders, views, and so on) for up to five items (such as products, categories, web pages, and so on).

**To run a trended report** 

1. Run a conversion or traffic report, such as **[!UICONTROL Reports]** > **[!UICONTROL Site Content]** > **[!UICONTROL Pages]**.
1. Under **[!UICONTROL Report Type]**, click **[!UICONTROL Trended.]**

-->

## Eseguire un rapporto di fallout {#task_8FD97C8260464F9DA731A93DB8F80184}

Il [!UICONTROL Fallout Report] mostra il numero di visitatori che hanno visitato una sequenza di pagine predefinita. Mostra anche i tassi di conversione e di abbandono tra ogni passaggio.

Scopri la nuova [Analisi dell’abbandono](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html?lang=it) in Analysis Workspace.

1. In entrata [!UICONTROL Adobe Analytics], fai clic su **[!UICONTROL Reports]** > **[!UICONTROL Paths]** > **[!UICONTROL Pages]** > **[!UICONTROL Fallout]**.
1. Nella pagina [!UICONTROL Fallout Report] fai clic su **[!UICONTROL Launch the Fallout Report Builder]**.

1. Il giorno [!UICONTROL Define Checkpoints] , specificare i punti di controllo che si desidera utilizzare per il report.
1. Fai clic su **[!UICONTROL Run Report]** (Usa modello di attribuzione non predefinito).

## Eseguire un rapporto Flusso di pagina {#task_133E8B87C3F04DA0A42D10CBA499305B}

I rapporti Flusso di pagina mostrano l’ordine in cui i visitatori accedono alle pagine e navigano nel sito. Questo rapporto aiuta a rispondere

Ad esempio, fai clic su **[!UICONTROL Workspace]** > **[!UICONTROL Reports]** > **[!UICONTROL Engagement]** > **[!UICONTROL Next and previous page flow]**.

## Eseguire un rapporto sul canale di marketing {#task_64ADED5CC75248319E06E3E029B47F78}

Il reporting sul canale di marketing fornisce un rapporto panoramico sull’allocazione del canale di primo e ultimo contatto, con metriche di reporting standard come ricavi, ordini e costi. Questi rapporti ti consentono di analizzare la quantità di ricavi generati da ogni canale.

Consulta la [Canale di marketing](/help/components/c-marketing-channels/analyze-mc.md) per ulteriori informazioni.

## Eseguire un rapporto sul rilevamento delle anomalie {#task_4808C96327354D789C075823F5C3A049}

È possibile eseguire [Rilevamento delle anomalie e analisi dei contributi](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/anomaly-detection/anomaly-detection.html?lang=it) solo in Analysis Workspace.

## Eseguire un rapporto in tempo reale {#task_5D25929C918E40B18965222FA94176B0}

Descrive come visualizzare e interpretare i rapporti in tempo reale.

**[!UICONTROL Reports > Site Metrics > Real-Time]** .

La generazione rapporti in tempo reale offre due rapporti principali: un rapporto di panoramica e un rapporto di dettaglio. Ognuno di essi è costituito da una serie di reportlet.

Consulta [Panoramica reportistica in tempo reale](/help/components/c-real-time-reporting/realtime.md) per ulteriori informazioni.

1. Dai un&#39;occhiata al **[!UICONTROL Overview]** rapporto e relativi componenti:  ![](assets/rtr_overview_report.png)

   <table id="choicetable_8586BECF55E843B2B5CD41205567EA32"> 
   <thead class="chhead sthead"> 
   <th class="choptionhd"> Componente interfaccia utente </th> 
   <th class="chdeschd"> Descrizione </th> 
   </thead> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleziona suite di rapporti</strong></td> 
   <td class="chdesc stentry"> Mostra la suite di rapporti coperta da questo rapporto in tempo reale. Per modificare la suite di rapporti, vedi <a href="https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/real-time-reports/t-realtime-admin.html"  > Configurazione rapporti in tempo reale </a>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Passare da un rapporto all’altro</strong></td> 
   <td class="chdesc stentry"> Consente di passare da un rapporto all’altro configurato (massimo 3). </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Seleziona intervallo di tempo</strong></td> 
   <td class="chdesc stentry"> Consente di scegliere l’intervallo di tempo complessivo da utilizzare per tutti i reportlet nel rapporto. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Configurare i rapporti</strong></td> 
   <td class="chdesc stentry"> Questo collegamento all’icona a forma di ingranaggio è visibile solo se disponi dei diritti di amministratore. Facendo clic su di esso si accede al Report Suite Manager in <span class="ignoretag"> <span class="uicontrol"> Strumenti di amministrazione </span>  &gt; <span class="uicontrol"> Suite di rapporti </span>  &gt; <span class="uicontrol"> Modifica impostazioni </span>  &gt; <span class="uicontrol"> Tempo reale </span> </span>. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Visualizzazione a schermo intero</strong></td> 
   <td class="chdesc stentry"> L'icona di visualizzazione a schermo intero è visibile solo se il monitor ha proporzioni specifiche (16:9 o 16:10) E se il browser lo supporta. Si noti che non è possibile interagire con lo schermo mentre è in modalità a schermo intero (premere <span class="uicontrol"> Esc </span> per uscire). La modalità a tutto schermo non si interrompe. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet traffico sito</strong></td> 
   <td class="chdesc stentry"> I dati della linea di tendenza blu mostrano il totale di traffico per il sito complessivo. L’asse X utilizza etichette letterali (15 minuti fa; 10 minuti fa) ad eccezione del valore corrente, che viene visualizzato come espressione in tempo reale. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet Totale sito</strong></td> 
   <td class="chdesc stentry"> Presenta un conteggio del totale del sito per la metrica selezionata del rapporto in tempo reale per gli ultimi N minuti. "N" è configurabile tramite il selettore Intervallo di tempo. <p>Il colore e la direzione della freccia si basano sul seguente algoritmo: 
      <ul id="ul_9F40CEA33798467393CB1266BB36D500"> 
      <li id="li_CCD01A44F912487DA5681EA50113643C">Guadagno significativo (freccia su): &gt; 100% </li> 
      <li id="li_7402491A9A614851B7F2AE0C77BD9A97">Guadagno (freccia su a destra): tra 5 % e 100% </li> 
      <li id="li_BCA79C08B5714D4B9315068112C66107"> Piatto (freccia destra): tra 5% e -5% </li> 
      <li id="li_234ECBD7D83A4AE680E4A70BF288681F"> Perdita (freccia giù a destra): tra -5% e -100% </li> 
      <li id="li_10C5EA8803604C1CA714D3DB27478B31"> Perdita significativa (freccia giù): &lt; -100% </li> 
      </ul> </p> <p>Se il totale del sito è riportato in "istanze", queste istanze riflettono la dimensione nel reportlet principale. Se esiste un nome specifico dell’istanza (ad esempio "Visualizzazioni pagina"), il totale del sito riporta tale nome. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet principale</strong></td> 
   <td class="chdesc stentry"> Rapporto per la dimensione principale del rapporto in tempo reale e per la relativa metrica. Visualizza una linea di tendenza per l'elemento per l'intervallo di tempo selezionato. Il totale della metrica rappresenta la somma per la linea di tendenza completa. La freccia indica se l'elemento sta guadagnando, guadagnando, piatta, perdendo o perdendo fortemente. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Finestra di dialogo di ricerca</strong></td> 
   <td class="chdesc stentry"> La ricerca ha effetto su tutti i reportlet. La ricerca persiste durante la visualizzazione del report. </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Ordina per... Più Popolari/Guadagnanti/ Perdenti</strong></td> 
   <td class="chdesc stentry"> Puoi scegliere di ordinare per <span class="uicontrol"> Più popolari </span>(impostazione predefinita), <span class="uicontrol"> Guadagni </span> (dimensioni che mostrano la crescita maggiore), e <span class="uicontrol"> Perdenti </span> (quote che si trovano su una traiettoria verso il basso). <p>Questa è la formula che viene utilizzata per determinare i guadagni o i perdenti: Real-Time esamina il campione più antico e quello successivo all'ultimo ed esegue un semplice calcolo di "% change". Pertanto, se è selezionato "Ultimi 15 minuti" e n rappresenta il minuto corrente, n-1 viene confrontato con n-15. Al momento, Real-Time non effettua alcuna ponderazione. Il minuto corrente viene ignorato perché non è completo e produrrebbe probabilmente una variazione % falsa. </p> <p>Questa formula è coerente in tutte le metriche utilizzate nel rapporto in tempo reale. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet secondario 1</strong></td> 
   <td class="chdesc stentry"> Presenta rapporti in tempo reale per la dimensione del secondo rapporto con provisioning e per la metrica. <p>Il reportlet secondario 1 mostra le prime 4 categorie; il quinto è un’aggregazione di tutti i valori rimanenti. Per ogni categoria viene fornita la visualizzazione totale non elaborata della categoria. Inoltre, il totale per tutte le categorie viene visualizzato al centro. </p> <p> Passando il puntatore del mouse su una sezione viene evidenziata la categoria associata e viene visualizzata la linea di tendenza della categoria sotto l'anello. </p> <p> Passando il puntatore del mouse su un elemento di riga viene evidenziata la riga più la sezione associata e viene visualizzata la riga di tendenza della categoria sotto l'anello. </p> </td> 
   </tr> 
   <tr class="chrow strow"> 
   <td class="choption"><strong>Reportlet secondario 2</strong></td> 
   <td class="chdesc stentry"> Presenta rapporti in tempo reale per la dimensione del terzo rapporto con provisioning e per la metrica. Passando il puntatore del mouse sopra l’etichetta dell’elemento, questa scorre verso destra e mostra una linea di tendenza per l’elemento che si trova al passaggio del mouse. </td> 
   </tr> 
   </table>

2. Fai clic su una voce di elenco nel reportlet principale per avviare **[!UICONTROL Details]** visualizzazione per la voce di elenco:  ![](assets/rtr_detail_report.png)

   | **Reportlet andamento articoli** | Visualizza la linea di tendenza dell&#39;elemento selezionato nel rapporto Panoramica per gli ultimi N minuti. N è configurabile tramite il selettore Intervallo di tempo. |
   |---|---|
   | **Reportlet Totale articoli** | Presenta un conteggio metrico totale per l’elemento selezionato nel rapporto Panoramica per gli ultimi N minuti. N è configurabile tramite il selettore Intervallo di tempo. |
   | **Reportlet secondario 1 correlato** | Questo reportlet è molto simile al Secondary 1 Reportlet. L’unica differenza è l’origine dati utilizzata per compilare il rapporto: in questo esempio viene mostrata la correlazione (o il raggruppamento) tra una pagina specifica (quella selezionata nel reportlet principale del rapporto Panoramica) e le istanze visualizzate. |
   | **Reportlet secondario 2 correlato** | Questo reportlet è molto simile al reportlet Secondary 2. L’unica differenza è l’origine dati utilizzata per compilare il rapporto: in questo esempio viene mostrata la correlazione (o il raggruppamento) tra una pagina specifica (quella selezionata nel reportlet principale del rapporto Panoramica) e la dimensione lingua. |
