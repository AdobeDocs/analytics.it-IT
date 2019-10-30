---
description: Le dimensioni che è possibile leggere e scrivere (se non diversamente specificato) utilizzando le regole di elaborazione.
seo-description: Le dimensioni che è possibile leggere e scrivere (se non diversamente specificato) utilizzando le regole di elaborazione.
seo-title: Dimensioni disponibili per le regole di elaborazione
solution: Analytics
subtopic: Regole di elaborazione
title: Dimensioni disponibili per le regole di elaborazione
topic: Strumenti di amministrazione
uuid: ba73ab59-a8cf-491c-8757-5fb03d6b0745
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Dimensioni disponibili per le regole di elaborazione

Le dimensioni che è possibile leggere e scrivere (se non diversamente specificato) utilizzando le regole di elaborazione.

## Valori personalizzati e dati contestuali {#section_7A5E1810CAC34B0BBC69F8F5F7C75AA5}

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
   <td colname="col2"> <p>Testo o valori personalizzati digitati direttamente nell'azione di una regola di elaborazione. Questi valori sono disponibili in condizioni e regole successive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valore concatenato </p> </td> 
   <td colname="col2"> <p>Valori creati combinando due valori. Ad esempio, categoria e nome pagina possono essere combinati per creare una sottocategoria. Questi valori sono disponibili in condizioni e regole successive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valori modificati </p> </td> 
   <td colname="col2"> <p>Se un valore di variabile viene modificato utilizzando le regole di elaborazione, il valore modificato viene utilizzato nelle condizioni e nelle regole successive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variabili dati di contesto </p> </td> 
   <td colname="col2"> <p>Variabili denominate inviate con un hit. </p> <p>Nota:  Tutti i dati contenuti in una variabile dati contestuali devono essere copiati in una variabile di reporting per essere visualizzati in un report. Le variabili di dati di contesto non sono visualizzabili in alcuna interfaccia di reporting, inclusi i feed di dati ClickStream. </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md" format="dita" scope="local"> Copiare una variabile di dati di contesto in una eVar </a> </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md" format="dita" scope="local"> Impostazione di un evento utilizzando una variabile di dati di contesto </a> </p> <p> <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/context_data_variables.html" format="http" scope="external"> Variabili dati di contesto</a> </p> </td> 
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
   <td colname="col2"> <p> <code> prop1 - prop75</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Gerarchia 1-5 </p> </td> 
   <td colname="col2"> <p> <code> hier1 - hier5</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Sezione del sito </p> </td> 
   <td colname="col2"> <p> <code> s.channel </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Server </p> </td> 
   <td colname="col2"> <p> <code> s.server </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Attributi Hit {#section_07E69A86A47741A083FD84F112EB80D0}

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
   <td colname="col2"> <p>La suite di rapporti su cui viene eseguita la regola di elaborazione, che potrebbe non essere la suite di rapporti originale specificata in AppMeasurement. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Nome pagina </p> </td> 
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Nota:  Una visualizzazione di pagina viene conteggiata in tutti gli hit in cui il nome della pagina non è vuoto. Quando viene tracciato un collegamento, il server di raccolta dati rimuove il nome della pagina dall’hit in modo da non conteggiare le visualizzazioni della pagina. Se si reinserisce un nome di pagina in queste chiamate utilizzando le regole di elaborazione, verrà conteggiata una visualizzazione di pagina. È consigliabile verificare che il nome della pagina sia già impostato prima di modificare il nome della pagina. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL della pagina </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> oppure l'URL della pagina corrente, se non <code> s.pageURL</code> è specificato. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro stringa query </p> </td> 
   <td colname="col2"> <p>Il valore di un parametro di stringa di query specificato nell'URL corrente, o null se non esiste alcun parametro. Per l’URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, il valore del parametro della stringa query <span class="syntax codeph"> cid</span> è <b>ad1</b>e il valore del nodo <span class="syntax codeph"> del parametro della stringa query</span> è <b>4</b>. </p> <p>Se si esegue JavaScript AppMeasurement H.25.2 o versioni precedenti, l'URL della pagina potrebbe essere troncato dopo 255 caratteri. JavaScript AppMeasurement H.25.3 (rilasciato a gennaio 2013) e versioni successive forniscono l'URL completo alle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percorso pagina </p> </td> 
   <td colname="col2"> <p>Percorso dell’URL della pagina. Il percorso dell’URL <b>https://www.example.com/news/a.html?cid=ad1</b> è <span class="syntax codeph"> news/a.html</span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio pagina </p> </td> 
   <td colname="col2"> <p>Il nome host completo, specificato nell'URL. https://<span class="syntax codeph"> en.main.example.co.uk</span>?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale pagina </p> </td> 
   <td colname="col2"> <p>Le ultime due sezioni del nome host della pagina. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stringa query pagina </p> </td> 
   <td colname="col2"> <p>Stringa di query completa dell'URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer* (sola lettura) </p> </td> 
   <td colname="col2"> <p>Referente HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro di stringa query di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Il valore di un parametro di stringa di query specificato nell'URL di provenienza, o null se non esiste alcun parametro. Per l’URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, il valore del parametro della stringa query <span class="syntax codeph"> cid</span> è <b>ad1</b>e il valore del nodo <span class="syntax codeph"> del parametro della stringa query</span> è <b>4</b>. </p> <p>Se si esegue JavaScript AppMeasurement H.25.2 o versioni precedenti, l'URL della pagina potrebbe essere troncato dopo 255 caratteri. JavaScript AppMeasurement H.25.3 (rilasciato a gennaio 2013) e versioni successive forniscono l'URL completo alle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Il nome host completo del referente. https://<span class="syntax codeph"> en.main.example.co.uk</span>?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Le ultime due sezioni del nome host del referente. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stringa query di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Parametri della stringa di query contenuti nell’URL di provenienza. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo IP (sola lettura) </p> </td> 
   <td colname="col2"> <p>Indirizzo IP come segnalato dal browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agente utente (sola lettura) </p> </td> 
   <td colname="col2"> <p>Agente utente come segnalato dal browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione codice AppMeasurement (sola lettura) </p> </td> 
   <td colname="col2"> <p>Versione della libreria appMeasurement utilizzata per effettuare la richiesta. Quando si utilizzano i beacon per immagini, è possibile inserirli con un valore personalizzato che viene letto utilizzando le regole di elaborazione. Questo valore viene visualizzato nella posizione seguente nell’URL: </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili di conversione {#section_311856B21B3B49DBAA0539CFA06C409F}

<table id="table_E28729026EDA485989178A3B887B5983"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>eVar 1-N </p> </td> 
   <td colname="col2"> <p> <code> evar1</code> - <code> evarN</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice di tracciamento campagna </p> </td> 
   <td colname="col2"> <p> <code> s.campaign</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice della valuta </p> </td> 
   <td colname="col2"> <p> <code> s.currencyCode</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Elenca variabili1-3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> - <code> s.list3</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID acquisto </p> </td> 
   <td colname="col2"> <p> <code> s.purchaseID</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID transazione </p> </td> 
   <td colname="col2"> <p> <code> s.transactionID </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stato visitatore </p> </td> 
   <td colname="col2"> <p> <code> s.state</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Codice postale visitatore </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Success Events {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

Le regole di elaborazione possono impostare gli eventi ma non possono leggerli come condizioni.

<table id="table_926ED12B58CA4FB685D799DC6EE567C0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Evento </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Evento 1-1000 </p> <p>(per i clienti di SiteCatalyst 15, evento 1-100.) </p> </td> 
   <td colname="col2"> <p> <code> event1</code> - <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>acquisto, scView, scAdd e altri eventi del carrello </p> </td> 
   <td colname="col2"> <p>Eventi predefiniti. </p> </td> 
  </tr> 
 </tbody> 
</table>

