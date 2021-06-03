---
description: Questa sezione è destinata agli amministratori di Adobe Analytics. Si concentra sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l’univocità e la coerenza dei collegamenti tra browser e dispositivi, e come migliorano la gestione del riposizionamento dei collegamenti su una pagina.
title: Metodologia di tracciamento dei collegamenti
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: Business Practitioner, Administrator
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '1000'
ht-degree: 1%

---

# Metodologia di tracciamento dei collegamenti

Questa sezione è destinata agli amministratori di Adobe Analytics. Si concentra sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l’univocità e la coerenza dei collegamenti tra browser e dispositivi, e come migliorano la gestione del riposizionamento dei collegamenti su una pagina.

>[!IMPORTANT]
>
>Qualsiasi collegamento in cui il testo (non il href) può contenere PII (personalmente identificabili) deve essere implementato esplicitamente utilizzando [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html) o escludendo la raccolta di collegamenti ActivityMap con [s.ActivityMap.linkExclusions o s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Per ulteriori informazioni sulla raccolta dei dati PII da parte di Activity Map, consulta [qui](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map basa il tracciamento dei collegamenti su questi due ID:

* ID principale: questo è il parametro riconoscibile del collegamento.
* Regione collegamento: si tratta di un parametro secondario che consente agli utenti di specificare una stringa rappresentativa dell’area di collegamento complessiva nella pagina o nell’area geografica. Questo parametro può essere generato automaticamente se non viene fornito dall’utente.

## ID principale {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Se l’HTML ha un s_object, l’ID principale viene impostato automaticamente su s_object. In caso contrario, i seguenti parametri vengono utilizzati come ID principale (in questo ordine di priorità):

* Innertext
* Testo alternativo
* Title
* Src
* Azione

## Utilizzo di InnerText e utilizzo di Link Action (URL) {#section_70C3573E22274522A8CC035BF18EC468}

L’azione Collegamento è l’azione eseguita dalla pagina web quando si fa clic sul collegamento, solitamente l’URL visitato dopo aver fatto clic sul collegamento. Alcuni dei problemi che potresti riscontrare durante l’utilizzo di Azione collegamento sono:

* con due o più collegamenti distinti con lo stesso ID
* leggibilità del collegamento
* un collegamento con più azioni (a seconda del dispositivo in cui stai visualizzando il collegamento)

Di conseguenza, utilizziamo InnerText con questi vantaggi rispetto all’utilizzo dell’azione collegamento (URL):

* È una buona rappresentazione dell&#39;identità Link. La duplicazione degli ID primari è notevolmente ridotta in quanto non è comune avere più collegamenti con lo stesso testo.
* Garantisce la coerenza dell&#39;ID primario tra i dispositivi e i tipi di browser.
* Non è interessato dal riposizionamento di un collegamento sulla pagina.
* Migliora la leggibilità, consentendo agli utenti di iniziare ad analizzare i rapporti di tracciamento dei collegamenti all’esterno di Activity Map.

## Area di collegamento {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Questo nuovo attributo consente agli utenti di specificare una stringa rappresentativa dell&#39;area della pagina in cui si trova il collegamento.

Ad esempio, per un collegamento &quot;Contatti&quot; che si trova nella sezione menu della pagina web, l&#39;utente potrebbe voler passare un parametro di area &quot;Menu&quot;. Analogamente, per un collegamento &quot;Contact Us&quot; situato nel piè di pagina della pagina web, il parametro di regione può essere impostato su &quot;footer&quot;.

Il valore Regione collegamento non è impostato sul collegamento stesso, ma su un elemento HTML nella struttura DOM HTML che include tale area.
L’utilizzo dell’area geografica dei collegamenti offre i seguenti vantaggi:

* Aiuta a distinguere i collegamenti con lo stesso ID primario.
* La tendenza in un’area geografica è meno influenzata dall’aspetto dinamico della pagina web.
* Gli utenti possono visualizzare i collegamenti con le prestazioni migliori all’interno di una regione. Con Area come ancoraggio, possiamo mostrare sovrapposizioni di collegamenti attualmente non visibili sulla pagina (Ajax, Targeting).
* Un’area geografica può sostituire le pagine in quanto una determinata area geografica può essere utilizzata in molte pagine web. Aiuta a rispondere a domande come: &quot;La mia regione &quot;Offerta di prodotti&quot; funziona al meglio sulla pagina di destinazione delle donne o sulla pagina di destinazione degli uomini?
* Area è di per sé una dimensione rilevante per l’analisi di pagine web altamente dinamiche. Questo perché rimuove il rumore a causa della modifica continua dei collegamenti: un&#39;area &quot;Ultime notizie&quot; nella pagina di destinazione CNN può presentare molti collegamenti che cambiano. Ma la regione ci sarà sempre. Quindi potrebbe essere interessante tendere a livello regionale in molti giorni.

**Tracciamento area personalizzato**

Puoi personalizzare il parametro Regione per un collegamento (l’impostazione predefinita è ID collegamento): Un tag impostato su &quot;ID&quot; utilizzerà tutti gli elementi HTML con un parametro &quot;id&quot; come regione. Pertanto, l’impostazione del tag Region su &quot;id&quot; restituirà molto probabilmente molte aree distinte (quante sono presenti diversi &quot;ID&quot; sulla pagina). In alternativa, se desideri un’implementazione più personalizzata, puoi impostare il tag di regione su un valore più specifico, ad esempio &quot;region_id&quot;.

Di seguito è riportato un esempio di HTML utilizzando l’attributo di ID regione predefinito &quot;id&quot;.

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

Se lo desideri, puoi assegnare tag agli elementi con un identificatore di stringa arbitrario, in questo caso &quot;lpos&quot;, e quindi aggiungere attributi con il nome &quot;lpos&quot;.

```
<script language="JavaScript" type="text/javascript">
s.ActivityMap.regionIDAttribute = "lpos";
</script>
<div id="nav" lpos="navbar">
  <ul>
    <li>Menu Category A
      <ul>
        <li><a href="">Menu Item A 1</a>
        <li><a href="">Menu Item A 2</a>
      </ul>
    </li>
    <li>Menu Category B
      <ul>
        <li><a href="">Menu Item B 1</a>
        <li><a href="">Menu Item B 2</a>
      </ul>
    </li>
  </ul>
</div> 
  
<div id="content">
  <div id="breaking_news" lpos="breaking_news>
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

## Variabili di configurazione {#configuration-vars}

Tieni presente che queste variabili sono elencate solo a scopo di riferimento. Activity Map deve essere configurato correttamente ma puoi personalizzare l’implementazione utilizzando queste variabili.

<table id="table_7BC8DC3F35CF49288D94BA707F06B283"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Nome variable </th> 
   <th colname="col2" class="entry"> Esempio </th> 
   <th colname="col3" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> s.ActivityMap.regionIDAttribute </td> 
   <td colname="col2"> Predefinito al parametro "id". Puoi impostarlo su un altro parametro. </td> 
   <td colname="col3"> Stringa che identifica l'attributo del tag da utilizzare come ID di regione da un elemento precedente (parent, parent.parent, ...) di s.linkObject, cioè <b>l'elemento su cui è stato fatto clic</b>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> s.ActivityMap.link </td> 
   <td colname="col2"> 
    <code>//&nbsp;only&nbsp;ever&nbsp;use&nbsp;"title"&nbsp;attributes&nbsp;from&nbsp;A&nbsp;tags</code><br/>
    <code>function(clickedElement)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;linkId;</code><br/>
    <code>&nbsp;&nbsp;if&nbsp;(clickedElement&nbsp;&amp;&amp;&nbsp;clickedElement.tagName.toUpperCase()&nbsp;===&nbsp;'A')&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;linkId&nbsp;=&nbsp;clickedElement.getAttribute('title');</code><br/>
    <code>&nbsp;&nbsp;}</code><br/>
    <code>&nbsp;&nbsp;return&nbsp;linkId;</code><br/>
    <code>}</code> </td>
   <td colname="col3"> Funzione che riceve l'oggetto HTMLElement selezionato e deve restituire un valore stringa che rappresenta <b>il collegamento selezionato</b>. <br/>
      <br/>
     Se il valore restituito è false (null, undefined, empty string, 0), non viene tracciato alcun collegamento. </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.region </td> 
   <td colname="col2"> 
        <code>//&nbsp;only&nbsp;ever&nbsp;use&nbsp;lowercase&nbsp;version&nbsp;of&nbsp;tag&nbsp;name&nbsp;concatenated&nbsp;with&nbsp;first&nbsp;className&nbsp;as&nbsp;the&nbsp;region</code><br/>
    <code>function(clickedElement)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;regionId,&nbsp;className;</code><br/>
    <code>&nbsp;&nbsp;while&nbsp;(clickedElement&nbsp;&amp;&amp;&nbsp;(clickedElement&nbsp;=&nbsp;clickedElement.parentNode))&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;regionId&nbsp;=&nbsp;clickedElement.tagName;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;if&nbsp;(regionId)&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;return&nbsp;regionId.toLowerCase();</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;}</code><br/>
    <code>&nbsp;&nbsp;}</code><br/>
    <code>}</code> </td> 
   <td colname="col3"> Funzione che riceve l'elemento HTMLElement selezionato e deve restituire un valore stringa che rappresenta <b>l'area in cui è stato trovato il collegamento quando si fa clic su</b>. <br/>
      <br/>
     Se il valore restituito è false (null, undefined, empty string, 0), non viene tracciato alcun collegamento. </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.linkExclusions </td> 
   <td colname="col2"> 
     <code>//&nbsp;Exclude&nbsp;links&nbsp;tagged&nbsp;with&nbsp;a&nbsp;special&nbsp;linkExcluded&nbsp;CSS&nbsp;class</code><br/>
    <code>&lt;style&gt;</code><br/>
    <code>.linkExcluded&nbsp;{</code><br/>
    <code>&nbsp;&nbsp;display:&nbsp;block;</code><br/>
    <code>&nbsp;&nbsp;height:&nbsp;1px;</code><br/>
    <code>&nbsp;&nbsp;left:&nbsp;-9999px;</code><br/>
    <code>&nbsp;&nbsp;overflow:&nbsp;hidden;</code><br/>
    <code>&nbsp;&nbsp;position:&nbsp;absolute;</code><br/>
    <code>&nbsp;&nbsp;width:&nbsp;1px;</code><br/>
    <code>}</code><br/>
    <code>&lt;/style&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;link&nbsp;does&nbsp;not&nbsp;have&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.&nbsp;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link1&lt;/span&gt;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.linkExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;has&nbsp;hidden&nbsp;text&nbsp;matching&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;span&nbsp;class="linkExcluded"&gt;exclude-link2&lt;/span&gt;</code><br/>
    <code>&lt;/a&gt;</code><br/>
    <code>&lt;script&gt;</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid');</code><br/>
    <code>&nbsp;&nbsp;s.ActivityMap.linkExclusions&nbsp;=&nbsp;'exclude-link1,exclude-link2';</code><br/>
    <code>&lt;/script&gt;</code> </td> 
   <td colname="col3"> Stringa che riceve un elenco di stringhe separate da virgola da cercare nel testo del collegamento. Se trovato, il collegamento viene escluso dal tracciamento da parte di Activity Map. Se non è impostato, non viene effettuato alcun tentativo per interrompere il tracciamento del collegamento da parte di Activity Map. </td>
  </tr>
  <tr>
   <td colname="col1"> s.ActivityMap.regionExclusions </td> 
   <td colname="col2"> 
    <code>//&nbsp;Exclude&nbsp;regions&nbsp;on&nbsp;the&nbsp;page&nbsp;from&nbsp;its&nbsp;links&nbsp;being&nbsp;trackable&nbsp;by&nbsp;ActivityMap</code><br/>
    <code>&lt;div&nbsp;id="links-included"&gt;</code><br/>
    <code>&nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;Link&nbsp;is&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;but&nbsp;does&nbsp;not&nbsp;match&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;/a&gt;</code><br/>
    <code>&lt;/div&gt;</code><br/>
    <code>&lt;div&nbsp;id="links-excluded"&gt;&nbsp;</code><br/>
    <code>&nbsp;&nbsp;&lt;a&nbsp;href="next-page.html"&gt;</code><br/>
    <code>&nbsp;&nbsp;&nbsp;&nbsp;Link&nbsp;not&nbsp;tracked&nbsp;because&nbsp;s.ActivityMap.regionExclusions&nbsp;is&nbsp;set&nbsp;and&nbsp;this&nbsp;link&nbsp;matches&nbsp;the&nbsp;filter.</code><br/>
    <code>&nbsp;&nbsp;&lt;/a&gt;</code><br/>
    <code>&lt;/div&gt;</code><br/>
    <code>&lt;script&gt;</code><br/>
    <code>&nbsp;&nbsp;var&nbsp;s&nbsp;=&nbsp;s_gi('samplersid');</code><br/>
    <code>&nbsp;&nbsp;s.ActivityMap.regionExclusions&nbsp;=&nbsp;'links-excluded';</code><br/>
    <code>&lt;/script&gt;</code> </td> 
   <td colname="col3"> Stringa che riceve un elenco di stringhe separate da virgola da cercare nel testo della regione. Se trovato, il collegamento viene escluso dal tracciamento da parte di Activity Map. Se non è impostato, non viene effettuato alcun tentativo per interrompere il tracciamento del collegamento da parte di Activity Map. </td>
  </tr>
 </tbody>
</table>
