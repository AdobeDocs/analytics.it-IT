---
description: Dimensioni che puoi leggere e scrivere (se non diversamente specificato) utilizzando le regole di elaborazione.
seo-description: Dimensioni che puoi leggere e scrivere (se non diversamente specificato) utilizzando le regole di elaborazione.
seo-title: Dimensioni disponibili per le regole di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Dimensioni disponibili per le regole di elaborazione
topic: Strumenti di amministrazione
uuid: ba 73 ab 59-a 8 cf -491 c -8757-5 fb 03 d 6 b 0745
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Dimensioni disponibili per le regole di elaborazione

Dimensioni che puoi leggere e scrivere (se non diversamente specificato) utilizzando le regole di elaborazione.

## Custom Values &amp; Context Data {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

<table id="table_5011C501D5DC489E87A42FFC51DEB40D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Valore </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Valore personalizzato </p> </td> 
   <td colname="col2"> <p>Testo personalizzato o valori digitati direttamente nell'azione di una regola di elaborazione. Tali valori sono disponibili nelle regole e nelle regole successivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valore concatenato </p> </td> 
   <td colname="col2"> <p>Valori creati combinando due valori. Ad esempio, la categoria e il nome della pagina possono essere combinati per creare una sottocategoria. Tali valori sono disponibili nelle regole e nelle regole successivi. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valori modificati </p> </td> 
   <td colname="col2"> <p>Se viene modificato un valore di variabile utilizzando le regole di elaborazione, il valore modificato viene utilizzato nelle regole e nelle regole successive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variabili dati di contesto </p> </td> 
   <td colname="col2"> <p>Variabili denominate che vengono inviate con un hit. </p> <p>Nota: Tutti i dati contenuti in una variabile di dati di contesto devono essere copiati in una variabile di reporting per essere visualizzati in un report. Le variabili di dati di contesto non sono visualizzabili in alcuna interfaccia di reporting, inclusi feed dati clickstream. </p> <p> <a href="../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md#concept_43AA4980A2D847D6A3BEC50BCC0780E7" format="dita" scope="local"> Copiare una variabile dati di contesto in una evar </a> </p> <p> <a href="../../../admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md#concept_359B4E165ED442938A8EB6A55A725682" format="dita" scope="local"> Impostare un evento utilizzando una variabile dati di contesto </a> </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=context_data_variables" format="http" scope="external"> Variabili dati di contesto</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Traffic Variables {#section_225156106F8B41F8BC1E68D58DDC2652}

