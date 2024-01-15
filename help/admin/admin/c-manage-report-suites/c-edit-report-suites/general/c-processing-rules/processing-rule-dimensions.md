---
description: Le dimensioni che è possibile leggere e scrivere (salvo diversa indicazione) utilizzando le regole di elaborazione.
subtopic: Processing rules
title: Dimensioni disponibili per le regole di elaborazione
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '729'
ht-degree: 100%

---

# Dimensioni disponibili per le regole di elaborazione

Le dimensioni che è possibile leggere e scrivere (salvo diversa indicazione) utilizzando le regole di elaborazione.

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
   <td colname="col2"> <p>Testo o valori personalizzati digitati direttamente nell’azione di una regola di elaborazione. Questi valori sono disponibili nelle condizioni e nelle regole successive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valore concatenato </p> </td> 
   <td colname="col2"> <p>Valori creati combinando due valori. Ad esempio, è possibile combinare categoria e nome della pagina per creare una sottocategoria. Questi valori sono disponibili nelle condizioni e nelle regole successive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Valori modificati </p> </td> 
   <td colname="col2"> <p>Se un valore di variabile viene modificato utilizzando le regole di elaborazione, il valore modificato viene utilizzato nelle condizioni e nelle regole successive. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variabili di dati contestuali </p> </td> 
   <td colname="col2"> <p>Variabili denominate inviate con un hit. </p> <p>Nota: tutti i dati contenuti in una variabile di dati contestuali devono essere copiati in una variabile di reporting per essere visualizzati in un rapporto. Le variabili di dati contestuali non sono visualizzabili in alcuna interfaccia di reporting, inclusi i feed di dati di click-stream. </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copiare una variabile di dati contestuali in una eVar </a> </p> <p> <a href="/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> Impostare un evento utilizzando una variabile di dati contestuali </a> </p> <p> <a href="/help/implement/vars/page-vars/contextdata.md"> Variabili di dati contestuali</a> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Variabili di traffico {#section_225156106F8B41F8BC1E68D58DDC2652}

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

## Attributi di hit {#section_07E69A86A47741A083FD84F112EB80D0}

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
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Nota: le chiamate di tracciamento dei collegamenti rimuovono la variabile <code>pageName</code> prima di raggiungere le regole di elaborazione. Se inserisci nuovamente un valore del nome di una pagina utilizzando le regole di elaborazione, l’hit viene considerato come una visualizzazione di pagina invece di una chiamata di tracciamento del collegamento. Adobe consiglia di verificare che il nome della pagina sia già impostato prima di modificarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL della pagina </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> o URL della pagina corrente se <code> s.pageURL</code> non è specificato. <p>Nota: le chiamate di tracciamento dei collegamenti rimuovono la variabile <code>pageURL</code> prima di raggiungere le regole di elaborazione. Se inserisci nuovamente un valore URL della pagina utilizzando le regole di elaborazione, l’hit viene considerato come una visualizzazione di pagina invece di una chiamata di tracciamento del collegamento. Adobe consiglia di verificare che l’URL della pagina sia già impostato prima di modificarlo. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro stringa di query </p> </td> 
   <td colname="col2"> <p>Valore di un parametro di stringa di query specificato nell’URL corrente oppure null se non esiste alcun parametro. Per l’URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, il valore del parametro di stringa di query <span class="syntax codeph"> cid</span> è <b>ad1</b> e il valore del parametro di stringa di query <span class="syntax codeph"> nodo</span> è <b>4</b>. </p> <p>Se utilizzi JavaScript AppMeasurement H.25.2 o versioni precedenti, l’URL della pagina potrebbe essere troncato dopo 255 caratteri. JavaScript AppMeasurement H.25.3 (rilasciato a gennaio 2013) e versioni successive forniscono l’URL completo alle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percorso pagina </p> </td> 
   <td colname="col2"> <p>Percorso dell’URL della pagina. Il percorso dell’URL <b>https://www.example.com/news/a.html?cid=ad1</b> è <span class="syntax codeph"> news/a.html</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio pagina </p> </td> 
   <td colname="col2"> <p>Il nome host completo, specificato nell’URL. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale pagina </p> </td> 
   <td colname="col2"> <p>Le ultime due sezioni del nome host della pagina. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stringa query pagina </p> </td> 
   <td colname="col2"> <p>Stringa completa di query dell’URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Destinatario che inoltra* (sola lettura) </p> </td> 
   <td colname="col2"> <p>Destinatario che inoltra HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro stringa query di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Il valore di un parametro di stringa di query specificato nell’URL di riferimento o null se non esiste alcun parametro. Per l’URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, il valore del parametro di stringa di query <span class="syntax codeph"> cid</span> è <b>ad1</b> e il valore del parametro di stringa di query <span class="syntax codeph"> nodo</span> è <b>4</b>. </p> <p>Se utilizzi JavaScript AppMeasurement H.25.2 o versioni precedenti, l’URL della pagina potrebbe essere troncato dopo 255 caratteri. JavaScript AppMeasurement H.25.3 (rilasciato a gennaio 2013) e versioni successive forniscono l’URL completo alle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Nome host completo del destinatario che inoltra. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Le ultime due sezioni del nome host del destinatario che inoltra. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stringa query di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Parametri della stringa di query contenuti nell’URL di riferimento. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Indirizzo IP (sola lettura) </p> </td> 
   <td colname="col2"> <p>Indirizzo IP riportato dal browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Agente utente (sola lettura) </p> </td> 
   <td colname="col2"> <p>Agente utente come segnalato dal browser. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versione codice AppMeasurement (sola lettura) </p> </td> 
   <td colname="col2"> <p>Versione della libreria appMeasurement utilizzata per effettuare la richiesta. Quando utilizzi i beacon per immagini, puoi compilare il modulo con un valore personalizzato che viene letto utilizzando le regole di elaborazione. Nell’URL questo valore viene visualizzato nella posizione seguente: </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/... </p> </td> 
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
   <td colname="col1"> <p>Elenco variabili 1-3 </p> </td> 
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
   <td colname="col1"> <p>CAP visitatore </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Eventi di successo {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

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
   <td colname="col1"> <p>Evento 1-1000 </p> <p>(per i clienti SiteCatalyst 15, Evento 1-100). </p> </td> 
   <td colname="col2"> <p> <code> event1</code> - <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>acquisto, scView, scAdd e altri eventi del carrello </p> </td> 
   <td colname="col2"> <p>Eventi predefiniti. </p> </td> 
  </tr> 
 </tbody> 
</table>
