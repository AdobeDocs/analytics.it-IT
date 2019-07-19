---
description: Nelle tabelle seguenti è riportato il parametro query che contiene il valore per ogni variabile di analisi inviata alla raccolta dati.
keywords: Implementazione di Analytics
seo-description: Nelle tabelle seguenti è riportato il parametro query che contiene il valore per ogni variabile di analisi inviata alla raccolta dati.
seo-title: Parametri query della raccolta dati
solution: Analytics
title: Parametri query della raccolta dati
topic: Sviluppatore e implementazione
uuid: 4 d 5 af 486-df 27-42 fe-bb 9 c -28938 dddf 2 b 2
translation-type: tm+mt
source-git-commit: 5a30ea6ac47ddd8612728e488afda868491a1ddc

---


# Parametri query della raccolta dati

Nelle tabelle seguenti è riportato il parametro query che contiene il valore per ogni variabile di analisi inviata alla raccolta dati.

This information can be used when debugging using [Packet Analyzers](../../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258), when manually constructing image requests, or when using [Dynamic Variables](../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262).

<table id="table_5442E15BF0AE4BDA92DDADD1C08F7C13"> 
 <thead> 
  <tr> 
   <th class="entry"> Parametro </th> 
   <th class="entry"> Variabile Analytics </th> 
   <th class="entry"> Report popolato </th> 
   <th class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> aamlh </td> 
   <td colname="col2"> Nessuno </td> 
   <td colname="col3"> Nessuno </td> 
   <td colname="col4"> Hint Location Manager (Hint di Audience Manager) (usato nell'integrazione di Experience Cloud Shared Profile) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aamb </td> 
   <td colname="col2"> Nessuno </td> 
   <td colname="col3"> Nessuno </td> 
   <td colname="col4"> Pubblico Audience Manager (usato nell'integrazione di Profilo condiviso di Experience Cloud) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> aid </td> 
   <td colname="col2"> Nessuno </td> 
   <td colname="col3"> Nessuno </td> 
   <td colname="col4"> ID visitatore di Analytics </td> 
  </tr> 
  <tr> 
   <td> AQB </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> Indica l'inizio di una richiesta di immagine. </td> 
  </tr> 
  <tr> 
   <td> AQE </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> Indica la fine di una richiesta di immagine, il che significa che la richiesta non è stata troncata. </td> 
  </tr> 
  <tr> 
   <td> bh </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Altezza browser </td> 
   <td> Altezza della finestra del browser (in pixel) </td> 
  </tr> 
  <tr> 
   <td> bw </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Larghezza browser </td> 
   <td> Larghezza della finestra del browser (in pixel) </td> 
  </tr> 
  <tr> 
   <td> c </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Profondità colore monitor </td> 
   <td> Qualità colore (in bit) </td> 
  </tr> 
  <tr> 
   <td> <code> c. <span class="varname"> [key] </code></span> </td> 
   <td> <p>s. contextdata </p> </td> 
   <td> <p>Nessuno </p> </td> 
   <td> <p>Le coppie chiave-valori sono specificate in uno dei seguenti formati: </p> <p> <code> &lt; my. a &gt; red &lt;/my. a &gt; </code> </p> <p>oppure: </p> <p> <code> &lt; my &gt; &lt; a &gt; red &lt;/a &gt; &lt;/my &gt; </code> </p> <p>Each of these examples result in a context data value of <code> my.a = red </code>. È possibile specificare più coppie chiave-valore. </p> <p>In the query string, this context data variable would appear as <code> c.&amp;my.a=red </code> </p> </td> 
  </tr> 
  <tr> 
   <td> c 1-c 75 </td> 
   <td> s. prop 1-s. prop 75 </td> 
   <td> Tutti i rapporti sul traffico personalizzato </td> 
   <td> Variabili di traffico utilizzate nel reporting personalizzato del traffico </td> 
  </tr> 
  <tr> 
   <td> cc </td> 
   <td> s. currencycode </td> 
   <td> Nessuno </td> 
   <td> Il tipo di valuta utilizzato nel sito </td> 
  </tr> 
  <tr> 
   <td> cdp </td> 
   <td> s. cookiedomainperiod </td> 
   <td> Nessuno </td> 
   <td> Indica il numero di periodi in un dominio per il tracciamento dei cookie; impostato manualmente. </td> 
  </tr> 
  <tr> 
   <td> ce </td> 
   <td> s. charset </td> 
   <td> Nessuno </td> 
   <td> Codifica caratteri della richiesta di immagine </td> 
  </tr> 
  <tr> 
   <td> cl </td> 
   <td> s. cookielifetime (s_ vi cookie "lifetime" in secondi) </td> 
   <td> Nessuno </td> 
   <td> Durata del cookie del visitatore. </td> 
  </tr> 
  <tr> 
   <td> ch </td> 
   <td> s. channel </td> 
   <td> Contenuto del sito | Sezioni del sito </td> 
   <td> La variabile Sezioni sito utilizzata nel rapporto sul traffico </td> 
  </tr> 
  <tr> 
   <td> cp </td> 
   <td> Tipo di hit </td> 
   <td> Tipo di hit </td> 
   <td> Indica se il comportamento è un risultato di un primo piano di interazione diretto o di informazioni che il dispositivo sta inviando senza sfondo di interazione diretto. </td> 
  </tr> 
  <tr> 
   <td> ct </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Tipi di connessione </td> 
   <td> Tipo di connessione (modem, LAN, ecc.) può essere compilato solo nei browser IE) </td> 
  </tr> 
  <tr> 
   <td> <code> D </code> </td> 
   <td> dynamicVariablePrefix </td> 
   <td> Nessuno </td> 
   <td> <p>See <a href="../../../implement/js-implementation/c-variables/dynvars-overview.md#concept_B016789733A94070A9EAB209EEC05262" format="dita" scope="local"> Dynamic Variables </a>. </p> </td> 
  </tr> 
  <tr> 
   <td> eventi o ev </td> 
   <td> s. events </td> 
   <td> Traffico del sito | Acquisti, Carrello acquisti, Eventi personalizzati </td> 
   <td> Il commerce e gli eventi personalizzati che si sono verificati sulla pagina; utilizzati nei rapporti di conversione </td> 
  </tr> 
  <tr> 
   <td> g </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> L'URL corrente della pagina, fino a 255 byte. </td> 
  </tr> 
  <tr> 
   <td> -g </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> Gli URL superiori a 255 byte vengono divisi, con i primi 255 byte visualizzati nel parametro g, con i byte rimanenti visualizzati successivamente nella stringa query nel parametro -g = query. </td> 
  </tr> 
  <tr> 
   <td> h 1-h 5 </td> 
   <td> s. hier 1-s. hier 5 </td> 
   <td> Contenuto del sito | Rapporti gerarchici </td> 
   <td> Variabili gerarchiche; utilizzati nel rapporto sul traffico </td> 
  </tr> 
  <tr> 
   <td> hp </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Home page Visitor </td> 
   <td> Indica se la pagina corrente è la home page del browser (Y o N; può essere compilato solo nei browser IE) </td> 
  </tr> 
  <tr> 
   <td> j </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Versione Javascript </td> 
   <td> Mostra la versione corrente di Javascript installata (generalmente 1. x) </td> 
  </tr> 
  <tr> 
   <td> k </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Cookie </td> 
   <td> Sono cookie supportati nel browser (Y, N o U) </td> 
  </tr> 
  <tr> 
   <td> l 1-l 3 </td> 
   <td> s. list 1-s. list 3 </td> 
   <td> Conversione personalizzata </td> 
   <td> Un elenco delimitato di valori passati in una variabile, quindi segnalati come elementi di singole righe a scopo di reportistica. </td> 
  </tr> 
  <tr> 
   <td> mid </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> ID visitatore Experience Cloud </td> 
  </tr> 
  <tr> 
   <td> ndh </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> Indica se la richiesta di immagine è stata originata dal file JS (1 o 0) </td> 
  </tr> 
  <tr> 
   <td> ns </td> 
   <td> s. visitornamespace </td> 
   <td> Nessuno </td> 
   <td> Specifica il dominio in cui i cookie sono impostati </td> 
  </tr> 
  <tr> 
   <td> oid </td> 
   <td> s. objectid </td> 
   <td> Contenuto del sito | Collegamenti | Clickmap </td> 
   <td> Identificatore oggetto per l'ultima pagina; used in clickmap </td> 
  </tr> 
  <tr> 
   <td> ot </td> 
   <td> Nessuno </td> 
   <td> Contenuto del sito | Collegamenti | Clickmap </td> 
   <td> Nome tag oggetto per l'ultima pagina; used in clickmap </td> 
  </tr> 
  <tr> 
   <td> p </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Plug-in Netscape </td> 
   <td> Nomi dei plug-in delimitati da punto e virgola </td> 
  </tr> 
  <tr> 
   <td> Pagename (o gn) </td> 
   <td> s. pagename </td> 
   <td> Contenuto del sito | Pagine </td> 
   <td> Il nome designato della pagina nel reporting </td> 
  </tr> 
  <tr> 
   <td> Pagetype (o gt) </td> 
   <td> s. pagetype </td> 
   <td> Contenuto del sito | Pagine non un nome </td> 
   <td> Indica se si tratta di una pagina o meno di 404 (errore o vuoto) </td> 
  </tr> 
  <tr> 
   <td> pccr </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> Si verifica solo per i nuovi visitatori; impedisce reindirizzamenti infiniti (sempre true) </td> 
  </tr> 
  <tr> 
   <td> pe </td> 
   <td> s. linktype </td> 
   <td> Contenuto del sito | Collegamenti | Exit Links, File Downloads, Custom Links </td> 
   <td> Determina il tipo di hit di collegamento personalizzato attivato </td> 
  </tr> 
  <tr> 
   <td> pev1 </td> 
   <td> Nessuno </td> 
   <td> Contenuto del sito | Collegamenti | Exit Links, File Downloads, Custom Links </td> 
   <td> URL L'hit di collegamento personalizzato è stato attivato </td> 
  </tr> 
  <tr> 
   <td> pev2 </td> 
   <td> Nessuno </td> 
   <td> Contenuto del sito | Collegamenti | Exit Links, File Downloads, Custom Links </td> 
   <td> Nome personalizzato collegamento personalizzato </td> 
  </tr> 
  <tr> 
   <td> pev3 </td> 
   <td> Nessuno </td> 
   <td> Tutti i rapporti video </td> 
   <td> Utilizzato per tenere traccia delle pietre miliari nei rapporti video legacy; deprewith v 15 </td> 
  </tr> 
  <tr> 
   <td> pf </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> Solo per Adobe. Non alterare. </td> 
  </tr> 
  <tr> 
   <td> pid </td> 
   <td> Nessuno </td> 
   <td> Contenuto del sito | Collegamenti | Clickmap </td> 
   <td> Identificatore pagina per l'ultima pagina; used in clickmap </td> 
  </tr> 
  <tr> 
   <td> pidt </td> 
   <td> Nessuno </td> 
   <td> Contenuto del sito | Collegamenti | Clickmap </td> 
   <td> Identificatore pagina per l'ultima pagina; used in clickmap </td> 
  </tr> 
  <tr> 
   <td> products (o pl) </td> 
   <td> s. products </td> 
   <td> Prodotti | Prodotti </td> 
   <td> Variabile prodotti utilizzata nel reporting conversione </td> 
  </tr> 
  <tr> 
   <td> Purchaseid (o pi) </td> 
   <td> s. purchaseid </td> 
   <td> Nessuno </td> 
   <td> Utilizzato per deduplicare gli acquisti, impedendo la gonfiatura delle entrate </td> 
  </tr> 
  <tr> 
   <td> r </td> 
   <td> s.referrer </td> 
   <td> Tutti i rapporti sulle origini traffico </td> 
   <td> URL di riferimento </td> 
  </tr> 
  <tr> 
   <td> s </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Risoluzioni monitor </td> 
   <td> Risoluzione dello schermo (altezza x larghezza) </td> 
  </tr> 
  <tr> 
   <td> server (o sv) </td> 
   <td> s. server </td> 
   <td> Contenuto del sito | Server </td> 
   <td> Il server della pagina; utilizzati nel rapporto sul traffico </td> 
  </tr> 
  <tr> 
   <td> state </td> 
   <td> s. state </td> 
   <td> Profilo visitatore | Stato visitatore </td> 
   <td> Specifica lo stato come definito dalla variabile. </td> 
  </tr> 
  <tr> 
   <td> t </td> 
   <td> (automatico, inviato con ogni hit privo di marca temporale personalizzata) </td> 
   <td> Nessuno </td> 
   <td> <p>The <code> t </code> parameter is in the following format: </p> 
    <code>dd/mm/yyyy &amp; amp; nbsp; hh: mm: ss &amp; amp; nbsp; D &amp; amp; nbsp; OFFSET </code>
  <p>Where D is a number in the range <code> 0-6 </code> specifying the day of the week, and <code> OFFSET </code> represents: </p> 
    <code>offset &amp; amp; nbsp; da &amp; amp; nbsp; GMT &amp; amp; nbsp; in &amp; amp; nbsp; hours &amp; amp; nbsp; * &amp; amp; nbsp; 60 &amp; amp; nbsp; * &amp; amp; nbsp; -&amp; amp; nbsp; 1 </code>
  <p> Ad esempio: </p> 
    <code>23/09/2016 &amp; amp; nbsp; 14:00:00 &amp; amp; nbsp; 1 &amp; amp; nbsp; 420 </code>
  </td> 
  </tr> 
  <tr> 
   <td> <code> ts </code> </td> 
   <td> <p>timestamp </p> </td> 
   <td> Nessuno </td> 
   <td> <p>Il timestamp personalizzato calcolato e inviato con l'hit. Generalmente utilizzato per il tracciamento offline. </p> </td> 
  </tr> 
  <tr> 
   <td> v </td> 
   <td> Nessuno </td> 
   <td> Profilo visitatore | Tecnologia | Java </td> 
   <td> Java abilitato (Y o N) </td> 
  </tr> 
  <tr> 
   <td> v0 </td> 
   <td> s.campaign </td> 
   <td> Campagne | Codici di tracciamento </td> 
   <td> La variabile della campagna utilizzata nel reporting della conversione </td> 
  </tr> 
  <tr> 
   <td> v 1-v 75 </td> 
   <td> s. evar 1-s. evar 75 </td> 
   <td> Tutti i rapporti Conversione personalizzata </td> 
   <td> Variabili di conversione utilizzate nel reporting di conversione personalizzato </td> 
  </tr> 
  <tr> 
   <td> vid </td> 
   <td> <p>s.visitorID </p> </td> 
   <td> Nessuno </td> 
   <td> L'ID univoco del visitatore impostato nella variabile ID visitatore. </td> 
  </tr> 
  <tr> 
   <td> vmk </td> 
   <td> s. vmk </td> 
   <td> Nessuno </td> 
   <td> Chiave di migrazione dei visitatori; utilizzato per migrare da terze parti ai cookie di prime parti. Obsoleto. </td> 
  </tr> 
  <tr> 
   <td> vvp </td> 
   <td> s. variableprovider </td> 
   <td> Nessuno </td> 
   <td> Utilizzati nelle integrazioni Genesis </td> 
  </tr> 
  <tr> 
   <td> xact </td> 
   <td> s. transactionid </td> 
   <td> Nessuno </td> 
   <td> L'ID transazione utilizzato per collegare dati online a dati offline </td> 
  </tr> 
  <tr> 
   <td> zip </td> 
   <td> s.zip </td> 
   <td> Profilo visitatore | CAP/Codice postale </td> 
   <td> Determina il codice ZIP come definito dalla variabile </td> 
  </tr> 
  <tr> 
   <td> /5/ (per protocollo mobile) o /1/ (per protocollo non mobile) nell'URL della richiesta di immagine. </td> 
   <td> Nessuno </td> 
   <td> Nessuno </td> 
   <td> <p> Controlla l'ordine in cui i cookie e altri metodi vengono utilizzati per identificare i visitatori. </p> </td> 
  </tr> 
 </tbody> 
</table>

