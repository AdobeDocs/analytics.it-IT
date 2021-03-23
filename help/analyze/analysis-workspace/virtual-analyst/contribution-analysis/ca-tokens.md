---
description: Utilizza l’analisi dei contributi per identificare anomalie statistiche e correlazioni nei dati.
title: Panoramica dell’analisi dei contributi
uuid: 2bd295b0-c5ce-4443-86af-024efd20c021
translation-type: ht
source-git-commit: 5d8032a9806836e7d0ecbd7fa3652ed1fd137e89
workflow-type: ht
source-wordcount: '1156'
ht-degree: 100%

---


# Panoramica dell’analisi dei contributi

L’analisi dei contributi riconosce pattern nascosti nei dati per spiegare le anomalie statistiche e identificare le correlazioni alla base di azioni inaspettate da parte del cliente, valori fuori dalla norma e improvvisi picchi o ribassi di metriche selezionate su segmenti di pubblico convergenti.

Si è verificata un’anomalia. Perché? Il report della funzionalità di rilevamento delle anomalie mostra un picco insolito negli ordini e vuoi scoprirne il motivo. Cos’è successo di straordinario? Chi risponde a una determinata campagna o riferimento? Un contenuto è diventato virale? Quali sono i fattori specifici che hanno contribuito a questa anomalia? Forse l’informazione più importante: come posso acquisire informazioni critiche sul mio cliente e ripetere queste prestazioni? (Oppure, se si è verificato un calo in una metrica o un aumento in una metrica negativa, come posso evitarlo in futuro?)

L’analisi dei contributi consente di valutare immediatamente i dati per individuare la causa di un’anomalia. Suddivide i contributi in un’anomalia in pochi secondi anziché settimane come in precedenza, fornendo pattern per determinati segmenti di pubblico e aiutando a sviluppare un percorso delle interazioni dei clienti. È possibile utilizzare l’analisi dei contributi in modo strategico per identificare e acquisire associazioni significative e sviluppare nuovi segmenti di pubblico, oppure in modo tattico per identificare attività non associate o fraudolente che attivano un avviso.

[Rilevamento delle anomalie](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) identifica picchi di dati e cali statistici estremi in base a metriche selezionate e a segmenti di pubblico selezionati. Definisce una norma storica basata su un periodo di formazione, quindi traccia gli offset estremi correlati a eventi specifici. Può segnalare un aumento precipitoso in una metrica Ordini positiva o un aumento in una metrica Saldi negativa, oppure un calo in entrambe, acquisendo punti di dati statisticamente rilevanti che devono essere valutati dall’analisi dei contributi. Una volta identificata un’anomalia statistica, l’analisi dei contributi consente di approfondire e valutare le variabili di marketing e campagne rilevanti in tutti i punti di dati anomali. Esegue algoritmi avanzati e processi di machine-learning per valutare le associazioni che hanno contribuito a un picco o a un calo significativo. Questi calcoli vengono quindi mostrati tramite visualizzazioni interattive progettate per fornire prospettive diverse e aiutare a identificare le cause di un fenomeno e i possibili rimedi.

La funzione Analisi contributi consente di sviluppare una narrazione per descrivere la causa di un’anomalia e come trattarla, acquisendo metriche rilevanti e identificando punti nascosti che forniscono una panoramica delle interazioni del pubblico e degli interessi più comuni dei clienti. A volte un’anomalia è facile da identificare e correggere, come un ordine errato di 2.000 kayak. A volte è più complessa, come l’identificazione di una tendenza emergente in un periodo di tempo all’interno di una regione che reagisce solo a una campagna mirata specifica. La combinazione di elementi che contribuiscono alle metriche per diverse dimensioni e associazioni offre un’idea generale delle interazioni del pubblico e contribuisce a fornire contesto per punti di dati anomali.

Di seguito sono riportati alcuni casi di utilizzo:

