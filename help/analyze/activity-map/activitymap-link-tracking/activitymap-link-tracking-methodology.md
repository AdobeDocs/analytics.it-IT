---
description: Questa sezione è destinata agli amministratori di Adobe Analytics. Si concentra sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l’univocità e la coerenza dei collegamenti tra browser e dispositivi, e migliorano la gestione del riposizionamento dei collegamenti su una pagina.
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

Questa sezione è destinata agli amministratori di Adobe Analytics. Si concentra sui nuovi parametri di tracciamento dei collegamenti e su come garantiscono l’univocità e la coerenza dei collegamenti tra browser e dispositivi, e migliorano la gestione del riposizionamento dei collegamenti su una pagina.

>[!IMPORTANT]
>
>Qualsiasi collegamento in cui il testo (non il href) può contenere dati PII (personalmente identificabili) deve essere implementato esplicitamente utilizzando [s_objectID](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/page-variables.html?lang=it) oppure escludendo la raccolta di collegamenti ActivityMap con [s.ActivityMap.linkExclusions o s.ActivityMap.regionExclusions](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md#configuration-vars). Per ulteriori informazioni su come Activity Map potrebbe raccogliere dati PII, consulta [qui](/help/analyze/activity-map/lnk-tracking-overview.md).

L’Activity Map basa il tracciamento dei collegamenti su questi due ID:

* ID primario: è il parametro riconoscibile del collegamento.
* Area collegamento: è un parametro secondario che consente agli utenti di specificare una stringa rappresentativa dell’area del collegamento complessiva nella pagina o nell’area. Questo parametro può essere generato automaticamente se non viene fornito dall’utente.

## ID primario {#section_E8705CC1BDBC47FB8A4FE02293BACFE6}

Se il HTML ha un s_objectid, l&#39;ID primario viene impostato automaticamente su s_objectid. In caso contrario, i seguenti parametri vengono utilizzati come ID primario (in questo ordine di priorità):

* Innertext
* Alttext
* Titolo
* Src
* Azione

## Utilizzo di InnerText e di Azione collegamento (URL) {#section_70C3573E22274522A8CC035BF18EC468}

L’azione di collegamento è l’azione eseguita dalla pagina web quando si fa clic sul collegamento, in genere l’URL visitato dopo aver fatto clic sul collegamento. Alcuni dei problemi che potresti riscontrare durante l’utilizzo di Azione collegamento sono:

* avere due o più collegamenti distinti con lo stesso ID
* leggibilità del collegamento
* un collegamento con più azioni (a seconda del dispositivo in cui stai visualizzando il collegamento)

Di conseguenza, utilizziamo InnerText con i seguenti vantaggi rispetto all’utilizzo di Azione collegamento (URL):

* È una buona rappresentazione dell’identità del collegamento. La duplicazione dell’ID primario è notevolmente ridotta, in quanto non è comune avere più collegamenti con lo stesso testo.
* Garantisce la coerenza dell’ID primario tra i dispositivi e i tipi di browser.
* Non è influenzato dal riposizionamento di un collegamento sulla pagina.
* Migliora la leggibilità, consentendo agli utenti di iniziare ad analizzare i rapporti di tracciamento dei collegamenti al di fuori di Activity Map.

## Area del collegamento {#section_75BF9B9E3CE94B59ACC3D9AF63E04535}

Questo nuovo attributo consente agli utenti di specificare una stringa rappresentativa dell&#39;area della pagina in cui si trova il collegamento.

Ad esempio, per un collegamento &quot;Contattaci&quot; che si trova nella sezione menu della pagina web, l’utente potrebbe voler trasmettere un parametro di regione &quot;Menu&quot;. Analogamente, per un collegamento &quot;Contattaci&quot; che si trova nel piè di pagina della pagina web, il parametro region può essere impostato su &quot;footer&quot;.

Il valore dell&#39;area HTML del collegamento non è impostato sul collegamento stesso, ma su un elemento HTML su della struttura DOM che racchiude tale area.
L’utilizzo di Area collegamenti offre i seguenti vantaggi:

* Consente di distinguere i collegamenti con lo stesso ID primario.
* La tendenza su un’area è meno influenzata dall’aspetto dinamico della pagina web.
* Gli utenti possono visualizzare i collegamenti con le prestazioni migliori all’interno di un’area geografica. Con Area come ancoraggio, possiamo mostrare le sovrapposizioni di collegamenti attualmente non visibili sulla pagina (Ajax, Targeting).
* Un’area geografica può sostituire le pagine, in quanto una determinata area può essere utilizzata in più pagine web. Aiuta a rispondere a domande del tipo: &quot;La mia area &quot;Offerta prodotti&quot; ha le migliori prestazioni sulla pagina di destinazione Donne o Uomo?
* Di per sé, Region è una dimensione rilevante per analizzare pagine web altamente dinamiche. Questo perché rimuove il rumore dovuto alla continua modifica dei collegamenti: una regione &quot;Ultime notizie&quot; nella pagina di destinazione della CNN può avere molti collegamenti che cambiano. Ma la regione ci sarà sempre. Quindi potrebbe essere interessante osservare le tendenze a livello regionale per molti giorni.

**Tracciamento personalizzato area geografica**

Puoi personalizzare il parametro Region per un collegamento (l&#39;impostazione predefinita è link ID): un tag impostato su &quot;ID&quot; utilizzerà tutti gli elementi HTML con un parametro &quot;id&quot; come Region. Pertanto, l’impostazione del tag Regione su &quot;id&quot; molto probabilmente restituirà molte regioni distinte (tante quante sono le &quot;ID&quot; diverse nella pagina). In alternativa, se desideri un’implementazione più personalizzata, puoi impostare il tag region su un elemento più specifico, ad esempio &quot;region_id&quot;.

Di seguito, puoi visualizzare alcuni esempi di HTML utilizzando l’attributo dell’ID di regione predefinito, &quot;id&quot;.

```
<div id="content">
  <div id="breaking_news">
    <a href="breaking-news.html">...</a>
  </div>
  <div id="todays_top_headlines">
    <a href="breaking-news.html">...</a>
  </div>
```

Se lo desideri, puoi assegnare un tag agli elementi con un identificatore di stringa arbitrario, in questo caso &quot;lpos&quot;, e quindi aggiungere attributi con il nome &quot;lpos&quot;.

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

Queste variabili sono elencate solo a scopo di riferimento. L’Activity Map deve essere configurato correttamente, ma puoi personalizzare la tua implementazione utilizzando queste variabili.

### `s.ActivityMap.regionIDAttribute`

Stringa che identifica l’attributo tag da utilizzare come ID di regione da un elemento predecessore (parent, parent.parent, ...) di `s.linkObject`, ovvero **elemento su cui è stato fatto clic**.

**Esempio**

Impostazione predefinita del parametro &quot;id&quot;. Puoi impostare questo su un altro parametro.

### `s.ActivityMap.link`

Funzione che riceve il clic `HTMLElement` e deve restituire un valore stringa che rappresenta il collegamento su cui è stato fatto clic. Se il valore restituito è false (null, indefinito, stringa vuota, 0), non viene tracciato alcun collegamento.

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

Funzione che riceve l&#39;elemento HTML su cui è stato fatto clic e deve restituire un valore stringa che rappresenta **l’area in cui è stato trovato il collegamento quando è stato fatto clic su.** Se il valore restituito è false (null, indefinito, stringa vuota, 0), non viene tracciato alcun collegamento.

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

Stringa che riceve un elenco separato da virgole di stringhe da cercare nel testo del collegamento. Se trovato, il collegamento non può essere tracciato dall’Activity Map. Se non è impostato, non viene effettuato alcun tentativo di interrompere il tracciamento del collegamento da parte dell’Activity Map.

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

Stringa che riceve un elenco separato da virgole di stringhe da cercare nel testo dell&#39;area. Se trovato, il collegamento non può essere tracciato dall’Activity Map. Se non è impostato, non viene effettuato alcun tentativo di interrompere il tracciamento del collegamento da parte dell’Activity Map.

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
