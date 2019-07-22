---
description: nulle
seo-description: nulle
seo-title: Panoramica di Contribution Analysis
title: Panoramica di Contribution Analysis
uuid: 2 bd 295 b 0-c 5 ce -4443-86 af -024 efd 20 c 021
translation-type: tm+mt
source-git-commit: d3aecc01bc490018c3878f0f6c4dbd621ad35a01

---


# Panoramica di Contribution Analysis

Analisi contributi rileva i pattern nascosti all'interno dei dati per spiegare le anomalie statistiche e identificare le correlazioni dietro azioni impreviste del cliente, valori out-of-bind e improvvisi picchi o centesimi per metriche selezionate su segmenti di pubblico convergenti.

Si è verificato un problema. Perché? Il rapporto Rilevamento anomalie mostra un picco insolito negli ordini e si desidera conoscerne il motivo. Cosa è uscito dall'ordinaria? Chi risponde a quale campagna o riferimento? Qualcosa è diventato virale? Quali sono i fattori specifici che hanno contribuito a tale anomalia? E, probabilmente, importante: Come posso fare per acquisire informazioni importanti sul mio cliente e ripetere queste prestazioni? (O se si è verificato un calo in una metrica o in una metrica negativa, come si può evitare in futuro?)

Analisi contributi consente di valutare immediatamente i dati per rispondere a un'anomalia. Consente di suddividere i contributi a un'anomalia in secondi in quanto tempo impiega settimane, fornire pattern per segmenti di pubblico e aiutarti a sviluppare una narrazione per le interazioni dei clienti. Potete utilizzare l'analisi dei contributi per identificare e acquisire le associazioni significative per sviluppare nuovi segmenti di pubblico, oppure utilizzarli in modo tattico per identificare attività out-of-bound o fraudolenti che attivano un avviso.

[Il rilevamento](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) delle anomalie identifica picchi di dati e dip statistici estremi in base alle metriche selezionate e ai segmenti di pubblico selezionati. Imposta una regola storica basata su un periodo di formazione, quindi traccia gli offreset estremi correlati a eventi specifici. Può riportare un'escalation rapida di una metrica di Ordini positiva o di un incremento di metriche negative Bounce o di un incremento in entrambe, acquisendo punti dati statisticamente rilevanti da valutare tramite Analisi contributi. Una volta identificato un'anomalia statistica, Analisi contributi permette di analizzare e valutare le variabili di marketing e campagne rilevanti in tutti i punti dati anomali. Consente di eseguire algoritmi avanzati e processi di machine-learning per valutare le associazioni che hanno contribuito a un picco o a una dip significativi. Questi calcoli vengono quindi visualizzati nelle visualizzazioni interattive progettate per fornire diverse prospettive, in modo da fornire una risposta a quanto è accaduto e cosa fare al riguardo.

Analisi contributi consente di sviluppare un commento per descrivere il motivo per cui si è verificata un'anomalia e come rispondervi, acquisire metriche rilevanti e identificare punti nascosti che offrono un motivo complessivo per interazioni con l'audience e interesse dei clienti. A volte un'anomalia è facile da visualizzare e correggere, ad esempio un ordine errato per 2,000 kayak. A volte è complesso, come individuare una tendenza emergente in un periodo di tempo in un'area che reagisce solo a una campagna specifica. La possibilità di suddividere insieme gli elementi per diverse metriche per diverse dimensioni e le rispettive associazioni offre un'idea generale delle interazioni con l'audience e contribuisce a fornire contesto per i punti dati anomali.

Ecco alcune idee:

* Marketing delle identità potenziale monitorando le modifiche nella domanda del prodotto.
* Migliorare l'esperienza dei clienti reagendo a interessi specifici del pubblico.
* Identificare gli ordini fraudolenti anticipatamente come rapporto out-of-bounds.
* Proteggersi dall'analisi aziendale identificando l'utilizzo e i download elevati.
* Monitorare le operazioni quali il reporting di tag javascript mancanti.

Dopo un'analisi completa di un'anomalia, viene generato un Riepilogo contributi per gli elementi principali ordinati dalle occorrenze totali e dalla percentuale dell'elemento dei valori che hanno contribuito. Un punteggio contributo normalizzato consente di confrontare, confrontare e associare facilmente altri elementi dimensionali significativi.

## Contribution Analysis Tokens - overview {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

>[!IMPORTANT]
>
>Analisi contributi è stata rimossa dal set di funzioni Reporting e analisi ed è ora disponibile solo tramite Analysis Workspace.

Tutti i clienti con adesione ad Analisi contributi possono eseguire un’analisi completa dei contributi per un numero limitato di volte al mese in Analysis Workspace. Ciò **esclude** i clienti di prodotti singoli (SiteCatalyst 15), i clienti di Analytics Foundation e i clienti di Analytics Select, che non hanno alcun accesso all’analisi dei contributi.

Il numero di esecuzioni per azienda dipende dal numero di token mensili assegnati in base al prodotto Adobe Analytics acquistato dalle singole aziende. Ciò include la possibilità di limitare la funzione di analisi dei contributi per evitare l’uso improprio dei token.

## Domande frequenti {#section_11D0431AD2014B96AB9561CA66A367CE}

