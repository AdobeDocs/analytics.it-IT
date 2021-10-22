---
description: Questa sezione è destinata agli amministratori di Adobe Analytics. Si concentra sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l’univocità e la coerenza dei collegamenti tra browser e dispositivi, e come migliorano la gestione del riposizionamento dei collegamenti su una pagina.
title: Metodologia di tracciamento dei collegamenti
uuid: 67864bf9-33cd-46fa-89a8-4d83d3b81152
feature: Activity Map
role: User, Admin
exl-id: 6aef3a0f-d0dd-4c84-ad44-07b286edbe18
source-git-commit: a6b38c6e7a34c876524ebe15514ac205898549d0
workflow-type: tm+mt
source-wordcount: '992'
ht-degree: 2%

---

# Metodologia di tracciamento dei collegamenti

Questa sezione è destinata agli amministratori di Adobe Analytics. Si concentra sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l’univocità e la coerenza dei collegamenti tra browser e dispositivi, e come migliorano la gestione del riposizionamento dei collegamenti su una pagina.

>[!IMPORTANT]
>
>Qualsiasi collegamento in cui il testo (non il href) può contenere PII (personalmente identificabili) deve essere implementato esplicitamente utilizzando [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=it) o escludendo la raccolta di collegamenti ActivityMap con [s.ActivityMap.linkExclusions o s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Per ulteriori informazioni sulla raccolta dei dati PII da parte di Activity Map, consulta [qui](/help/analyze/activity-map/lnk-tracking-overview.md).

Activity Map basa il tracciamento dei collegamenti su questi due ID:

* ID principale: questo è il parametro riconoscibile del collegamento.
* Regione collegamento: si tratta di un parametro secondario che consente agli utenti di specificare una stringa rappresentativa dell’area di collegamento complessiva nella pagina o nell’area geografica. Questo parametro può essere generato automaticamente se non viene fornito dall’utente.

## ID principale {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Se HTML ha un s_object, l&#39;ID principale viene impostato automaticamente su s_object. In caso contrario, i seguenti parametri vengono utilizzati come ID principale (in questo ordine di priorità):

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

Puoi personalizzare il parametro Regione per un collegamento (l’impostazione predefinita è ID collegamento): Un tag impostato su &quot;ID&quot; utilizza tutti gli elementi di HTML con un parametro &quot;id&quot; come area geografica. Pertanto, l’impostazione del tag Region su &quot;id&quot; restituirà molto probabilmente molte aree distinte (quante sono presenti diversi &quot;ID&quot; sulla pagina). In alternativa, se desideri un’implementazione più personalizzata, puoi impostare il tag di regione su un valore più specifico, ad esempio &quot;region_id&quot;.

Di seguito puoi visualizzare alcuni HTML di esempio utilizzando l’attributo ID di regione predefinito &quot;id&quot;.

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

### `s.ActivityMap.regionIDAttribute`

Stringa che identifica l&#39;attributo del tag da utilizzare come ID di regione da un elemento precedente (parent, parent.parent, ...) di `s.linkObject`, vale a dire, **l’elemento su cui è stato fatto clic**.

**Esempio**

Predefinito al parametro &quot;id&quot;. Puoi impostarlo su un altro parametro.

### `s.ActivityMap.link`

Funzione che riceve il clic `HTMLElement` e deve restituire un valore stringa che rappresenta il collegamento su cui hai fatto clic. Se il valore restituito è false (null, undefined, empty string, 0), non viene tracciato alcun collegamento.

**Esempio**

```
// only ever use "title" attributes from A tags
function(clickedElement) {
  var linkId;
  if (clickedElement && clickedElement.tagName.toUpperCase() === 'A') {
    linkId = clickedElement.getAttribute('title');
  }
  return linkId;
}
```

### `s.ActivityMap.region`

Funzione che riceve l&#39;oggetto HTMLElement selezionato e deve restituire un valore stringa che rappresenta **l’area in cui è stato trovato il collegamento quando si è fatto clic su di esso.** Se il valore restituito è false (null, undefined, empty string, 0), non viene tracciato alcun collegamento.

**Esempio**

```
// only ever use lowercase version of tag name concatenated with first className as the region
function(clickedElement) {
  var regionId, className;
  while (clickedElement && (clickedElement = clickedElement.parentNode)) {
    regionId = clickedElement.tagName;
    if (regionId) {
      return regionId.toLowerCase();
    }
  }
}
```

### `s.ActivityMap.linkExclusions`

Stringa che riceve un elenco di stringhe separate da virgola da cercare nel testo del collegamento. Se trovato, il collegamento viene escluso dal tracciamento da parte di Activity Map. Se non è impostato, non viene effettuato alcun tentativo per interrompere il tracciamento del collegamento da parte di Activity Map.

**Esempio**

```
// Exclude links tagged with a special linkExcluded CSS class
<style>
.linkExcluded {
  display: block;
  height: 1px;
  left: -9999px;
  overflow: hidden;
  position: absolute;
  width: 1px;
}
</style>
<a href="next-page.html">
  Link is tracked because link does not have hidden text matching the filter. 
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link1</span>
</a>
<a href="next-page.html">
  Link not tracked because s.ActivityMap.linkExclusions is set and this link has hidden text matching the filter.
  <span class="linkExcluded">exclude-link2</span>
</a>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.linkExclusions = 'exclude-link1,exclude-link2';
</script>
```

### `s.ActivityMap.regionExclusions`

Stringa che riceve un elenco di stringhe separate da virgola da cercare nel testo della regione. Se trovato, il collegamento viene escluso dal tracciamento da parte di Activity Map. Se non è impostato, non viene effettuato alcun tentativo per interrompere il tracciamento del collegamento da parte di Activity Map.

**Esempio**

```
// Exclude regions on the page from its links being trackable by ActivityMap
<div id="links-included">
  <a href="next-page.html">
    Link is tracked because s.ActivityMap.regionExclusions is set but does not match the filter.
  </a>
</div>
<div id="links-excluded"> 
  <a href="next-page.html">
    Link not tracked because s.ActivityMap.regionExclusions is set and this link matches the filter.
  </a>
</div>
<script>
  var s = s_gi('samplersid');
  s.ActivityMap.regionExclusions = 'links-excluded';
</script>
```
