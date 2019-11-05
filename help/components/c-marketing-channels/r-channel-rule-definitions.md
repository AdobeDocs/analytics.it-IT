---
description: Questa tabella di riferimento definisce i campi, le opzioni e gli attributi che potete selezionare nella pagina Regole di elaborazione del canale di marketing.
seo-description: Questa tabella di riferimento definisce i campi, le opzioni e gli attributi che potete selezionare nella pagina Regole di elaborazione del canale di marketing.
seo-title: 'Regole di elaborazione per il canale di marketing: definizioni'
solution: Analytics
subtopic: Canali di marketing
title: 'Regole di elaborazione per il canale di marketing: definizioni'
topic: Reports and Analytics
uuid: 4e71ff5b-912a-4dc0-9c22-4be74c5e3cc0
translation-type: tm+mt
source-git-commit: bc46011a48aa18e33ba6f1912223857f5a664f35

---


# Regole di elaborazione per il canale di marketing: definizioni

Questa tabella di riferimento definisce i campi, le opzioni e gli attributi che potete selezionare nella pagina Regole di elaborazione del canale di marketing.

<table id="table_C18A0F1C9E214EB585A29801BA2400F8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Termine </p> </th> 
   <th colname="col2" class="entry"> <p>Definizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Tutte </p> </td> 
   <td colname="col2"> <p>Attiva questo canale solo quando tutte le regole della regola numerata sono vere. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Any </p> </td> 
   <td colname="col2"> <p>Attiva questo canale quando una delle regole del set di regole è vera. Questa opzione è disponibile solo se nella regola numerata è presente più di una regola. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID AMO </p> </td> 
   <td colname="col2"> <p>Il codice di tracciamento principale utilizzato dalle integrazioni Advertising Cloud e Advertising Analytics. Quando una di queste integrazioni è abilitata, il prefisso del codice di tracciamento può essere utilizzato per identificare canali specifici di Advertising Cloud. L'utilizzo di "AMO ID" inizia con "AL" per la ricerca, "AC" per la visualizzazione o "AO" per Social. Quando l'ID AMO viene utilizzato nei canali di marketing, le metriche click/cost/impression possono essere attribuite al canale corretto (se non configurate, queste metriche andranno a Direct o Nessuno). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID AMO ED </p> </td> 
   <td colname="col2"> <p>Il codice di tracciamento secondario utilizzato da Advertising Cloud. Lo scopo principale di questo codice di tracciamento è quello di fungere da chiave per l'invio di dati ad Ad Cloud. Tuttavia, può essere utilizzato anche per identificare la visualizzazione ClickThroughs rispetto a visualizzazione ViewThroughs se si desidera visualizzarli come due canali di marketing separati. A tale scopo, è possibile impostare la logica del canale di marketing per le estremità "AMO EF ID" con ":d" per le estremità Display ClickThrough o "AMO EF ID" con ":i" per Display ViewThrough. Se non desideri dividere la visualizzazione in due canali, utilizza invece la dimensione ID AMO. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variabili di conversione </p> </td> 
   <td colname="col2"> <p>È costituito da eVar abilitate per questa suite di rapporti e si applica solo quando queste variabili sono impostate tramite il codice Adobe sulla pagina. </p> <p>Consulta la <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf"  > guida all’implementazione </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esiste </p> </td> 
   <td colname="col2"> <p>Sono disponibili diverse selezioni, tra cui: </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol"> Non Esiste </span>: Specifica che l'attributo hit non esiste nella richiesta. Ad esempio, in un dominio di riferimento, se l'utente digita un URL o fa clic su un segnalibro, l'attributo di dominio di riferimento non esiste. </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol"> Vuoto </span>: Specifica che esiste un attributo hit, in genere un parametro eVar o una stringa di query, ma non è associato alcun valore all'attributo hit. </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol"> Non Contiene </span>: Consente di specificare, ad esempio, che un dominio di riferimento non contiene un valore specifico (anziché utilizzare la selezione <span class="term"> Contiene </span>. </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificare il canale come </p> </td> 
   <td colname="col2"> <p>Associa la regola a un canale di marketing aggiunto alla pagina <span class="wintitle"> Marketing Channel Manager </span> . </p> <p>Consultate <a href="/help/components/c-marketing-channels/c-channels.md"   > Aggiunta di canali di marketing </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Corrisponde alle regole di rilevamento ricerche pagate </p> </td> 
   <td colname="col2"> <p>Ricerca a pagamento rilevata da Adobe. Le ricerche pagate sono quando le aziende pagano una tariffa per il motore di ricerca per elencare il loro sito. Le ricerche pagate vengono in genere visualizzate nella parte superiore o destra dei risultati della ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Corrisponde alle regole di rilevamento ricerche naturali </p> </td> 
   <td colname="col2"> <p>Una ricerca non a pagamento rilevata dai report Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il Referente Corrisponde Ai Filtri URL Interni </p> </td> 
   <td colname="col2"> <p> Una visita il cui URL di pagina corrisponde a un filtro URL interno, come definito per la suite di rapporti in Strumenti di amministrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il Referente Non Corrisponde Ai Filtri URL Interni </p> </td> 
   <td colname="col2"> <p>L'URL di provenienza non corrisponde a un filtro URL interno, come definito per la suite di rapporti in Strumenti di amministrazione. Potete utilizzare questa impostazione con URL <span class="term"> pagina </span> ed <span class="term"> Esiste </span> per impostare una regola catch-all, in modo che nessuna visita venga effettuata nella sezione <a href="/help/components/c-marketing-channels/c-faq.md#no-channel-identified" > Nessun canale identificato </a> del rapporto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ignora gli hit corrispondenti ai filtri URL interni </p> </td> 
   <td colname="col2"> <p>(Per i referenti) Tiene traccia solo degli hit provenienti da siti esterni. In genere, lasciate questa impostazione attivata a meno che non desideriate includere il traffico interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Prima pagina della visita </p> </td> 
   <td colname="col2"> <p>La prima pagina di una visita rilevata dai report Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pagina </p> </td> 
   <td colname="col2"> <p>Il nome della pagina Web del sito a cui è assegnato un tag mediante il Web beacon di Adobe. Questo valore è equivalente a <span class="varname"> s.pageName </span>. Alcuni esempi includono <span class="varname"> Home Page </span> e <span class="varname"> Informazioni su di noi </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio pagina </p> </td> 
   <td colname="col2"> <p>Il dominio della pagina in cui il visitatore arriva, ad esempio <span class="filepath"> products.example.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio pagina e percorso </p> </td> 
   <td colname="col2"> <p>Il dominio e il percorso, ad esempio <span class="filepath"> products.example.co.uk/mens/pants/overview.html </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale pagina (TLD+1) </p> </td> 
   <td colname="col2"> <p>Il dominio principale della pagina in cui il visitatore accede, ad esempio <span class="filepath"> example.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL della pagina </p> </td> 
   <td colname="col2"> <p>L’URL di una pagina Web sul sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio di riferimento </p> </td> 
   <td colname="col2"> <p>Il dominio di provenienza dei visitatori prima che visitassero il sito, ad esempio, i referenti provenienti da <span class="filepath"> abcsite.com </span> e <span class="filepath"> xyzsite.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro stringa query </p> </td> 
   <td colname="col2"> <p>Se l’URL di una pagina sul sito è simile a <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>, la pagina e il gatto sono entrambi parametri di stringa di query. (Vedere <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>.) </p> <p>È possibile specificare un solo parametro di stringa di query per set di regole. Per aggiungere ulteriori parametri di stringa di query, utilizzare <span class="uicontrol"> ANY </span>come operatore, quindi aggiungere nuovi parametri di stringa di query alla regola. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer </p> </td> 
   <td colname="col2"> <p>Posizione della pagina Web (URL completo) in cui si trovavano i visitatori prima di accedere al sito. Un referente esiste al di fuori del dominio definito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio e percorso di riferimento </p> </td> 
   <td colname="col2"> <p>Una concatenazione del dominio di riferimento e del percorso URL. Gli esempi includono: </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro di riferimento </p> </td> 
   <td colname="col2"> <p>Un parametro della stringa di query sull’URL del referente. Ad esempio, se i visitatori provengono da <span class="filepath"> example.com/?page=12345&amp;cat=1 </span>, i parametri di riferimento sono pagina e gatto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Riferimento a dominio radice </p> </td> 
   <td colname="col2"> <p>Il dominio radice del referente. Un referente esiste al di fuori del dominio definito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Motore di ricerca </p> </td> 
   <td colname="col2"> <p>Un motore di ricerca come Google o Yahoo! che ha portato i visitatori al tuo sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parole chiave di ricerca </p> </td> 
   <td colname="col2"> <p>Una parola utilizzata per eseguire una ricerca utilizzando un motore di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Motore di ricerca + Parole chiave </p> </td> 
   <td colname="col2"> <p>Una concatenazione della parola chiave di ricerca e del motore di ricerca per identificare in modo univoco il motore di ricerca. Ad esempio, se cercate la parola computer, il motore di ricerca e la parola chiave sono identificati come segue: </p> 
    <code>
      Search&nbsp;Tracking&nbsp;Code&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"&lt;search_type&gt;:&lt;search&nbsp;engine&gt;:&lt;search&nbsp;keyword&gt;"&nbsp;where &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;search_type&nbsp;=&nbsp;"n"&nbsp;or&nbsp;"p",&nbsp;search_engine&nbsp;=&nbsp;"Google",&nbsp;and&nbsp;search_keyword&nbsp;= &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"computer" 
    </code> <p><b></b> Nota: n = naturale; p = paid </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imposta il valore del canale su </p> </td> 
   <td colname="col2"> <p>Oltre a sapere quale canale di marketing porta un visitatore sul sito, puoi sapere quale banner pubblicitario, parola chiave di ricerca o campagna e-mail all'interno del canale riceve credito per l'attività del sito di un visitatore. Questo ID è un valore di canale memorizzato insieme al canale. Spesso questo valore è un ID campagna incorporato nella pagina di destinazione o nell’URL di provenienza; in altri casi è la combinazione di motori di ricerca e parole chiave di ricerca, o l'URL di provenienza a identificare il visitatore in modo più corretto da un determinato canale. </p> </td> 
  </tr> 
 </tbody> 
</table>
