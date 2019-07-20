---
description: Descrive come calcolare le metriche comuni utilizzando i feed di dati.
keywords: Feed dati; processo; metriche; pre column; post, colonna; bot; filtro della data; evento, stringa; common; formule
seo-description: Descrive come calcolare le metriche comuni utilizzando i feed di dati.
seo-title: Metriche calcolate
solution: Analytics
title: Metriche calcolate
topic: Reports & Analytics
uuid: a 45 ea 5 bb -7 c 83-468 f-b 94 a -63 add 78931 d 7
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Metriche calcolate

Descrive come calcolare le metriche comuni utilizzando i feed di dati.

<!--Meike, I commented out this heading because it contains no content, and I'm troubleshooting a dita error-Bob
## Pre vs. Post column {#section_19967AF2FD9D44D6A8EC30F77E71F2ED}
-->

## Bots {#section_06753B95800F47668AAF52E7227F27C8}

Bots are excluded from data feeds according to the [bot rules](https://marketing.adobe.com/resources/help/en_US/reference/?f=bot_rules) defined for your report suite.

## Date filtering {#section_3BFF4F7EED1F4FA69EBF12BF98B347E8}

Include rows from the date range you want included by filtering the `date_time` field. `date_time` Il campo è leggibile (ad esempio, `YYYY-MM-DD HH:MM:SS`) e viene regolato nel fuso orario della suite di rapporti. For example, `date_time starts with "2013-12"` includes hits from December 2013.

## Event string {#section_87B686512EFD4A6CA072165CB28A130A}

The event string in `event_list` and `post_event_list` contains a comma-delimited list of events, which may have a value and/or a unique ID. We recommend doing all processing on the `post_event_list` because it is de-duplicated and has already applied logic to remove duplicate events with the same ID (see [Event Serialization](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_event_serialization)).

Per l'ID evento alla mappatura del nome, consultate la ricerca dell'evento distribuita con il feed di dati.

For more information on events, see [Events](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_events).

## Formulas for common metrics {#section_E26A01C234484857BF8C74443222AE41}

La tabella seguente contiene istruzioni per calcolare diverse metriche comuni.

<table id="table_814EA73C01EE4B2CA3CEB2839E19ADF9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metrica </th> 
   <th colname="col2" class="entry"> Come calcolare </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Visualizzazioni pagina </td> 
   <td colname="col2"> <p> Page views can be calculated by counting when there is either a value in <code> post_pagename </code> or <code> post_page_url </code>. </p> 
    <p>Potete usare logica simile per contare collegamenti personalizzati: </p> 
    <ul id="ul_8DFBEE3ED30C465D8E55B1F3880D5263"> 
     <li id="li_009F2B7E3F9443889AE95B3358169444"> <code> post_ page_ event = 100 </code> per contare i collegamenti personalizzati. </li> 
     <li id="li_866DA2F5C2404347863CD1417F822FE8"> <code> post_ page_ event = 101 </code> per contare i collegamenti di download. </li> 
     <li id="li_4BC6E62CE8B1474DB22448FA32C9EE01"> <code> post_ page_ event = 102 </code> per il conteggio dei collegamenti. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visite </td> 
   <td colname="col2"> 
    <ol id="ol_FE1831195A474650B07D7820DCD38728"> 
     <li id="li_274590E937A142D19B204768B1F10325">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_038B8FF66EA44E138C8A8932DA7B39E5">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8 e 9 sono righe di riepilogo caricate utilizzando le origini dati. 7 rappresenta i caricamenti delle origini dati ID transazione che non devono essere inclusi nei conteggi dei visitatori e delle visite. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_7FCD9BDF4D8547719420B34BA48BFA2D">Combine <code> post_visid_high </code>, <code> post_visid_low </code>, <code> visit_num </code>, and <code> visit_start_time_gmt </code>*. Conta un numero univoco di combinazioni. </li> 
    </ol> <p>*In rare circumstances, internet irregularities, system irregularities, or the use of custom visitor IDs can result in duplicate <code> visit_num </code> values for the same visitor ID that are not the same <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=metrics_visit" format="http" scope="external"> visit </a>. To avoid resulting issues, also include <code> visit_start_time_gmt </code> when counting visits. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitatori </td> 
   <td colname="col2"> 
    <ol id="ol_E2BC9235A3164EF5936EFC5D9E9327D0"> 
     <li id="li_2C145CA54EBF4B358FC7DC78D8DA577D">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_9EF364652A214A4D9B66552BC6BBE527">Exclude all rows with <code> hit_source = 5,7,8,9 </code>. 5, 8 e 9 sono righe di riepilogo caricate utilizzando le origini dati. 7 rappresenta i caricamenti delle origini dati ID transazione che non devono essere inclusi nei conteggi dei visitatori e delle visite. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a> </li> 
     <li id="li_4AB5129315644A29987E8FCB9C9F9C39">Combine <code> post_visid_high </code> with <code> post_visid_low </code>. Conta un numero univoco di combinazioni. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Istanze evento </td> 
   <td colname="col2"> <p>When an event is set on a hit, <code> post_event_list </code> contains the event. The <code> post_event_list </code> is de-duplicated and is recommended to determine event instances. </p> <p>Ad esempio: </p> 
    <code>post_ event_ list = 1,200 </code>
  <p>Indicates an instance of <code> purchase </code> and <code> event1 </code>. </p> 
    <ol id="ol_84B529A668A54686957D1EB36D944467"> 
     <li id="li_F953D7668C704C1AB7970123E369472A">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_65B0B504DB654479844EAE490D9283EB">Exclude all rows with <code> hit_source = 5,8,9 </code>. Queste sono righe di riepilogo caricate utilizzando le origini dati. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_FB1C31048EC7415088F41E8CDC01AEBD">Count the number of times the event lookup value appears in <code> post_event_list </code>. </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Istanze evar </td> 
   <td colname="col2"> <p>When an eVar is set on a hit, <code> event_list </code> contains an instance of that eVar. </p> <p>Ad esempio: </p> 
    <code>post_ event_ list &amp; amp; nbsp; = &amp; amp; nbsp; 100,101,106 </code>
  <p>Indicates an instance of <code> eVar1 </code>, <code> eVar2 </code>, and <code> eVar7 </code>. Ciò significa che un valore per queste tre evar è stato impostato sull'hit. </p> <p>To calculate instances for eVars, use the same logic explained in <i>Event instances</i> above, but count the number of times the eVar lookup appears in the <code> post_event_list </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Durata </td> 
   <td colname="col2"> <p>Per calcolare il tempo trascorso, devi raggruppare gli hit per visita, quindi ordinarli in base al numero di hit all'interno della visita. </p> 
    <ol id="ol_946E7CD6005A42EB9A4B79268BF84066"> 
     <li id="li_D109FAF4686D4935B7A6DCA5D383612F">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_D88F3691DB6746EBA84AA52841E56803">Group hits for a visit by concatenating <code> visid_high </code>, <code> visid_low </code>, and <code> visit_num </code>. </li> 
     <li id="li_08792F3BDFEA4DA29E0983C4BE65D73B">Order hits for each visit by <code> visit_page_num </code>. </li> 
     <li id="li_4B956734DBB84603B86DDA6A2B0B41A0">Using <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-page-event.md#concept_A3AC076C3728445EB4CC572A6EDA5263" format="dita" scope="local"> page_event </a>, filter the types of hits you want. </li> 
     <li id="li_2C5AC0477CFC409B8F169079354C8226">Trova hit in cui il valore di cui desideri tenere traccia viene impostato. For example: 
      <code>
        hit 1: post_prop1=red hit 2: post_prop1=blue 
      </code> </li> 
     <li id="li_20106B322F7B45CE8D2FBD9B0CB3D60D">Subtract the <code> post_cust_hit_time </code> for hit 1 from the <code> post_cust_hit_time </code> for hit 2 to determine the seconds between these two hits. The result is the time spent for <code> post_prop1=red </code>. Se questo determina un numero negativo, indica che l'hit è stato ricevuto e il calcolo deve essere eliminato. </li> 
    </ol> <p>Questa logica può essere estesa per calcolare il tempo impiegato per altri valori. When calculating time spent, Analytics calculates time spent based on the time the value was set in a <code> track </code> ( <code> page_event=0 </code>) or <code> trackLink </code> ( <code> page_event=10|11|12 </code>) call, to the time of the next page view ( <code> track </code> call). </p> <p>Quando si trascina il tempo trascorso per un periodo specifico, reporting e analisi di marketing e analisi ad hoc valutano gli hit oltre il periodo di reporting per determinare il tempo trascorso per i valori nel periodo di reporting, a meno che la data di inizio e/o di fine del periodo di tempo sia su un limite mensile. A causa della complessità di questi calcoli, potrebbe essere difficile rispettare esattamente le metriche dedicate. Data warehouse non valuta gli hit oltre il periodo di reporting. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ricavi, ordini, unità </td> 
   <td colname="col2"> <p>Currency conversion is applied to the <code> post_product_list </code> according to the settings for the report suite, so using that column is recommended. </p> 
    <ol id="ol_03D62086EDDE42AD82049830D85FDC69"> 
     <li id="li_2A5B8205EA30492986C35DC382B91F16">Exclude all rows where <code> exclude_hit &gt; 0 </code>. </li> 
     <li id="li_6417C228AC414B01A30F85BE4842ED3C">Exclude all rows with <code> hit_source = 5,8,9 </code>. 5-9 rappresenta le righe di riepilogo caricate utilizzando le origini dati. See <a href="../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42" format="dita" scope="local"> Hit Source Lookup </a>. </li> 
     <li id="li_C48F91C74F5E4286B5F0B285E33AF733">Ignore purchase data for rows where <code> duplicate_purchase = 1 </code>. This flag indicates that the purchase is a duplicate (meaning that a hit with the same <code> purchaseID </code> was already recorded). </li> 
     <li id="li_FA1639FEF516419BA1BFDC37B063B346"> <p><code> post_ product_ list </code> usa la stessa sintassi di <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_products" format="http" scope="external"> s. products </a>, per analizzare la stringa per calcolare le metriche. Ad esempio: </p> 
      <code>; Cross Trainers; 1; 69.95; Calzini sportive; 10; 29.99 </code>
  <p>Analizzando questa stringa, potete determinare che 1 accoppiatori di cross trainer sono stati acquistati per $ 69.95 e che il fatturato totale derivante da questo acquisto era di $ 99.94. </p> </li> 
    </ol> <p>Nota: Analytics consente agli eventi valuta contenenti entrate sui prodotti di essere trasferiti attraverso la stringa degli eventi, pertanto potrebbe essere necessario tenere conto delle entrate che non si trovano nella stringa products. See <i>Numeric/Currency Events</i> in <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=c_events" format="http" scope="external"> s.events </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>
