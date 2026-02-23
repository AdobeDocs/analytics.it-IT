---
description: Scopri il rilevamento delle anomalie nei dati in Analysis Workspace.
title: Panoramica sul rilevamento di anomalie
feature: Anomaly Detection
role: User, Admin
exl-id: b1625206-c774-40ef-9d92-25ee8ff1478d
source-git-commit: 8b1e25b9633b6db3e49da079f7014e6b7b595474
workflow-type: tm+mt
source-wordcount: '1279'
ht-degree: 49%

---

# Panoramica sul rilevamento di anomalie

In Analysis Workspace puoi visualizzare e analizzare le anomalie nei dati in modo contestuale. L’analisi dei contributi funziona con il rilevamento delle anomalie per aiutare a identificare cosa ha contribuito all’anomalia.


>[!BEGINSHADEBOX]

Per un video demo, vedi ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Rilevamento anomalie](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/data-science/anomaly-detection-in-analysis-workspace){target="_blank"}.

>[!ENDSHADEBOX]

>[!IMPORTANT]
>
>I clienti Select e Adobe Analytics Foundation di Adobe Analytics possono accedere solo alla funzione di rilevamento delle anomalie *con granularità giornaliera* in Workspace. Per ulteriori informazioni, consulta [Adesioni a Rilevamento delle anomalie e Analisi contributi](#anomaly-detection-and-contribution-analysis-entitlements).

## Rilevamento delle anomalie

Il rilevamento anomalie fornisce un metodo statistico per determinare come una particolare metrica è cambiata in relazione ai dati precedenti.

Il rilevamento delle anomalie consente di separare i &quot;segnali effettivi&quot; dal &quot;rumore&quot; e quindi di identificare i fattori potenziali che hanno contribuito a tali segnali o anomalie. In altre parole, consente di identificare quali fluttuazioni statistiche hanno un impatto significativo e quali no. Puoi quindi identificare la causa principale di una vera anomalia. Inoltre, è possibile ottenere previsioni di metriche affidabili (KPI).

Di seguito sono riportati alcuni esempi di anomalie che è possibile analizzare:

* Cali drastici nel valore medio dell’ordine
* Picchi negli ordini con ricavi bassi
* Picchi o cadute nelle registrazioni di prova
* Cadute nelle visualizzazioni della pagina di destinazione
* Picchi negli eventi del buffer video
* Picchi di bit rate video ridotti

Rilevamento delle anomalie e [Analisi contributi](/help/analyze/analysis-workspace/c-anomaly-detection/anomaly-detection.md) sono flussi di lavoro principali in Analysis Workspace. Puoi eseguire l’analisi dei contributi per le anomalie giornaliere e incorporare il risultato nel progetto Analysis Workspace.

L’algoritmo di rilevazione delle anomalie di Analysis Workspace include:

* Supporto per granularità oraria, settimanale e mensile, oltre alla granularità giornaliera esistente.
* Consapevolezza della stagionalità (come il &quot;Black Friday&quot;) e delle festività.

## Analisi contributi

L’analisi dei contributi rileva pattern nascosti nei dati per spiegare le anomalie statistiche e identificare le correlazioni sottostanti.

* azioni cliente impreviste,
* valori non associati, e
* picchi o cadute improvvisi

per le metriche selezionate tra segmenti di pubblico convergenti.


>[!BEGINSHADEBOX]

Per un video dimostrativo, consulta ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Analisi contributi](https://experienceleague.adobe.com/it/docs/analytics-learn/tutorials/data-science/contribution-analysis-workspace){target="_blank"}.

>[!ENDSHADEBOX]


Si è verificata un’anomalia. Perché? Il report della funzionalità di rilevamento delle anomalie mostra un picco insolito negli ordini e vuoi scoprirne il motivo. Cos’è successo di straordinario? Chi risponde a una determinata campagna o riferimento? Un contenuto è diventato virale? Quali sono i fattori specifici che hanno contribuito a questa anomalia? Forse l’informazione più importante: come posso acquisire informazioni critiche sul mio cliente e ripetere queste prestazioni? (Oppure, se si è verificato un calo in una metrica o un aumento in una metrica negativa, come posso evitarlo in futuro?)

L’analisi dei contributi consente di valutare immediatamente i dati per individuare la causa di un’anomalia. Suddivide i contributi in un’anomalia in pochi secondi anziché settimane come in precedenza, fornendo pattern per determinati segmenti di pubblico e aiutando a sviluppare un percorso delle interazioni dei clienti. È possibile utilizzare l’analisi dei contributi in modo strategico per identificare e acquisire associazioni significative. Quindi utilizza tali associazioni in modo strategico per sviluppare nuovi segmenti di pubblico o in modo tattico per identificare attività non associate o fraudolente che attivano un avviso.

[Rilevamento delle anomalie](#anomaly-detection) identifica picchi di dati e cali statistici estremi in base a metriche selezionate e a segmenti di pubblico selezionati. Il rilevamento delle anomalie imposta una norma storica basata su un periodo di formazione e quindi traccia gli offset estremi correlati a eventi specifici. Il rilevamento delle anomalie può segnalare un aumento precipitoso in una metrica Ordini positiva o un aumento in una metrica Rimbalzi negativa, oppure un calo in entrambe, acquisendo punti di dati statisticamente rilevanti da valutare mediante l’analisi dei contributi. Una volta identificata un’anomalia statistica, l’analisi dei contributi consente di approfondire e valutare le variabili di marketing e campagne rilevanti in tutti i punti di dati anomali. Esegue algoritmi avanzati e processi di machine-learning per valutare le associazioni che hanno contribuito a un picco o a un calo significativo. Questi calcoli vengono quindi mostrati tramite visualizzazioni interattive progettate per fornire prospettive diverse e aiutare a identificare le cause di un fenomeno e i possibili rimedi.

L’analisi dei contributi consente di sviluppare una narrazione per descrivere la causa di un’anomalia. E come rispondere alle anomalie, acquisendo metriche rilevanti e identificando punti nascosti che ti forniscono una ragione complessiva per le interazioni del pubblico e gli interessi più comuni dei clienti. A volte un’anomalia è facile da identificare e correggere, come un ordine errato di 2.000 kayak. A volte è più complessa, come l’identificazione di una tendenza emergente in un periodo di tempo all’interno di una regione che reagisce solo a una campagna mirata specifica. La combinazione di elementi che contribuiscono alle metriche per diverse dimensioni e associazioni offre un’idea generale delle interazioni del pubblico e contribuisce a fornire contesto per punti di dati anomali.

Di seguito sono riportati alcuni casi di utilizzo:

* Identifica le opportunità di remarketing monitorando i cambiamenti nella domanda dei prodotti.
* Migliora l’esperienza del cliente reagendo a specifici interessi del pubblico.
* Identifica gli ordini fraudolenti sin da subito tramite report fuori limite.
* Previeni lo spionaggio aziendale identificando utilizzi e download elevati.
* Monitora operazioni quali la segnalazione di tag JavaScript mancanti.

Dopo un’analisi completa di un’anomalia, viene generato un riepilogo dei contributi contenente gli elementi principali ordinati per occorrenze totali e la percentuale dei valori contribuenti dell’elemento. Un punteggio di contributo normalizzato consente di confrontare, contrastare e associare facilmente elementi di dimensione significativa.

## Token di analisi dei contributi

Tutti i clienti con adesione ad Analisi contributi possono eseguire un’analisi completa dei contributi per un numero limitato di volte al mese in Analysis Workspace. L&#39;analisi dei contributi **esclude** i clienti SiteCatalyst 15 (Point Product), i clienti Analytics Foundation e i clienti Select di Analytics, che non hanno diritto all&#39;analisi dei contributi.

Il numero di esecuzioni per azienda è limitato dai token mensili concessi in base al prodotto Adobe Analytics acquistato dalla tua azienda. Il numero di esecuzioni per azienda include la possibilità di limitare l’accesso all’analisi dei contributi per evitare l’uso improprio dei token.

## Domande frequenti

| Domanda | Risposta |
| --- | --- |
| Perché Adobe ha introdotto i token? | La funzione Analisi contributi ha riscosso un grande successo in Adobe Analytics. La possibilità di disporre di un numero limitato di esecuzioni complete al mese (anziché 3 sole dimensioni per alcuni prodotti Analytics) consente di comprendere le funzionalità dell’analisi completa e illimitata dei contributi. |
| Come funzionano i token in Analisi contributi? È necessario spendere un token per caricare un progetto con un’analisi dei contributi esistente oppure è richiesto solo se si esegue una nuova analisi? | Ad ogni azienda per la quale si esegue l’accesso (non a ciascun utente) viene assegnato un determinato numero di token al mese, che consente di eseguire analisi dei contributi “complete” in Analysis Workspace.  Ogni volta che generi una nuova analisi dei contributi, paghi un token. Il caricamento di progetti con analisi dei contributi pre-eseguite non costa un token. |
| Cosa devo fare se la mia azienda ha esaurito i token e desidera eseguire ulteriori analisi dei contributi? | Puoi effettuare l’aggiornamento a un altro prodotto Adobe Analytics, ad esempio da Standard (2 token/mese) a Ultimate (20 token/mese). Non è possibile acquistare altri token. È necessario eseguire l’aggiornamento all’interno del framework di creazione pacchetti esistente. |
| Come si limita l’accesso all’analisi dei contributi? | Per impostazione predefinita, solo gli amministratori hanno accesso all’esecuzione di Analisi contributi. Tuttavia, gli amministratori possono concedere l’accesso ad altri utenti creando un gruppo di autorizzazioni in [Adobe Admin Console](/help/admin/admin-console/home.md). Concedi l’autorizzazione per utilizzare Analisi contributi solo agli utenti che hanno un motivo legittimo per utilizzarla e che sono certi di non abusare del loro accesso. L’autorizzazione si chiama [!UICONTROL Contribution Analysis] (Analisi contributi) e si trova in [!UICONTROL Report Suite Tools] (Strumenti suite di rapporti). [Ulteriori informazioni](/help/admin/admin-console/permissions/report-suite-tools.md) |
| Come faccio a conoscere il numero di token mensili a disposizione della mia azienda e quanti token sono stati utilizzati dalla mia azienda nel mese in corso? | Vai a  [!UICONTROL Admin] > [!UICONTROL All admin] >[!UICONTROL Company settings Home] >[!UICONTROL View Feature Access Levels]. Cerca in<ul><li>Analisi contributi: numero di token di utilizzo mensili</li><li>Analisi contributi: numero di token di utilizzo consumati in questo mese</li></ul> |

## Adesioni a Rilevamento delle anomalie e Analisi contributi

Di seguito è riportato un elenco dettagliato delle adesioni disponibili per Rilevamento delle anomalie e Analisi contributi in Analysis Workspace.

<table id="table_5C9B7E4AE82640B5A913519E576889B5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Adesione ad Adobe Analytics </th> 
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
   <td colname="col1"> <p><a href="https://business.adobe.com/it/products/analytics/compare-adobe-analytics-packages.html?promoid=B4XQ3X7G&mv=other"  > Select </a> </p> </td> 
   <td colname="col2"> <p>Solo granularità giornaliera </p> </td> 
   <td colname="col3"> <p>Nessun token </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/it/products/analytics/compare-adobe-analytics-packages.html?promoid=91BF51TR&mv=other"  > Prime </a> </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>10 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><a href="https://business.adobe.com/it/products/analytics/compare-adobe-analytics-packages.html?promoid=8N4B5F1V&mv=other"  > Ultimate</a> </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>20 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Componente aggiuntivo Predictive Workbench </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>Token illimitati </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Standard </p> 
    <ul id="ul_73D52020793B44868C9CE0F90893075D"> 
     <li id="li_21EE0871C87E43C8B781219B2BA0FA74">Adobe Analytics Core </li> 
     <li id="li_AB3593200F33439BAEE8FEB13CAE57F4">ADOBE ANALYTICS OD </li> 
     <li id="li_2B7D625519BC4A4CB598C95F15D3029B">MA ADOBE ANALYTICS </li> 
    </ul> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>2 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (360, Attribuzione) </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>2 token al mese </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Premium (Complete, <a href="https://business.adobe.com/it/products/analytics/predictive-analytics.html"  >Predictive Intelligence</a>) </p> </td> 
   <td colname="col2"> <p>Sì </p> </td> 
   <td colname="col3"> <p>Token illimitati </p> </td> 
  </tr> 
 </tbody> 
</table>
