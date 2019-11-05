---
description: nulle
seo-description: nulle
seo-title: Panoramica dell'analisi dei contributi
title: Panoramica dell'analisi dei contributi
uuid: 2bd295b0-c5ce-4443-86af-024efd20c021
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Panoramica dell'analisi dei contributi

Analisi contributi rileva i pattern nascosti nei dati per spiegare le anomalie statistiche e identificare le correlazioni alla base di azioni inaspettate da parte del cliente, valori non associati e picchi o ribassi improvvisi per metriche selezionate tra segmenti di pubblico convergenti.

È successo qualcosa. Perché? Il rapporto Anomaly Detection (Rilevamento anomalo) mostra un picco insolito negli ordini e vuoi sapere perché. Cos'è successo fuori dal comune? Chi risponde a quale campagna o riferimento? Qualcosa è diventato virale? Quali sono i fattori specifici che hanno contribuito a questa anomalia? E forse più importante: Come posso acquisire informazioni importanti sul mio cliente e ripetere queste prestazioni? (Oppure, se si è verificato un calo in una metrica o un aumento in una metrica negativa, come posso evitarlo in futuro?)

L’analisi dei contributi consente di valutare immediatamente i dati per individuare il motivo di un’anomalia. Suddivide i contributi a un’anomalia in secondi in quanto richiedeva settimane, fornendo pattern per segmenti di pubblico e aiutando a sviluppare una narrazione per le interazioni dei clienti. Puoi utilizzare Analisi contributi in modo strategico per identificare e acquisire associazioni significative per sviluppare nuovi segmenti di pubblico, oppure utilizzarlo tatticamente per identificare attività non associate o fraudolente che attivano un avviso.

[Rilevamento](/help/analyze/analysis-workspace/virtual-analyst/c-anomaly-detection/anomaly-detection.md) delle anomalie identifica picchi di dati e cali statistici estremi in base a metriche selezionate e a segmenti di pubblico selezionati. Definisce una norma storica basata su un periodo di formazione e quindi traccia gli offset estremi correlati a eventi specifici. Può segnalare un aumento precipitoso in una metrica Ordini positivi o un aumento in una metrica Saldi negativi, o un calo in entrambe, catturando i punti dati statisticamente rilevanti che devono essere valutati dall’analisi dei contributi. Una volta identificata un’anomalia statistica, Analisi contributi consente di approfondire e valutare le variabili di marketing e campagne rilevanti in tutti i punti dati anomali. Esegue algoritmi avanzati e processi di machine-learning per valutare le associazioni che hanno contribuito a un picco o a un calo significativo. Questi calcoli vengono quindi visualizzati in visualizzazioni interattive progettate per fornire prospettive diverse per spiegare perché è accaduto qualcosa e cosa fare al riguardo.

Contribution Analysis consente di sviluppare una narrazione per descrivere il motivo e la modalità di risposta a un’anomalia, acquisire le metriche rilevanti e identificare punti nascosti che forniscono una ragione generale per le interazioni tra il pubblico e gli interessi dei clienti più importanti. A volte un'anomalia è facile da vedere e correggere, come un ordine errante per 2.000 kayak. A volte è complesso, come identificare una tendenza emergente in un periodo di tempo in una regione che reagisce solo a una campagna mirata specifica. La combinazione di elementi che contribuiscono alle metriche per diverse dimensioni e associazioni offre un'idea generale delle interazioni tra il pubblico e contribuisce a fornire contesto per punti dati anomali.

Ecco alcune idee:

* Potenziale di ricommercializzazione delle identità mediante il monitoraggio delle modifiche della domanda di prodotto.
* Migliorate l'esperienza del cliente reagendo a specifici interessi del pubblico.
* Identificare gli ordini fraudolenti fin dall'inizio come rapporto fuori limite.
* Proteggetevi dallo spionaggio aziendale identificando un utilizzo e download elevati.
* Monitorare le operazioni, ad esempio la segnalazione dei tag javascript mancanti.

Dopo un’analisi completa di un’anomalia, per gli articoli principali ordinati dalle occorrenze totali e dalla percentuale dell’articolo rispetto ai valori contributori viene generato un Riepilogo contributi. Un punteggio di contributo normalizzato consente di confrontare, confrontare e associare facilmente elementi di dimensione significativi.

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
   <td colname="col2"> <p>La funzione Analisi contributi di Adobe Analytics ha riscosso un grande successo dal rilascio iniziale nel 2015. La possibilità di disporre di un numero limitato di esecuzioni "complete" al mese (invece che di 3 sole dimensioni per alcuni prodotti Analytics) consente di vedere meglio le funzionalità di analisi completa e illimitata dei contributi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Come funziona l’utilizzo dei token nell’analisi dei contributi? È necessario spendere un token per caricare un progetto con un’analisi dei contributi esistente oppure è richiesto solo se si esegue una nuova analisi?</b> </p> </td> 
   <td colname="col2"> <p>Ogni società di accesso (non ogni utente) riceve un certo numero di token al mese, che consentono di eseguire un’analisi dei contributi "completa" in Analysis Workspace. </p> <p>Ogni volta che si genera una nuova analisi dei contributi si paga un token. Quando si caricano progetti con analisi dei contributi preesistenti non viene richiesto alcun token. </p> </td> 
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
   <td colname="col2"> <p>Per impostazione predefinita, solo gli amministratori hanno accesso per eseguire Analisi contributi, ma gli amministratori possono concedere l’accesso ad altri utenti creando un gruppo di autorizzazioni in <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html"  > Admin Console </a>. È necessario concedere l’autorizzazione per utilizzare l’analisi dei contributi solo agli utenti che hanno un motivo legittimo per utilizzarla e che non abusino del loro accesso. </p> <p>Il titolo dell’autorizzazione è “Contribution Analysis” (Analisi contributi), alla voce <span class="ignoretag"><span class="uicontrol">Analytics</span> &gt; <span class="uicontrol">Admin (Amministratore)</span> &gt; <span class="uicontrol">User Management (Gestione utente)</span> &gt; <span class="uicontrol">Edit Groups (Modifica gruppi)</span> &gt; <span class="uicontrol">Edit All Report Access (Modifica accesso a tutti i rapporti)</span> &gt; <span class="uicontrol">Customize Report Suite Tools (Personalizza strumenti della suite di rapporti)</span> &gt; <span class="uicontrol">Tools And Reports (Strumenti e rapporti)</span></span>. </p> </td> 
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
>Le funzioni Rilevamento delle anomalie e Analisi contributi sono state rimosse da Reports &amp; Analytics e sono ora disponibili solo in Analysis Workspace. I clienti di Adobe Analytics Select e Adobe Analytics Foundation hanno accesso solo al rilevamento delle anomalie "giornaliero" in Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adesione Adobe Analytics </th> 
   <th colname="col2" class="entry"> Detección de anomalías </th> 
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
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/select.html?promoid=B4XQ3X7G&amp;mv=other"  > Select </a> </p> </td> 
   <td colname="col2"> <p>Solo granularità giornaliera </p> </td> 
   <td colname="col3"> <p>Nessun token </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/prime.html?promoid=91BF51TR&amp;mv=other"  > Prime </a> </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>10 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://www.adobe.com/data-analytics-cloud/analytics/ultimate.html?promoid=8N4B5F1V&amp;mv=other"  > Ultimate</a> </p> </td> 
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
   <td colname="col1"> <p>Premium (Complete, <a href="https://www.adobe.com/data-analytics-cloud/analytics/predictive-intelligence.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>Token illimitati </p> </td> 
  </tr> 
 </tbody> 
</table>
