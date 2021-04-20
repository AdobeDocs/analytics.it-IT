---
description: Le dimensioni che è possibile leggere e scrivere (salvo diversa indicazione) utilizzando le regole di elaborazione.
subtopic: Processing rules
title: Dimensioni disponibili per le regole di elaborazione
feature: Admin Tools
uuid: ba73ab59-a8cf-491c-8757-5fb03d6b0745
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '744'
ht-degree: 5%

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
   <td colname="col1"> <p>Variabili di dati di contesto </p> </td> 
   <td colname="col2"> <p>Variabili denominate inviate con un hit. </p> <p>Nota:  Tutti i dati contenuti in una variabile di dati di contesto devono essere copiati in una variabile di reporting per essere visualizzati in un rapporto. Le variabili di dati di contesto non sono visualizzabili in alcuna interfaccia di reporting, inclusi i feed di dati ClickStream. </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copiare una variabile di dati di contesto in un eVar  </a> </p> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md"> Impostare un evento utilizzando una variabile di dati di contesto  </a> </p> <p> <a href="/help/implement/vars/page-vars/contextdata.md"> Variabili di dati di contesto</a> </p> </td> 
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

## Attributi hit {#section_07E69A86A47741A083FD84F112EB80D0}

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
   <td colname="col2"> <p> <code> s.pageName</code> </p> <p>Nota:  Le chiamate di tracciamento dei collegamenti rimuovono la variabile <code>pageName</code> prima che raggiungano le regole di elaborazione. Se inserisci nuovamente un valore del nome di una pagina utilizzando le regole di elaborazione, l'hit viene considerato come una visualizzazione di pagina invece di una chiamata di tracciamento del collegamento. Adobe consiglia di verificare che il nome della pagina sia già impostato prima di modificarlo. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL della pagina </p> </td> 
   <td colname="col2"> <code> s.pageURL</code> o l'URL della pagina corrente se non  <code> s.pageURL</code> è specificato. <p>Nota:  Le chiamate di tracciamento dei collegamenti rimuovono la variabile <code>pageURL</code> prima che raggiungano le regole di elaborazione. Se inserisci nuovamente un valore URL della pagina utilizzando le regole di elaborazione, l'hit viene considerato come una visualizzazione di pagina invece di una chiamata di tracciamento del collegamento. Adobe consiglia di verificare che l’URL della pagina sia già impostato prima di modificarlo. </p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Query String Parameter </p> </td> 
   <td colname="col2"> <p>Il valore di un parametro di stringa di query specificato nell'URL corrente oppure null se non esiste alcun parametro. Per l'URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, il valore del parametro di stringa query <span class="syntax codeph"> cid</span> è <b>ad1</b> e il valore del parametro di stringa query <span class="syntax codeph"> node</span> è <b>4</b>. </p> <p>Se utilizzi JavaScript AppMeasurement H.25.2 o versioni precedenti, l’URL della pagina potrebbe essere troncato dopo 255 caratteri. JavaScript AppMeasurement H.25.3 (rilasciato a gennaio 2013) e versioni successive forniscono l’URL completo alle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Percorso pagina </p> </td> 
   <td colname="col2"> <p>Percorso dell’URL della pagina. Il percorso dell'URL <b>https://www.example.com/news/a.html?cid=ad1</b> è <span class="syntax codeph"> news/a.html</span> . </p> </td> 
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
   <td colname="col2"> <p>Stringa completa di query dell'URL. https://en.main.example.co.uk/index.jsp?<span class="syntax codeph"> q=value</span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer* (sola lettura) </p> </td> 
   <td colname="col2"> <p>referente HTTP. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro stringa query di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Il valore di un parametro di stringa di query specificato nell'URL di riferimento o null se non esiste alcun parametro. Per l'URL <b>https://www.example.com/a.html?cid=ad1&amp;node=4</b>, il valore del parametro di stringa query <span class="syntax codeph"> cid</span> è <b>ad1</b> e il valore del parametro di stringa query <span class="syntax codeph"> node</span> è <b>4</b>. </p> <p>Se utilizzi JavaScript AppMeasurement H.25.2 o versioni precedenti, l’URL della pagina potrebbe essere troncato dopo 255 caratteri. JavaScript AppMeasurement H.25.3 (rilasciato a gennaio 2013) e versioni successive forniscono l’URL completo alle regole di elaborazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Nome host completo del referrer. https://<span class="syntax codeph"> en.main.example.co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio radice di riferimento (sola lettura) </p> </td> 
   <td colname="col2"> <p>Le ultime due sezioni del nome host del referrer. https://en.main.example.<span class="syntax codeph"> co.uk</span>/index.jsp?q=value </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stringa di query di riferimento (sola lettura) </p> </td> 
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
   <td colname="col2"> <p>Versione della libreria appMeasurement utilizzata per effettuare la richiesta. Quando utilizzi i beacon per immagini, puoi compilare il modulo con un valore personalizzato letto utilizzando le regole di elaborazione. Questo valore viene visualizzato nella posizione seguente nell'URL: </p> <p>https://server.net/b/ss/report-suite-ID/1/<span class="syntax codeph"> CODEVERSION</span>/.. </p> </td> 
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
   <td colname="col1"> <p>Variabili elenco1-3 </p> </td> 
   <td colname="col2"> <p> <code> s.list1</code> -  <code> s.list3</code> </p> </td> 
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
   <td colname="col1"> <p>CAP/codice postale del visitatore </p> </td> 
   <td colname="col2"> <p> <code> s.zip</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Eventi di successo {#section_C1946FEB64FC4F579671EC5E0D06AE8A}

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
   <td colname="col1"> <p>Evento 1-1000 </p> <p>(Per i clienti SiteCatalyst 15, evento 1-100.) </p> </td> 
   <td colname="col2"> <p> <code> event1</code> -  <code> event1000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>acquisto, scView, scAdd e altri eventi cart </p> </td> 
   <td colname="col2"> <p>Eventi predefiniti. </p> </td> 
  </tr> 
 </tbody> 
</table>
