---
description: Questa tabella di riferimento definisce i campi, le opzioni e gli attributi hit che puoi selezionare nella pagina Regole di elaborazione canale marketing.
seo-description: Questa tabella di riferimento definisce i campi, le opzioni e gli attributi hit che puoi selezionare nella pagina Regole di elaborazione canale marketing.
seo-title: Regole di elaborazione canale marketing - definizioni
solution: Analytics
subtopic: Canali di marketing
title: Regole di elaborazione canale marketing - definizioni
topic: Reports & Analytics
uuid: 4 e 71 ff 5 b -912 a -4 dc 0-9 c 22-4 be 74 c 5 e 3 cc 0
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Regole di elaborazione canale marketing - definizioni

Questa tabella di riferimento definisce i campi, le opzioni e gli attributi hit che puoi selezionare nella pagina Regole di elaborazione canale marketing.

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
   <td colname="col2"> <p>Attiva questo canale solo quando tutte le regole nella regola numerata sono true. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Any </p> </td> 
   <td colname="col2"> <p>Attiva questo canale quando una qualsiasi delle regole nel set di regole è true. Questa opzione è disponibile solo se nella regola numerata sono presenti più regole. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID AMO </p> </td> 
   <td colname="col2"> <p>Il codice di tracciamento principale utilizzato dalle integrazioni Pubblicitarie Cloud e Advertising Analytics. Quando una di queste integrazioni è abilitata, il prefisso del codice di tracciamento può essere utilizzato per identificare i canali specifici di Advertising Cloud. Use "AMO ID" inizia con "AL" per Cerca, "AC" per Visualizzazione, o "AO" per Social. Quando l'ID AMO è utilizzato nei canali di marketing, le metriche di click/cost/impression possono essere attribuite al canale corretto (se non sono configurate, queste metriche passeranno a Direct o None). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>AMO ED ID </p> </td> 
   <td colname="col2"> <p>Il codice di tracciamento secondario utilizzato da Advertising Cloud. Lo scopo principale di questo codice di tracciamento è fungere da chiave per l'invio di dati ad Ad Cloud. Può anche essere utilizzato per identificare le visualizzazioni clickthrough rispetto a Visualizzazione viewthroughs se desiderate vedere questi due canali di marketing separati. Questo può essere fatto impostando la logica canale di marketing per «AMO EF ID» termina con «: d "for Display clickthroughs o" AMO EF ID "termina con": i "per Visualizzazione viewthroughs. Se non desideri dividere la visualizzazione in due canali, usa la dimensione AMO ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Variabili di conversione </p> </td> 
   <td colname="col2"> <p>È composto da evar abilitati per questa suite di rapporti e si applica solo quando queste variabili sono impostate tramite il codice Adobe sulla pagina. </p> <p>See the <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/oms_sc_implement.pdf" scope="external" format="html"> Implementation Guide </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Esiste </p> </td> 
   <td colname="col2"> <p>Sono disponibili diverse selezioni, tra cui: </p> <p> 
     <ul id="ul_FE39B5F36235441FB757CC73CA2C4F51"> 
      <li id="li_6DC09918D69B443091AB94DB773D5189"> <p> <span class="uicontrol"> Non esiste </span>: Specifica che l'attributo hit non esiste nella richiesta. Ad esempio, in un dominio di provenienza, se l'utente digita un URL o fa clic su un segnalibro, l'attributo di dominio di provenienza non esiste. </p> </li> 
      <li id="li_3AB958F997974682824E85014CA266D6"> <p> <span class="uicontrol"> È vuoto </span>: Specifica che esiste un attributo hit, in genere un parametro di stringa evar o query, ma non è associato alcun valore all'attributo hit. </p> </li> 
      <li id="li_25EDA39748D141BA8173CC4C41035ABA"> <p> <span class="uicontrol"> Non contiene </span>: Consente, ad esempio, di specificare che un dominio di riferimento non contiene un valore specifico (anziché utilizzare la selezione <span class="term"> Contiene </span>). </p> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Identificare il canale come </p> </td> 
   <td colname="col2"> <p>Associates the rule with a marketing channel that you added to the <span class="wintitle"> Marketing Channel Manager </span> page. </p> <p>See <a href="../../components/c-marketing-channels/c-channels.md#task_98C9D3F5DBBC4B198E0A9ED4D3891E03" type="task" format="dita" scope="local"> Add marketing channels </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Corrisponde alle regole di rilevamento delle ricerche pagate </p> </td> 
   <td colname="col2"> <p>Una ricerca a pagamento rilevata da Adobe. Le ricerche a pagamento indicano quando le aziende pagano una tariffa per il motore di ricerca in modo da elencare il proprio sito. Le ricerche a pagamento in genere appaiono nella parte superiore o destra dei risultati della ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Corrisponde alle regole naturali di rilevamento della ricerca </p> </td> 
   <td colname="col2"> <p>Una ricerca non pagata rilevata da Adobe Report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il referente corrisponde a filtri URL interni </p> </td> 
   <td colname="col2"> <p> Una visita la cui pagina URL corrisponde a un filtro URL interno, come definito per la suite di rapporti in Strumenti di amministrazione. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Il referente non corrisponde ai filtri URL interni </p> </td> 
   <td colname="col2"> <p>L'URL di provenienza non corrisponde a un filtro URL interno, come definito per la suite di rapporti in Strumenti di amministrazione. You can use this setting with <span class="term"> Page URL </span> and <span class="term"> Exists </span> to set up a catch-all rule, so that no visits land in the <a href="../../components/c-marketing-channels/c-faq.md#section_451E42994DA247A8A7B8559C715A5EE7" type="section" format="dita" scope="local"> No Channel Identified </a> section of the report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ignora hit corrispondenti a filtri URL interni </p> </td> 
   <td colname="col2"> <p>(Per i referenti) Traccia solo hit provenienti da siti esterni. In genere, lasciate attivata questa impostazione a meno che non desideriate includere il traffico interno. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>È prima pagina di visita </p> </td> 
   <td colname="col2"> <p>La prima pagina di una visita rilevata da Adobe Report. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Pagina </p> </td> 
   <td colname="col2"> <p>Nome della pagina di una pagina Web sul sito con tag tramite il beacon Web di Adobe. This value is equivalent to <span class="varname"> s.pageName </span>. Examples include <span class="varname"> Home Page </span> and <span class="varname"> About Us </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio pagina </p> </td> 
   <td colname="col2"> <p>The domain of the page on which the visitor lands, such as <span class="filepath"> products.example.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio e percorso della pagina </p> </td> 
   <td colname="col2"> <p>The domain and path, such as <span class="filepath"> products.example.co.uk/mens/pants/overview.html </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale pagina (TLD +1) </p> </td> 
   <td colname="col2"> <p>The root domain of the page on which the visitor lands, such as <span class="filepath"> example.co.uk </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>URL della pagina </p> </td> 
   <td colname="col2"> <p>L'URL di una pagina Web sul sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio di riferimento </p> </td> 
   <td colname="col2"> <p>The domain your visitors came from before they visited your site, for example, referrers coming from <span class="filepath"> abcsite.com </span> versus <span class="filepath"> xyzsite.com </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro stringa query </p> </td> 
   <td colname="col2"> <p>If a page URL on your site looks like <span class="filepath"> https://example.com/?page=12345&amp;cat=1 </span>, then page and cat are both query string parameters. (See <span class="filepath"> https://en.wikipedia.org/wiki/Query_string </span>.) </p> <p>Potete specificare un solo parametro di stringa query per set di regole. To add additional query string parameters, use <span class="uicontrol"> ANY </span> as your operator, then add new query string parameters to the rule. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Referrer </p> </td> 
   <td colname="col2"> <p>Posizione della pagina Web (URL completo) che i visitatori avevano prima di entrare nel sito. Un referente esiste all'esterno del dominio definito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio di riferimento e percorso </p> </td> 
   <td colname="col2"> <p>Una concatenazione del dominio di riferimento e del percorso dell'URL. Gli esempi includono: </p> <p> <span class="filepath"> www.example.com/products/id/12345 </span> </p> <p> <span class="filepath"> ad.example.com/foo </span> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Parametro di riferimento </p> </td> 
   <td colname="col2"> <p>Un parametro di stringa query sull'URL del referente. For example, if your visitors come from <span class="filepath"> example.com/?page=12345&amp;cat=1 </span>, then page and cat are the referring parameters. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Dominio principale referente </p> </td> 
   <td colname="col2"> <p>Il dominio principale del referente. Un referente esiste all'esterno del dominio definito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Motore di ricerca </p> </td> 
   <td colname="col2"> <p>Un motore di ricerca come Google o Yahoo! che hanno portato visitatori al sito. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Ricerca parole chiave </p> </td> 
   <td colname="col2"> <p>Parola utilizzata per eseguire una ricerca utilizzando un motore di ricerca. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Motore di ricerca + Parole chiave </p> </td> 
   <td colname="col2"> <p>Concatenazione di Search Keyword e Motore di ricerca per identificare in modo univoco il motore di ricerca. Ad esempio, se si cerca il computer di testo, il motore di ricerca e la parola chiave sono identificati come segue: </p> 
    <code>Codice di tracciamento ricerca = " &lt; search_ type &gt;: &lt; motore di ricerca &gt;: &lt; parola chiave ricerca &gt; «where search_ type = "n» or" p ", search_ engine =" Google ", and search_ keyword =" computer " </code>
  <p><b>Nota:</b> n = naturale; p = paid </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Imposta il valore del canale su </p> </td> 
   <td colname="col2"> <p>Oltre a sapere quale canale di marketing porta un visitatore sul tuo sito, puoi sapere quale banner pubblicitario, parola chiave di ricerca o campagna e-mail all'interno del canale ottieni credito per l'attività del sito di un visitatore. Questo ID è un valore di canale memorizzato insieme al canale. Spesso questo valore è un ID campagna incorporato nella pagina di destinazione o nell'URL di provenienza. in altri casi è il motore di ricerca e la combinazione di parole chiave di ricerca, oppure l'URL di provenienza che identifica più correttamente il visitatore da un particolare canale. </p> </td> 
  </tr> 
 </tbody> 
</table>



