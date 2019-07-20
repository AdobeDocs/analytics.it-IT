---
description: Questa sezione è destinata agli amministratori di Adobe Analytics. Si focalizza sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l'univocità e la coerenza dei collegamenti tra browser e dispositivi e migliora la gestione del riposizionamento dei collegamenti su una pagina.
seo-description: Questa sezione è destinata agli amministratori di Adobe Analytics. Si focalizza sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l'univocità e la coerenza dei collegamenti tra browser e dispositivi e migliora la gestione del riposizionamento dei collegamenti su una pagina.
seo-title: Metodologia di tracciamento dei collegamenti
solution: Analytics
title: Metodologia di tracciamento dei collegamenti
topic: Activity map
uuid: 67864 bf 9-33 cd -46 fa -89 a 8-4 d 83 d 3 b 81152
translation-type: tm+mt
source-git-commit: 4f313ae50c4d5a0f3bfec493c2d554bc8614aeef

---


# Metodologia di tracciamento dei collegamenti

Questa sezione è destinata agli amministratori di Adobe Analytics. Si focalizza sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l'univocità e la coerenza dei collegamenti tra browser e dispositivi e migliora la gestione del riposizionamento dei collegamenti su una pagina.

>[!IMPORTANT]
>
>Any link where the text (not the href) may contain PII (Personally Identifiable Information) should be implemented explicitly using [s_objectID](https://marketing.adobe.com/resources/help/en_US/sc/implement/s_objectID.html) or by excluding ActivityMap link collection with [s.ActivityMap.linkExclusions or s.ActivityMap.regionExclusions](../../../analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#section_634197EACD404AC086DF9A03B813C8C3). For more information on how Activity Map may be collecting PII data, go [here](../../../analyze/activity-map/lnk-tracking-overview.md#section_A9F016E64F33446F8916855D8C69A7C6).

Activity Map basa il tracciamento dei collegamenti su questi due ID:

* ID principale: questo è il parametro riconoscibile del collegamento.
* Regione collegamento: si tratta di un parametro secondario che consente agli utenti di specificare una stringa rappresentante l'area di collegamento globale nella pagina o nell'area geografica. Questo parametro può essere generato automaticamente se non viene fornito dall'utente.

## Primary ID {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Se l'HTML ha un valore s_ objectid, l'ID principale viene impostato su s_ objectid. In caso contrario, i seguenti parametri vengono utilizzati come ID principale (in questo ordine di priorità):

* Testo non inserito
* Alttext
* Titolo
* Src
* Azione

## Using InnerText versus using Link Action (URL) {#section_70C3573E22274522A8CC035BF18EC468}

L'azione Collegamento è l'azione eseguita dalla pagina Web quando si fa clic sul collegamento, in genere l'URL visitabile dopo aver fatto clic sul collegamento. Alcuni dei problemi che potrebbero verificarsi quando si utilizza l'Azione collegamento sono:

* con due o più collegamenti distinti con lo stesso ID
* leggibilità del collegamento
* un collegamento con più azioni (a seconda del dispositivo in cui si sta visualizzando il collegamento)

Di conseguenza, utilizziamo innertext con questi vantaggi rispetto all'uso dell'azione Collegamento (URL):

* È una buona rappresentazione dell'identità Collegamento. La duplicazione degli ID principale è notevolmente ridotta, in quanto non è comune avere più collegamenti con lo stesso testo.
* Garantisce la coerenza dell'ID principale tra dispositivi e tipi di browser.
* Non viene modificata da un riposizionamento del collegamento sulla pagina.
* Migliora la leggibilità, in modo che gli utenti possano iniziare ad analizzare i rapporti di tracciamento dei collegamenti all'esterno della Activity Map.

## Link region {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Questo nuovo attributo consente agli utenti di specificare una stringa rappresentante l'area della pagina in cui si trova il collegamento.

Ad esempio, per un collegamento "Contattaci" che si trova nella sezione del menu della pagina Web, l'utente potrebbe voler passare un parametro di tipo «Menu». Analogamente, per un collegamento "Contattaci" che si trova nel piè di pagina della pagina Web, il parametro regione può essere impostato su "piè di pagina".

Il valore Regione collegamento non è impostato sul collegamento stesso, ma su un elemento HTML nella struttura HTML DOM che include tale regione.
L'utilizzo di Area collegamento presenta i seguenti vantaggi:

* Consente di distinguere i collegamenti con lo stesso ID principale.
* L'andamento su un'area è minore dell'aspetto dinamico della pagina Web.
* Gli utenti possono visualizzare i collegamenti più performanti all'interno di un'area. Con l'opzione Regione come ancoraggio, è possibile visualizzare sovrapposizioni di collegamenti non visibili sulla pagina (Ajax, Targeting).
* Un'area può sostituire le pagine in quanto una determinata area può essere utilizzata su più pagine Web. Consente di rispondere alle domande come: «La mia area di offerta prodotto funziona meglio sulla pagina di destinazione da donna o sulla pagina di destinazione dei uomo?
* Di per sé, Regione è una dimensione rilevante per analizzare pagine Web altamente dinamiche. Questo perché rimuove il rumore a causa di una modifica continua dei collegamenti: un'area "Ultime notizie" nella pagina di destinazione CNN può presentare molti collegamenti. Ma l'area sarà sempre disponibile. Pertanto, potrebbe essere interessante determinare tendenze a livello di regione in molti giorni.

**Tracciamento regioni personalizzato**

Puoi personalizzare il parametro Regione per un collegamento (il valore predefinito è ID collegamento): Un tag impostato su «ID» utilizza tutti gli elementi HTML con un parametro «id» come Area. Quindi, impostare il tag Regione su «id» probabilmente restituisce molte aree distinte (molti degli «ID» sulla pagina). In alternativa, se desiderate implementare un'implementazione più personalizzata, potete impostare il tag regione su qualcosa di più specifico, ad esempio "region_ id".

Di seguito, potete visualizzare un codice HTML di esempio utilizzando l'attributo ID di regione predefinito, "id".

```
<div id="content"> 
  <div id="breaking_news"> 
      <a href="breaking-news.html">...</a> 
   </div> 
 <div id="todays_top_headlines"> 
      <a href="breaking-news.html">...</a> 
   </div> 
```

Se lo desiderate, potete assegnare un tag agli elementi con un identificatore stringa arbitrario, in questo caso "lpos", quindi aggiungere attributi con il nome "lpos".

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

## Configuration variables {#section_634197EACD404AC086DF9A03B813C8C3}

Queste variabili sono elencate solo a scopo di riferimento. La Mappa dell'attività deve essere configurata correttamente fuori dalla casella, ma puoi personalizzare la tua implementazione utilizzando queste variabili.

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
   <td colname="col1"> s. activitymap. regionidattribute </td> 
   <td colname="col2"> Il valore predefinito è il parametro «id». Potete impostare questo parametro su un altro parametro. </td> 
   <td colname="col3"> String that identifies the tag attribute to use as region ID from some ancestor (parent, parent.parent, ...) element of s.linkObject, i.e. <b>the element that was clicked</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. link </td> 
   <td colname="col2"> 
    <code>// solo gli attributi "title" da una funzione tag (click kedelement) {var linkid; if (click kedelement &amp; &amp; click kedelement. tagname. touppercase () = = ='A ') {linkid = click kedelement. getattribute ('title '); } return linkid; } </code>
  </td> 
   <td colname="col3"> Function that receives the clicked HTMLElement and should return a string value that represents <b>the link that was clicked</b>. <p>Se il valore restituito è falso (null, non definito, stringa vuota, 0), non viene tracciato alcun collegamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. region </td> 
   <td colname="col2"> 
    <code>// viene utilizzata solo la versione minuscola del nome di tag concatenato con il primo classname come funzione area (click kedelement) {var regionid, classname; while (click kedelement &amp; &amp; (click kedelement = click kedeldelement. parentnode)) {regionid = click kedelement. tagname; if (regionid) {return regionid. tolowercase (); }}}} </code>
  </td> 
   <td colname="col3"> Function that receives the clicked HTMLElement and should return a string value that represents <b>the region where the link was found when clicked</b>. <p>Se il valore restituito è falso (null, non definito, stringa vuota, 0), non viene tracciato alcun collegamento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. linkexclusions </td> 
   <td colname="col2"> 
    <code>// Escludi i collegamenti con una classe CSS linkesclusa speciale &lt; stile &gt;. linkesclusa {display: block; height: 1 px; left: -9999 px; overflow: hidden; position: absolute; larghezza: 1 px; } &lt;/stile &gt; &lt; a href = "next-page.html" &gt; Collegamento viene tracciato perché il collegamento non contiene testo nascosto che corrisponde al filtro.&lt;/a &gt; &lt; a href = "next-page.html" &gt; Collegamento non tracciato perché s. activitymap. linkexclusions è impostato e questo collegamento ha un testo nascosto corrispondente al filtro. &lt; span class = "linkexcluded" &gt; exclude-link 1 &lt;/span &gt; &lt;/a &gt; &lt; a href = "next-page.html" &gt; Collegamento non tracciato perché s. activitymap. linkexclusions è impostato e questo collegamento ha corrispondenza con il filtro.  &lt;span class="linkExcluded"&gt;exclude-link2&lt;/span&gt; &lt;/a&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2'; &lt;/script&gt; 
    </code> </td> 
   <td colname="col3"> <p>Stringa che riceve un elenco separato da virgole di stringhe da cercare nel testo del collegamento. Se trovato, il collegamento non viene escluso dalla mappa dell'attività. Se non viene impostato, non viene eseguito alcun tentativo per interrompere il tracciamento del collegamento tramite Activity Map. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s. activitymap. regionexclusions </td> 
   <td colname="col2"> 
    <code>// Escludi le aree nella pagina dai relativi collegamenti tracciabili da activitymap &lt; div id = "links-included" &gt; &lt; a href = "next-page.html" &gt; Link viene tracciata perché s. activitymap. regionexclusions è impostata ma non corrisponde al filtro.&lt;/a &gt; &lt;/div &gt; &lt; div id = "links-excluded" &gt; &lt; a href = "next-page.html" &gt; Collegamento non tracciato perché s. activitymap. regionexclusions è impostato e questo collegamento corrisponde al filtro.&lt;/a&gt; &lt;/div&gt; &lt;script&gt;   var s = s_gi('samplersid');   s.ActivityMap.regionExclusions = 'links-excluded'; &lt;/script&gt;
    </code> </td> 
   <td colname="col3"> <p>Stringa che riceve un elenco separato da virgole di stringhe da cercare nel testo della regione. Se trovato, il collegamento non viene escluso dalla mappa dell'attività. Se non viene impostato, non viene eseguito alcun tentativo per interrompere il tracciamento del collegamento tramite Activity Map. </p> </td> 
  </tr> 
 </tbody> 
</table>
