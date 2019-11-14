---
description: Questa sezione è destinata agli amministratori di Adobe Analytics. I nuovi parametri di tracciamento dei collegamenti sono incentrati su come garantire l’univocità e la coerenza dei collegamenti tra browser e dispositivi e come migliorare la gestione del riposizionamento dei collegamenti su una pagina.
solution: Analytics
title: Metodologia di tracciamento dei collegamenti
topic: Activity map
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Metodologia di tracciamento dei collegamenti

Questa sezione è destinata agli amministratori di Adobe Analytics. I nuovi parametri di tracciamento dei collegamenti sono incentrati su come garantire l’univocità e la coerenza dei collegamenti tra browser e dispositivi e come migliorare la gestione del riposizionamento dei collegamenti su una pagina.

>[!IMPORTANT]
>
>Qualsiasi collegamento in cui il testo (non i href) può contenere informazioni PII (Personally Identifiable Information) deve essere implementato esplicitamente utilizzando [s_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) o escludendo la raccolta di collegamenti ActivityMap con [s.ActivityMap.linkExclusions o s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Per ulteriori informazioni su come la Activity Map potrebbe raccogliere dati PII, [consulta](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map basa il tracciamento dei collegamenti su questi due ID:

* ID principale: questo è il parametro riconoscibile del collegamento.
* Regione collegamento: si tratta di un parametro secondario che consente agli utenti di specificare una stringa rappresentativa dell’area di collegamento globale nella pagina o nell’area geografica. Questo parametro può essere generato automaticamente se non è fornito dall'utente.

## ID principale {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Se l'HTML ha un s_objectid, l'ID principale viene impostato per impostazione predefinita su s_objectid. In caso contrario, i seguenti parametri vengono utilizzati come ID principale (in questo ordine di priorità):

* Innertext
* Alttext
* Titolo
* Src
* Azione

## Utilizzo di InnerText e utilizzo di Link Action (URL) {#section_70C3573E22274522A8CC035BF18EC468}

L’azione Collegamento è l’azione eseguita dalla pagina Web quando si fa clic sul collegamento, in genere l’URL visitato dopo aver fatto clic sul collegamento. Alcuni dei problemi a cui potrebbe verificarsi l’utilizzo di Azione collegamento sono:

* con due o più collegamenti distinti con lo stesso ID
* leggibilità del collegamento
* un collegamento con più azioni (a seconda del dispositivo su cui si trova il collegamento)

Di conseguenza, l’utilizzo di InnerText offre i seguenti vantaggi rispetto all’utilizzo di Link Action (URL):

* È una buona rappresentazione dell'identità Collegamento. La duplicazione degli ID primari è notevolmente ridotta in quanto non è comune disporre di più collegamenti con lo stesso testo.
* Garantisce la coerenza dell'ID principale tra dispositivi e tipi di browser.
* Non viene interessato dal riposizionamento del collegamento sulla pagina.
* Migliora la leggibilità, consentendo agli utenti di iniziare ad analizzare i rapporti di tracciamento dei collegamenti all'esterno della Activity Map.

## Area collegamenti {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Questo nuovo attributo consente agli utenti di specificare una stringa rappresentativa dell'area della pagina in cui si trova il collegamento.

Ad esempio, per un collegamento "Contatti" che si trova nella sezione menu della pagina Web, l'utente potrebbe voler passare un parametro di regione "Menu". Allo stesso modo, per un collegamento "Contact Us" posizionato nel piè di pagina della pagina Web, il parametro di regione può essere impostato su "footer".

Il valore Regione collegamento non è impostato sul collegamento stesso, ma su un elemento HTML sopra la struttura DOM HTML che include tale area.
L’utilizzo di Link Region offre i seguenti vantaggi:

* Consente di distinguere i collegamenti con lo stesso ID primario.
* La tendenza in un’area è meno influenzata dall’aspetto dinamico della pagina Web.
* Gli utenti possono visualizzare i collegamenti con le prestazioni più elevate all'interno di un'area geografica. Con Regione come ancoraggio, possiamo visualizzare sovrapposizioni di collegamenti che non sono attualmente visibili sulla pagina (Ajax, Targeting).
* Una regione può sostituire le pagine come una determinata area geografica e può essere utilizzata in molte pagine Web. Consente di rispondere a domande come: "La mia regione "Offerta di prodotto" si comporta meglio sulla pagina di destinazione delle donne o sulla pagina di destinazione degli uomini?
* Di per sé, Regione è una dimensione rilevante per l'analisi di pagine Web altamente dinamiche. Questo perché rimuove il disturbo dovuto alla modifica continua dei collegamenti: una regione "Ultime notizie" nella pagina di destinazione CNN potrebbe avere molti collegamenti in continuo cambiamento. Ma la regione ci sarà sempre. Potrebbe essere interessante tendere a livello regionale in molti giorni.

**Tracciamento area personalizzato**

Puoi personalizzare il parametro Regione per un collegamento (il valore predefinito è ID collegamento): Un tag impostato su "ID" utilizza tutti gli elementi HTML con un parametro "id" come regione. Pertanto, se si imposta il tag Regione su "id", molto probabilmente verranno restituite molte aree distinte (fino a che non sono presenti "ID" diversi sulla pagina). In alternativa, se desiderate un'implementazione più personalizzata, potete impostare il tag regione su qualcosa di più specifico, ad esempio "region_id".

Di seguito potete visualizzare un esempio di HTML utilizzando l'attributo ID regione predefinito "id".

```
<div id="content"> 
  <div id="breaking_news"> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
```

Se lo si desidera, è possibile assegnare tag agli elementi con un identificatore stringa arbitrario, in questo caso "lpos", e quindi aggiungere attributi con il nome "lpos".

```
s.ActivityMap.regionIDAttribute="lpos"; 
   
<div id="nav" lpos="navbar"> 
  <ul> 
     <li> Menu Category A 
    <ul> 
      <li><a href="">Menu Item A 1</a> 
      <li><a href="">Menu Item A 2</a> 
     </ul> 
    </li> 
     <li> Menu Category B 
     <ul> 
      <li><a href="">Menu Item B 1</a>  
      <li><a href="">Menu Item B 2</a> 
  
   </ul> 
</ul> 
</div> 
  
<div id="content" > 
  <div id="breaking_news" lpos="breaking_news> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
</div>
```

## Variabili di configurazione {#configuration-vars}

Queste variabili sono elencate solo a scopo di riferimento. La Activity Map deve essere configurata correttamente ma puoi personalizzare l'implementazione utilizzando queste variabili.

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome della variabile </th> 
   <th colname="col2" class="entry"> Esempio  </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionIDAtribute </td> 
   <td colname="col2"> Il valore predefinito è "id". Potete impostare questo parametro su un altro. </td> 
   <td colname="col3"> Stringa che identifica l’attributo del tag da utilizzare come ID di regione da un elemento antenato (parent, parent.parent, ...) di s.linkObject, ovvero <b>l’elemento su cui è stato fatto clic</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.link </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;only&nbsp;ever&nbsp;use&nbsp;"title"&nbsp;attributes&nbsp;from&nbsp;A&nbsp;tags function(clickedElement){ &nbsp;&nbsp;&nbsp;var&nbsp;linkId; &nbsp;&nbsp;&nbsp;if(clickedElement&nbsp;&amp;&amp;&nbsp;clickedElement.tagName.toUpperCase()&nbsp;===&nbsp;'A'){ &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;linkId&nbsp;=&nbsp;clickedElement.getAttribute('title'); &nbsp;&nbsp;&nbsp;} &nbsp;&nbsp;&nbsp;return&nbsp;linkId; } 
    </code> </td> 
   <td colname="col3"> Funzione che riceve l'oggetto HTMLElement selezionato e deve restituire un valore di stringa che rappresenta <b>il collegamento su cui è stato fatto clic</b>. <p>Se il valore restituito è false (null, undefined, empty string, 0), non viene tracciato alcun collegamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.region </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;only&nbsp;ever&nbsp;use&nbsp;lowercase&nbsp;version&nbsp;of&nbsp;tag&nbsp;name&nbsp;concatenated&nbsp;with&nbsp;first&nbsp;className&nbsp;as&nbsp;the&nbsp;region function(clickedElement){ &nbsp;&nbsp;&nbsp;var&nbsp;regionId,className; &nbsp;&nbsp;&nbsp;while(clickedElement&nbsp;&amp;&amp;&nbsp;(clickedElement=&nbsp;clickedElement.parentNode)){ &nbsp;regionId&nbsp;=&nbsp;clickedElement.tagName; &nbsp;if(regionId){ &nbsp;return&nbsp;regionId.toLowerCase(); &nbsp;} &nbsp;} } 
    </code> </td> 
   <td colname="col3"> Funzione che riceve l'oggetto HTMLElement su cui è stato fatto clic e che deve restituire un valore di stringa che rappresenta <b>l'area in cui è stato trovato il collegamento quando l'utente ha fatto clic</b>. <p>Se il valore restituito è false (null, undefined, empty string, 0), non viene tracciato alcun collegamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;Exclude&nbsp;links&nbsp;tagged&nbsp;with&nbsp;a&nbsp;special&nbsp;linkExcluded&nbsp;CSS&nbsp;class &nbsp;&lt;style&gt; .linkExcluded{ &nbsp;&nbsp;display:&nbsp;block; &nbsp;&nbsp;height:&nbsp;1px; &nbsp;&nbsp;left:&nbsp;-9999px; &nbsp;&nbsp;overflow:&nbsp;hidden; &nbsp;&nbsp;position:&nbsp;absolute; &nbsp;&nbsp;width:&nbsp;1px; } &lt;/style&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;link&nbsp;does&nbsp;not&nbsp;have&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.&nbsp;&lt;/a&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter. &nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link1&lt;/span&gt; &lt;/a&gt; &lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter. &nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt; &nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid'); &nbsp;&nbsp;s.ActivityMap.linkExclusions&nbsp;=&nbsp;'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>Stringa che riceve un elenco di stringhe separate da virgole da cercare nel testo del collegamento. Se trovato, il collegamento viene escluso dal tracciamento della Activity Map. In caso contrario, non viene eseguito alcun tentativo di interrompere il tracciamento del collegamento per Activity Map. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>
      //&nbsp;Exclude&nbsp;regions&nbsp;on&nbsp;the&nbsp;page&nbsp;from&nbsp;its&nbsp;links&nbsp;being&nbsp;trackable&nbsp;by&nbsp;ActivityMap &lt;div&nbsp;id="links-included"&gt;&nbsp; &nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;but&nbsp;does&nbsp;not&nbsp;match&nbsp;the&nbsp;filter.&lt;/a&gt; &lt;/div&gt; &lt;div&nbsp;id="links-excluded"&gt;&nbsp; &nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;matches&nbsp;the&nbsp;filter.&lt;/a&gt; &lt;/div&gt; &lt;script&gt; &nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid'); &nbsp;&nbsp;s.ActivityMap.regionExclusions&nbsp;=&nbsp;'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>Stringa che riceve un elenco di stringhe separate da virgole da cercare nel testo della regione. Se trovato, il collegamento viene escluso dal tracciamento della Activity Map. In caso contrario, non viene eseguito alcun tentativo di interrompere il tracciamento del collegamento per Activity Map. </p> </td> 
  </tr> 
 </tbody> 
</table>
