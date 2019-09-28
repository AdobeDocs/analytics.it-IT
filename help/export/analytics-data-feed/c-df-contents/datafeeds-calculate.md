---
description: Descrive come calcolare metriche comuni utilizzando i feed di dati.
keywords: Feed dati;processo;metriche;pre-colonna;post-colonna;bots;date filter;event string;common;formule
seo-description: Descrive come calcolare metriche comuni utilizzando i feed di dati.
seo-title: Calcolare metriche
solution: Analytics
title: Calcolare metriche
topic: Reports and Analytics
uuid: a45ea5bb-7c83-468f-b94a-63add78931d7
translation-type: tm+mt
source-git-commit: 3c5cc9275c9978caf57e4e29704e23405ac24b65

---


# Calcolare metriche

Descrive come calcolare metriche comuni utilizzando i feed di dati.

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## Bot {#section_06753B95800F47668AAF52E7227F27C8}

I bot sono esclusi dai feed di dati in base alle regole [](https://marketing.adobe.com/resources/help/en_US/reference/bot_rules.html) bot definite per la suite di rapporti.

## Filtro data {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

Includi righe dall'intervallo di date che desideri includere filtrando il `date_time` campo. Il `date_time` campo è leggibile dall’utente (ad esempio, `YYYY-MM-DD HH:MM:SS`) e viene adattato al fuso orario della suite di rapporti. Ad esempio, `date_time starts with "2013-12"` include gli hit a partire da dicembre 2013.

## Stringa evento {#section_87B686512EFD4A6CA072165CB28A130A}

La stringa dell'evento in `event_list` e `post_event_list` contiene un elenco delimitato da virgole di eventi, che può avere un valore e/o un ID univoco. È consigliabile eseguire tutte le elaborazioni sul `post_event_list` perché è deduplicata e ha già applicato la logica per rimuovere gli eventi duplicati con lo stesso ID (consultate Serializzazione [](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_event_serialization.html)evento).

Per la mappatura dell'ID evento per il nome, vedete la ricerca evento fornita con il feed di dati.

Per ulteriori informazioni sugli eventi, vedere [Eventi](https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html).

## Formule per metriche comuni {#section_E26A01C234484857BF8C74443222AE41}

La tabella seguente contiene istruzioni per calcolare diverse metriche comuni.

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Modalità di calcolo </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina </td> 
   <td colname="col2"> <p> Le visualizzazioni pagina possono essere calcolate contando se esiste un valore in <code> post_pagename </code> o <code> post_page_url </code>. </p> 
    <p>Puoi usare una logica simile per contare i collegamenti personalizzati: </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_page_event = 100 </code> per contare i collegamenti personalizzati. </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_page_event = 101 </code> per contare i collegamenti dei download. </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_page_event = 102 </code> per contare i collegamenti di uscita. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Escludete tutte le righe in cui <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Escludete tutte le righe con <code> hit_source = 5,7,8,9 </code>. 5, 8 e 9 sono righe di riepilogo caricate utilizzando le origini dati. 7 rappresenta i caricamenti dell'origine dati ID transazione che non devono essere inclusi nei conteggi delle visite e dei visitatori. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">Combinate <code> post_visid_high </code>, <code> post_visid_low </code>, <code> visit_num </code>e <code> visit_start_time_gmt </code>*. Numero univoco di combinazioni. </li> 
    </ol> <p>*In rare circostanze, irregolarità di Internet, irregolarità di sistema o l'uso di ID visitatore personalizzati possono causare la duplicazione dei valori <code> visit_num </code> per lo stesso ID visitatore che non è la stessa <a href="https://marketing.adobe.com/resources/help/en_US/reference/metrics_visit.html" format="http" scope="external"> visita </a>. Per evitare i problemi che ne derivano, includete anche <code> visit_start_time_gmt </code> durante il conteggio delle visite. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Escludete tutte le righe in cui <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Escludete tutte le righe con <code> hit_source = 5,7,8,9 </code>. 5, 8 e 9 sono righe di riepilogo caricate utilizzando le origini dati. 7 rappresenta i caricamenti dell'origine dati ID transazione che non devono essere inclusi nei conteggi delle visite e dei visitatori. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">Combinate <code> post_visid_high </code> con <code> post_visid_low </code>. Numero univoco di combinazioni. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Istanze evento </td> 
   <td colname="col2"> <p>Quando un evento è impostato su un hit, <code> post_event_list </code> contiene l’evento. Il <code> post_event_list </code> viene deduplicato ed è consigliato per determinare le istanze dell'evento. </p> <p>Ad esempio: </p> 
    <code>
      post_event_list = 1.200 </code> <p>Indica un'istanza di <code> purchase </code> e <code> event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Escludete tutte le righe in cui <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Escludete tutte le righe con <code> hit_source = 5,8,9 </code>. Si tratta di righe di riepilogo caricate utilizzando le origini dati. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Conta il numero di volte in cui il valore di ricerca dell’evento viene visualizzato in <code> post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Istanze eVar </td> 
   <td colname="col2"> <p>Quando un eVar viene impostato su un hit, <code> event_list </code> contiene un'istanza di tale eVar. </p> <p>Ad esempio: </p> 
    <code>
      post_event_list&amp;nbsp;=&amp;nbsp;100,101,106 </code> <p>Indica un'istanza di <code> eVar1 </code>, <code> eVar2 </code>e <code> Var7 </code>. Ciò significa che è stato impostato un valore per queste tre eVar sull’hit. </p> <p>Per calcolare le istanze per le eVar, utilizzare la stessa logica descritta nelle istanze <i></i> Evento sopra, ma contare il numero di volte in cui la ricerca eVar viene visualizzata nell'elenco <code> post_event_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata </td> 
   <td colname="col2"> <p>Per calcolare il tempo trascorso, devi raggruppare gli hit per visita, quindi ordinarli in base al numero di hit all’interno della visita. </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Escludete tutte le righe in cui <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Raggruppare gli hit per una visita concatenando <code> visid_high </code>, <code> visid_low </code>e <code> visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Ordina gli hit per ogni visita per <code> visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Utilizzando <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-page-event.md#concept_A3AC076C3728445EB4CC572A6EDA5263" format="dita" scope="local"> page_event </a>, filtrate i tipi di hit desiderati. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">Trova gli hit in cui è impostato il valore per il quale desideri tenere traccia del tempo trascorso. Ad esempio: 
      hit 1 <code>: post_prop1=hit rosso 2: post_prop1=blu </code> </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Sottrai il <code> post_cust_hit_time </code> per l’hit 1 dal <code> post_cust_hit_time </code> per l’hit 2 per determinare i secondi tra questi due hit. Il risultato è il tempo impiegato per <code> post_prop1=rosso </code>. Se questo restituisce un numero negativo, indica che l’hit è stato ricevuto fuori ordine e che il calcolo deve essere eliminato. </li> 
    </ol> <p>Questa logica può essere estesa per calcolare il tempo impiegato per altri valori. Quando si calcola il tempo trascorso, Analytics calcola il tempo trascorso in base all’ora in cui il valore è stato impostato in una <code> traccia </code> ( <code> page_event=0 </code>) o <code> trackLink </code> ( <code> page_event=10|11|12 </code>), fino al momento della visualizzazione della pagina successiva ( <code> tracciamento </code> ). </p> <p>Quando si crea un rapporto sul tempo trascorso per un periodo specifico, reporting e analisi di marketing e analisi ad hoc valutano gli hit oltre il periodo di reporting, per determinare il tempo trascorso per i valori all'interno del periodo di reporting, tranne quando la data di inizio e/o di fine del periodo è su un limite mensile. A causa della complessità di questi calcoli, potrebbe essere difficile far corrispondere esattamente il tempo impiegato dalle metriche. Data Warehouse non valuta gli hit oltre il periodo di reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entrate, ordini, unità </td> 
   <td colname="col2"> <p>La conversione della valuta viene applicata all' <code> post_product_list </code> in base alle impostazioni per la suite di rapporti, pertanto è consigliabile utilizzare tale colonna. </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Escludete tutte le righe in cui <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Escludete tutte le righe con <code> hit_source = 5,8,9 </code>. 5-9 rappresentano le righe di riepilogo caricate utilizzando le origini dati. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignora i dati di acquisto per le righe in cui <code> duplicate_purchase = 1 </code>. Questo flag indica che l'acquisto è un duplicato (ovvero un hit con lo stesso <code> ID acquisto </code> è già stato registrato). </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p>Il <code> post_product_list </code> utilizza la stessa sintassi di <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_products.html" format="http" scope="external"> s.products </a>, pertanto puoi analizzare questa stringa per calcolare le metriche. Ad esempio: </p> 
      <code>
        ;Formatori incrociati;1;69.95,;Calzature atletiche;10;29.99 </code> <p>Analizzando questa stringa, è possibile determinare che 1 paio di cross-trainer sono stati acquistati per $69,95, e che i ricavi totali da questo acquisto sono stati $99,94. </p> </li> 
    </ol> <p>Nota:  Analytics consente di trasmettere gli eventi di valuta che contengono ricavi di prodotto attraverso la stringa degli eventi, pertanto potrebbe essere necessario contabilizzare i ricavi che non sono nella stringa dei prodotti. Vedere Eventi <i></i> numerici/valutari in <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/c_events.html" format="http" scope="external"> s.events </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