<table id="table_575F618C59DC4933BC77F935518EAE39"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>prop 1-75 </p> </td> 
   <td colname="col2"> <p> <code> prop 1 - prop 75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerarchia 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier 1 - hier 5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sezione sito </p> </td> 
   <td colname="col2"> <p> <code> s. channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p> <code> s. server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Hit Attributes {#section_07E69A86A47741A083FD84F112EB80D0}

<table id="table_9011B1FA462B4DBBAA58FC2D6D638DA1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Attributo </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID suite di rapporti (sola lettura) </p> </td> 
   <td colname="col2"> <p>La suite di rapporti su cui viene eseguita la regola di elaborazione, che potrebbe non essere la suite di rapporti originale specificata in appmeasurement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome pagina </p> </td> 
   <td colname="col2"> <p> <code> s. pagename</code> </p> <p>Nota: Una visualizzazione di pagina viene conteggiata su tutti gli hit in cui il nome della pagina non è vuoto. Quando viene tracciato un collegamento, il server di raccolta dati rimuove il nome della pagina dall'hit in modo che le visualizzazioni di pagina non vengano conteggiate. Se reinserisce il nome di una pagina in queste chiamate utilizzando le regole di elaborazione, viene conteggiata una visualizzazione di pagina. È consigliabile verificare che il nome della pagina sia già impostato prima di modificare il nome della pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL della pagina </p> </td> 
   <td colname="col2"> <code> s. pageurl</code> o l'URL della pagina corrente se <code> s. pageurl</code> non è specificato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro stringa query </p> </td> 
   <td colname="col2"> <p>Il valore di un parametro stringa query specificato nell'URL corrente, oppure null se non esiste alcun parametro. For the URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, the value of Query String Parameter <span class="syntax codeph"> cid</span> is <b>ad1</b>, and the value of Query String Parameter <span class="syntax codeph"> node</span> is <b>4</b>. </p> <p>Se esegui javascript appmeasurement H .25 .2 o versione precedente, l'URL della pagina potrebbe essere troncato dopo 255 caratteri. Javascript appmeasurement H .25 .3 (rilasciato il 2013 gennaio) e successivamente fornisce l'URL completo alle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percorso pagina </p> </td> 
   <td colname="col2"> <p>Percorso dell'URL della pagina. The path of the URL <b>https://www.example.com/news/a.html?cid=ad1</b> is <span class="syntax codeph"> news/a.html</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio pagina </p> </td> 
   <td colname="col2"> <p>Nome host completo, specificato nell'URL. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale pagina </p> </td> 
   <td colname="col2"> <p>Le ultime due sezioni del nome host della pagina. https://en.main.example.<span class="syntax codeph"> co.uk/index.jsp?q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stringa query pagina </p> </td> 
   <td colname="col2"> <p>La stringa di query completa dell'URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q = valore</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer * (sola lettura) </p> </td> 
   <td colname="col2"> <p>Referente HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro stringa di query di provenienza (sola lettura) </p> </td> 
   <td colname="col2"> <p>Il valore di un parametro stringa query specificato nell'URL di provenienza, oppure null se non esiste alcun parametro. For the URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, the value of Query String Parameter <span class="syntax codeph"> cid</span> is <b>ad1</b>, and the value of Query String Parameter <span class="syntax codeph"> node</span> is <b>4</b>. </p> <p>Se esegui javascript appmeasurement H .25 .2 o versione precedente, l'URL della pagina potrebbe essere troncato dopo 255 caratteri. Javascript appmeasurement H .25 .3 (rilasciato il 2013 gennaio) e successivamente fornisce l'URL completo alle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Il nome host completo del referente. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale referente (sola lettura) </p> </td> 
   <td colname="col2"> <p>Le ultime due sezioni del nome host del referente. https://en.main.example.<span class="syntax codeph"> co.uk/index.jsp?q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stringa query di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Parametri stringa query contenuti nell'URL di provenienza. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q = valore</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo IP (sola lettura) </p> </td> 
   <td colname="col2"> <p>Indirizzo IP indicato dal browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agente utente (sola lettura) </p> </td> 
   <td colname="col2"> <p>Agente utente indicato dal browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione codice appmeasurement (sola lettura) </p> </td> 
   <td colname="col2"> <p>La versione della libreria appmeasurement utilizzata per effettuare la richiesta. Quando usi i beacon immagine, puoi comporre questo valore con un valore personalizzato che viene letto utilizzando le regole di elaborazione. Questo valore viene visualizzato nella posizione seguente nell'URL: </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## Conversion Variables {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar 1</code> - <code> evarn</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice di tracciamento campagna </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice della valuta </p> </td> 
   <td colname="col2"> <p> <code> s. currencycode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elenca variabili 1-3 </p> </td> 
   <td colname="col2"> <p> <code> s. list 1</code> - <code> s. list 3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID acquisto </p> </td> 
   <td colname="col2"> <p> <code> s. purchaseid</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID transazione </p> </td> 
   <td colname="col2"> <p> <code> s. transactionid </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato visitatore </p> </td> 
   <td colname="col2"> <p> <code> s. state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>CAP/Codice postale </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Success Events {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

Le regole di elaborazione possono impostare eventi ma non possono leggerli come condizioni.

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Evento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Event 1-1000 </p> <p>(per i clienti sitecatalyst 15, Event 1-100.) </p> </td> 
   <td colname="col2"> <p> <code> event 1</code> - <code> event 1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>acquisto, scview, cetd e altri eventi carrello </p> </td> 
   <td colname="col2"> <p>Eventi predefiniti. </p> </td> 
  </tr> 
 </tbody> 
</table>

