---
description: Le categorie di origine dati identificano diversi tipi di origini dati che forniscono funzionalità simili.
subtopic: Data sources
title: Panoramica dei tipi di dati e categorie
topic-fix: Developer and implementation
uuid: b5004cdc-b68a-4a82-a159-a7cd7b8bfe21
exl-id: d459fd06-a0fe-49e6-8624-b42f0c60ee6e
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '907'
ht-degree: 97%

---

# Panoramica dei tipi di dati e categorie

Le categorie di origine dati identificano diversi tipi di origini dati che forniscono funzionalità simili.

Le categorie consentono di raggruppare le origini dati dal punto di vista di un utente. Quando crei un&#39;origine dati tramite l&#39;UI di Origini dati, seleziona dapprima una categoria di origini dati, quindi un tipo di origine dati specifico. Ogni categoria contiene tipi di origini dati che supportano tipi di dati simili. Origini dati presenta le categorie di origini dati seguenti:

## Utilizzo sito web {#section_4BA8D97B6BA848518F21760AE49F41D1}

<table id="table_2562E7A400214B8F9BB9177D210348F4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Origine dati </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo di elaborazione </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>File di registro server web </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-web-log.md"   > Registro web </a> </p> </td> 
   <td colname="col3"> <p>La maggior parte dei server web genera file di registro che registrano ogni pagina utilizzata. Tramite questa origine dati puoi elaborare i file di registro dalla maggior parte dei dati di server web e aggiungere i dati ai rapporti. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Caricamento in serie di Advertising Cloud </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Fornisce caricamenti in serie manuali e automatizzati in Excel in Advertising Cloud. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Origine dati Traffico a livello di sito </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md"   > Traffico </a> </p> </td> 
   <td colname="col3"> <p>Importa i dati del traffico per tutto il sito web. Ad esempio, Visualizzazioni pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Origine dati Traffico suddivisa </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-traffic.md"   > Traffico </a> </p> </td> 
   <td colname="col3"> <p>Importa i dati Traffico suddivisi per un'altra variabile del sito web. Ad esempio Visualizzazioni pagina per Prodotto. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Campagne pubblicitarie {#section_9AE27E347CFC48F29E7C1134B6E928A6}

<table id="table_2A297A86CC3E4B1E8B72389AA148549A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Origine dati </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo di elaborazione </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Ad server generico </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di integrare impression e altre metriche top-line sulle attività di trasmissione degli annunci dall'ad server ai rapporti di marketing. È l'origine dati ad server generica e deve essere utilizzata se l'ad server specifico non è supportato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server campagne e-mail generico </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di integrare le metriche dal server di campagne e-mail nei rapporti di marketing. </p> <p>Le metriche incorporate comunemente includono il numero di messaggi inviati, i messaggi consegnati e i messaggi letti. È l'origine dati di campagne e-mail generica e deve essere utilizzata se il server di campagne e-mail specifico non è supportato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Servizio Pay-Per-Click generico </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p> Consente di importare i dati sulle prestazioni pay-per-click, inclusi impression, clic e costi. </p> <p>È l'origine dati pay-per-click generica e deve essere utilizzata se il servizio pay-per-click specifico non è supportato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Gestione delle relazioni con i clienti (CRM)  {#section_013A1C5D3CAD4CCEAD22C2FDD26715A0}

<table id="table_5895659CAB2C415AB2AA59A2E6C75AD1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Origine dati </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo di elaborazione </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Call center generico </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di integrare informazioni sul call center nei rapporti di marketing. Le metriche importate più comunemente includono il numero di chiamate, il tempo al telefono, l'agente e le vendite totali. </p> <p>È l'origine dati call center generica e deve essere utilizzata se il software call center specifico non è supportato. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Assistenza clienti generica </p> <p>Applicazione </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di integrare informazioni sul software di assistenze clienti nei rapporti di marketing. Include metriche quali il numero di nuovi incidenti, il numero di incidenti risolti e il tempo impiegato per la risoluzione degli incidenti. </p> <p>È l'origine dati assistenza clienti generica e deve essere utilizzata se il servizio assistenza clienti specifico non è supportato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Soddisfazione dei clienti  {#section_1058CA3860044630B0B06EEDA261DBA2}