<table id="table_357775E5058644099E26B15A6790E8AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Domanda </th> 
   <th colname="col2" class="entry"> Risposta </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Perché Adobe ha introdotto i token? </b> </p> </td> 
   <td colname="col2"> <p>La funzione Analisi contributi di Adobe Analytics ha riscosso un grande successo dal rilascio iniziale nel 2015. La possibilità di disporre di un numero limitato di esecuzioni “complete” al mese (anziché 3 sole dimensioni per alcuni prodotti Analytics) consente di comprendere meglio i risultati ottenibili dall’analisi completa e illimitata dei contributi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Come funziona l’utilizzo dei token nell’analisi dei contributi? È necessario spendere un token per caricare un progetto con un’analisi dei contributi esistente oppure è richiesto solo se si esegue una nuova analisi?</b> </p> </td> 
   <td colname="col2"> <p>Ad ogni azienda per la quale si esegue l’accesso (non a ciascun utente) viene assegnato un determinato numero di token al mese, che consente di eseguire analisi dei contributi “complete” in Analysis Workspace. </p> <p>Ogni volta che si genera una nuova analisi dei contributi si paga un token. Quando si caricano progetti con analisi dei contributi preesistenti non viene richiesto alcun token. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>I token si applicano anche all’analisi dei contributi in Reports &amp; Analytics?</b> </p> </td> 
   <td colname="col2"> <p>No. La funzione Analisi contributi non è più offerta in Reports &amp; Analytics a partire dalla release di aprile 2018. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Cosa devo fare se la mia azienda ha esaurito i token ma intende eseguire altre analisi dei contributi?</b> </p> </td> 
   <td colname="col2"> <p>Si può eseguire l’aggiornamento a un altro prodotto Adobe Analytics, ad esempio da Standard (2 token al mese) a Ultimate (20 token al mese). Non è contemplato il solo acquisto di altri token; è necessario eseguire l’aggiornamento all’interno del framework del pacchetto esistente. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Come si limita l’accesso all’analisi dei contributi?</b> </p> </td> 
   <td colname="col2"> <p>By default, only admins have access to run Contribution Analyses, but admins can grant access to other users by creating a permission group in the <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html" format="html" scope="external"> Admin Console </a>. È consigliabile autorizzare l'uso dell'analisi dei contributi solo agli utenti che hanno un motivo legittimo per utilizzarlo e sono considerati affidabili per non approfittare dell'accesso. </p> <p>Il titolo dell’autorizzazione è “Contribution Analysis” (Analisi contributi), alla voce <span class="ignoretag"><span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Admin (Amministratore)</span> &gt; <span class="uicontrol">User Management (Gestione utente)</span> &gt; <span class="uicontrol">Edit Groups (Modifica gruppi)</span> &gt; <span class="uicontrol">Edit All Report Access (Modifica accesso a tutti i rapporti)</span> &gt; <span class="uicontrol">Customize Report Suite Tools (Personalizza strumenti della suite di rapporti)</span> &gt; <span class="uicontrol">Tools And Reports (Strumenti e rapporti)</span></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Come faccio per sapere a quanti token ha diritto mensilmente la mia azienda e quanti ne abbiamo utilizzati nel mese in corso?</b> </p> </td> 
   <td colname="col2"> <p>Vai a <span class="ignoretag"><span class="uicontrol">Admin (Amministratore)</span> &gt; <span class="uicontrol">Company Settings (Impostazioni società)</span> &gt; <span class="uicontrol">View Feature Access Levels (Visualizza funzione livelli di accesso)</span></span>. Su questa pagina sono presenti 2 nuovi elementi: </p> <p><img placement="break"  src="assets/ca_access_level.png" id="image_16012FE1162C485EA768D175F43D7563" width="500px" /> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Anomaly Detection and Contribution Analysis entitlements {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

Di seguito è riportato un elenco dettagliato delle adesioni disponibili per Rilevamento delle anomalie e Analisi contributi in Analysis Workspace.

>[!IMPORTANT]
>
>Le funzioni Rilevamento delle anomalie e Analisi contributi sono state rimosse da Reports &amp; Analytics e sono ora disponibili solo in Analysis Workspace. I clienti Select e Foundation di Adobe Analytics possono accedere solo alla funzione Rilevamento anomalie con granularità giornaliera in Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adesione Adobe Analytics </th> 
   <th colname="col2" class="entry"> Rilevamento delle anomalie </th> 
   <th colname="col3" class="entry"> Analisi contributi </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Foundation </p> </td> 
   <td colname="col2"> <p>Solo granularità giornaliera </p> </td> 
   <td colname="col3" colsep="1"> <p>Nessun token </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other" format="html" scope="external"> Select </a> </p> </td> 
   <td colname="col2"> <p>Solo granularità giornaliera </p> </td> 
   <td colname="col3"> <p>Nessun token </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other" format="html" scope="external"> Prime </a> </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>10 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other" format="html" scope="external"> Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>20 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>+Predictive Workbench </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>Token illimitati </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">Adobe Analytics OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">Adobe Analytics MA </li> 
    </ul> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>2 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360, Attribution) </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>2 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Complete, <a href="https://www.adobe.com/data-analytics-cloud/analytics/predictive-intelligence.html" format="html" scope="external">Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>Token illimitati </p> </td> 
  </tr> 
 </tbody> 
</table>