* Identifica le opportunità di remarketing monitorando i cambiamenti nella domanda dei prodotti.
* Migliora l’esperienza del cliente reagendo a specifici interessi del pubblico.
* Identifica gli ordini fraudolenti sin da subito tramite report fuori limite.
* Previeni lo spionaggio aziendale identificando utilizzi e download elevati.
* Monitora operazioni quali la segnalazione di tag javascript mancanti.

Dopo un’analisi completa di un’anomalia, viene generato un riepilogo dei contributi contenente gli elementi principali ordinati per occorrenze totali e la percentuale dei valori contribuenti dell’elemento. Un punteggio di contributo normalizzato consente di confrontare, contrastare e associare facilmente elementi di dimensione significativa.

## Token di analisi dei contributi - Panoramica {#section_3EF8D2BBCE6E4C309D753BCF04A453D0}

>[!IMPORTANT]
>
>La funzione Analisi contributi è stata rimossa da Reports &amp; Analytics ed è ora disponibile solo tramite Analysis Workspace.

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
   <td colname="col2"> <p>La funzione Analisi contributi ha riscosso un grande successo in Adobe Analytics. La possibilità di disporre di un numero limitato di esecuzioni “complete” al mese (anziché 3 sole dimensioni per alcuni prodotti Analytics) consente di comprendere meglio i risultati ottenibili dall’analisi completa e illimitata dei contributi. </p> </td> 
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
   <td colname="col2"> <p>Per impostazione predefinita, solo gli amministratori hanno accesso all’esecuzione di Analisi contributi, ma possono concedere l’accesso ad altri utenti creando un gruppo di autorizzazioni in <a href="https://docs.adobe.com/content/help/it-IT/core-services/interface/manage-users-and-products/admin-getting-started.html"  >Admin Console</a>. Si consiglia di concedere l’autorizzazione all’analisi dei contributi solo agli utenti che abbiano un motivo legittimo per accedervi e di cui si sia certi che non abuseranno dei diritti di accesso ricevuti. </p> <p>Il titolo dell’autorizzazione è “Contribution Analysis” (Analisi contributi), alla voce <span class="ignoretag"><span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Amministratore</span> &gt; <span class="uicontrol">Gestione utente</span> &gt; <span class="uicontrol">Modifica gruppi</span> &gt; <span class="uicontrol">Modifica accesso a tutti i rapporti</span> &gt; <span class="uicontrol">Personalizza strumenti della suite di rapporti</span> &gt; <span class="uicontrol">Strumenti e rapporti</span></span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Come faccio a conoscere il numero di token mensili a disposizione della mia azienda e quanti ne abbiamo utilizzati nel mese in corso?</b> </p> </td> 
   <td colname="col2"> <p>Vai a <span class="ignoretag"><span class="uicontrol">Amministratore</span> &gt; <span class="uicontrol">Impostazioni società</span> &gt; <span class="uicontrol">Visualizza funzione livelli di accesso</span></span>. Su questa pagina sono presenti 2 nuovi elementi: </p> <p><img placement="break"  src="assets/ca_access_level.png" id="image_16012FE1162C485EA768D175F43D7563" width="500px" /> </p> </td> 
  </tr> 
 </tbody> 
</table>


## Adesioni a Rilevamento delle anomalie e Analisi contributi {#section_9278D58F21A840AA9B1ED1BD07A1EF0A}

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
   <td colname="col1"> <p><a href="https://www.adobe.com/it/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other"  > Select </a> </p> </td> 
   <td colname="col2"> <p>Solo granularità giornaliera </p> </td> 
   <td colname="col3"> <p>Nessun token </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/it/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other"  > Prime </a> </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>10 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/it/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
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
   <td colname="col1"> <p>Premium (Complete, <a href="https://www.adobe.com/it/data-analytics-cloud/analytics/predictive-intelligence.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>Token illimitati </p> </td> 
  </tr> 
 </tbody> 
</table>