<table id="table_3811CA1E2B7C45D7A0CBEC5CE44C11A8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Origine dati </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo di elaborazione </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Dati sondaggio generici </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di integrare i risultati dei sondaggi da uno strumento di terze parti nei rapporti di marketing e mostra il livello di soddisfazione dei clienti in merito alle interazioni con il sito. </p> <p>È l'origine dati sondaggio generica e deve essere utilizzata se il servizio dati sondaggio specifico non è supportato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prestazioni del sito  {#section_3A7BECB0B4B247FB991DC59237ECFE1F}

<table id="table_7B623D08275E4FDEADDD85EA89A2B7C7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Origine dati </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo di elaborazione </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Velocità di caricamento del sito generica </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di integrare i dati da un'applicazione o servizio che monitora la velocità dei download con i dati. </p> <p>È l'origine dati velocità download e deve essere utilizzata se il software di velocità download specifico non è supportato. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Generico  {#section_9B9A2A9871894B6491032AE1E961629A}

<table id="table_D63A6A00C93A4CD48FEBE7BC24E5DA9F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Origine dati </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo di elaborazione </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Origine dati generica (solo dati di riepilogo) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Utilizza questa origine dati quando non esiste una corrispondenza migliore per il tipo di dati da importare nei reporting e analisi di marketing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Origine dati generica (Elaborazione completa) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-full-processing.md"   > Elaborazione completa </a> </p> </td> 
   <td colname="col3"> <p>Consente di importare i dati del file di registro. Questi dati vengono elaborati come se fossero stati ricevuti dai server di raccolta dati al momento specificato (ogni hit riceve una marca temporale). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> <p>Origine dati generica (ID transazione) </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-transactionid.md"   > ID transazione </a> </p> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-visitorid.md"   > ID visitatore </a> </p> </td> 
   <td colname="col3"> <p>Consente di collegare qualsiasi evento offline a un evento online. L'ID transazione funge da chiave tra gli eventi offline e online. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Acquisti online  {#section_2B2D4DBB045548C3A5DC7DEF81BA56D1}

<table id="table_EE450D955D4C4264A40142AF6D74F1AA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Origine dati </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo di elaborazione </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Resi di prodotti </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di importare i dati dei resi di prodotti da associare a un ID acquisto in modo da identificare motori di ricerca, parole chiave, campagne e altri attributi che genereranno resi con maggiore probabilità. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Costo del prodotto </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di fornire il costo effettivo dei prodotti acquistati e spediti dal sito Web associando costo o profitto a singoli prodotti in modo da creare rapporti precisi su campagne, parole chiave e promozioni interne più redditizie per il sito Web. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato ordine </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di utilizzare le metriche per identificare lo stato di ogni ordine effettuato, inclusi gli ordini annullati, spediti, completati o ritenuti fraudolenti. </p> <p>Il reporting dello stato degli ordini può identificare quali metodi di acquisizione generano il tasso di completamento degli ordini più alto. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Lead e preventivi  {#section_0B3EAA59BEC94244BE3EB3825D719DF6}

<table id="table_85B095414F6C4644A191A94AC0CAD13D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Origine dati </p> </th> 
   <th colname="col2" class="entry"> <p>Tipo di elaborazione </p> </th> 
   <th colname="col3" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Generazione di lead </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di caricare le informazioni sui risultati dei lead per ogni lead generato sul sito Web, inclusi i ricavi effettivi generati. </p> <p>Dopo aver attribuito con precisione i ricavi agli ID lead, puoi identificare le campagne e le promozioni più redditizie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Preventivo online </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di caricare le informazioni sui risultati dei lead per ogni lead generato sul sito Web, inclusi i ricavi effettivi generati. </p> <p>Dopo aver attribuito con precisione i ricavi agli ID lead, puoi identificare le campagne e le promozioni più redditizie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dati del call center </p> </td> 
   <td colname="col2"> <p> <a href="/help/import/c-data-sources/c-datasrc-types/datasrc-conversion.md"   > Conversione </a> </p> </td> 
   <td colname="col3"> <p>Consente di caricare le transazioni del call center in modo da identificare le tattiche (campagne, promozioni e così via) che convincono i clienti a fare una telefonata. </p> </td> 
  </tr> 
 </tbody> 
</table>
