---
description: I download dei file e i collegamenti di uscita possono essere tracciati automaticamente in base ai parametri impostati in appmeasurement per il file javascript.
keywords: Implementazione di Analytics
seo-description: I download dei file e i collegamenti di uscita possono essere tracciati automaticamente in base ai parametri impostati in appmeasurement per il file javascript.
seo-title: Funzione s. tl () - Tracciamento collegamenti
solution: Analytics
subtopic: Tracciamento dei collegamenti
title: Funzione s. tl () - Tracciamento collegamenti
topic: Sviluppatore e implementazione
uuid: f 28 f 071 a -8820-4 f 74-89 cd-fd 2333 a 21 f 22
translation-type: tm+mt
source-git-commit: acaea784c977d7ff438f84faf8af5a3c605e3cf5

---


# Funzione s. tl () - Tracciamento collegamenti

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

## The s.tl() Function - Link Tracking {#concept_EA13689CB8EE4F308FC89A1293046D5E}

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

Se necessario, questi tipi di collegamenti possono essere tracciati manualmente utilizzando il codice di collegamento personalizzato come illustrato di seguito. Inoltre, il codice di collegamento personalizzato può essere usato per tenere traccia dei collegamenti personalizzati generici che possono essere utilizzati per diverse esigenze di tracciamento e reporting.

## s.tl() Parameter Reference {#section_DDF19EE3ACE24EFAB2D65CD4B0D7DBC4}

<!-- Meike, I converted a table within to table to this section. Please check against orginal file -Bob -->

**this**

Il primo argomento deve essere sempre impostato su questo (impostazione predefinita) o su true. L'argomento fa riferimento all'oggetto selezionato. se impostata su "this", fa riferimento alla proprietà HREF del collegamento.

Se si implementa il tracciamento dei collegamenti su un oggetto privo di proprietà HREF, è sempre necessario impostare questo argomento su "this."

Poiché facendo clic su un collegamento spesso si esce dalla pagina corrente, viene utilizzato un ritardo di 500 ms per garantire che venga inviata ad Adobe una richiesta di immagine prima che l'utente esca dalla pagina. Questo ritardo è necessario solo quando si esce dalla pagina, ma in genere è presente quando viene chiamata la funzione s. tl (). Se desiderate disattivare il ritardo, passate la parola chiave «true» come primo parametro quando chiamate la funzione s. tl ().

**linkType**

`s.tl(this,linkType,linkName, variableOverrides, doneAction)`

Linktype ha tre valori possibili, a seconda del tipo di collegamento che si desidera acquisire. Se il collegamento non è un collegamento di uscita o uscita, scegliete l'opzione Collegamenti personalizzati.

| Type (Tipo) | Valore linktype |
|--- |--- |
| Download dei file | ' d ' |
| Uscita dai collegamenti | ' è |
| Collegamenti personalizzati | ' o ' |

**linkName**

Può trattarsi di un qualsiasi valore personalizzato, fino a 100 caratteri. Questo determina il modo in cui il collegamento viene visualizzato nel report appropriato.

**Variableoverrides**

(Optional, pass null if not using) This lets you change variable values for this single call, It is similar to other [!DNL AppMeasurement] libraries.

**Useforcedlinktracking**

Questo flag viene utilizzato per disattivare il tracciamento forzato dei collegamenti per alcuni browser. Per impostazione predefinita, il tracciamento forzato dei collegamenti è abilitato per i browser firefox 20 + e webkit.

Valore predefinito = true

Esempio: `s.useForcedLinkTracking& = false`

**Forcedlinktrackingtimeout**

The maximum number of milliseconds to wait for tracking to finish before performing the doneAction that was passed into `s.tl`. Questo valore specifica il tempo massimo di attesa. Se la chiamata di collegamento di tracciamento viene completata prima del timeout, doneaction viene eseguita immediatamente. Se notate che le chiamate di collegamento non sono state completate, potrebbe essere necessario aumentare il timeout.

Valore predefinito = 250

Esempio: `s.forcedLinkTrackingTimeout&nbsp;=&nbsp;500`

**Doneaction**

Un parametro opzionale per specificare un'azione di navigazione da eseguire al completamento della chiamata di collegamento della traccia quando useforcedlinktracking è abilitato.

Sintassi:

`s.tl(linkObject,linkType,linkName,variableOverrides,doneAction)`

Doneaction: (Facoltativo) Specifica l'azione da intraprendere dopo che la chiamata di tracciamento del collegamento è stata inviata o è scaduta, in base al valore specificato da:

`s.forcedLinkTrackingTimeout`

The doneAction variable can be the string navigate, which causes the method to set `document.location` to the href attribute of linkObject . La variabile doneaction può anche essere una funzione che consente la personalizzazione avanzata.

If providing a value for doneAction in an anchor onClick event, you must return false after the `s.tl` call to prevent the default browser navigation.

Per rispecchiare il comportamento predefinito e seguire l'URL specificato dall'attributo href, fornire una stringa di navigazione come doneaction.

Facoltativamente, è possibile fornire la propria funzione per gestire l'evento di navigazione passando questa funzione come doneaction.

Esempi:

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a> <a href="#" onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

**Esempio**

The following example of an [!UICONTROL s.tl()] function call uses the default 500 ms delay to ensure data is collected before leaving the page.

```js
s.tl(this,'o','link name');
```

L'esempio seguente disattiva il ritardo di 500 ms, se l'utente non lascia la pagina o se l'oggetto su cui si fa clic non ha alcun HREF.

```js
s.tl(true,'o','link name');
```

Il ritardo di 500 ms è un ritardo massimo. Se l'immagine richiesta restituisce meno di 500 ms, il ritardo si interrompe immediatamente. Questo consente al visitatore di passare alla pagina successiva o all'azione successiva all'interno della pagina.

I seguenti esempi sono per gestire i collegamenti personalizzati sui browser webkit:

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a>
```

```js
<a href="#"  onclick="s.tl(this,'o','MyLink',null,  
function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

>[!NOTE]
>
>Gli usi del codice di collegamento personalizzato sono spesso molto specifici per le esigenze del sito Web e dei rapporti. Puoi contattare il tuo Adobe Consulente o l'Assistenza clienti prima di implementare un codice di collegamento personalizzato per comprendere le possibilità disponibili e il modo migliore per sfruttare questa funzionalità in base alle tue esigenze aziendali.

Il codice di base per tenere traccia di un collegamento utilizzando il codice di collegamento personalizzato è riportato nell'esempio seguente:

```js
<a href="index.html" onClick="s.tl(this,'o','Link Name')">My Page</a>
```

>[!NOTE]
>
>The [!UICONTROL s_gi] function must contain your report suite ID as a function parameter. Be sure to swap out [!DNL rsid] for your unique report suite ID.

>[!NOTE]
>
>Se il parametro nome collegamento non è definito, l'URL del collegamento (determinato dall'oggetto "this") viene usato come nome del collegamento.

[!DNL Analytics] possono essere definite come parte del codice di collegamento personalizzato.

## Automatic Tracking of Exit Links and File Downloads {#concept_DF078C5C1B004695B3B7C4536C99D4B2}

Il file javascript può essere configurato per monitorare automaticamente i download dei file e i collegamenti di uscita in base a parametri che definiscono i tipi di file e i collegamenti di uscita.

<!-- 

link_automatic.xml

 -->

I parametri che controllano il tracciamento automatico sono i seguenti:

```js
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

The parameters *`trackDownloadLinks`* and *`trackExternalLinks`* determine if automatic file download and exit link tracking are enabled. When enabled, any link with a file type matching one of the values in *`linkDownloadFileTypes`* is automatically tracked as a file download. Any link with a URL that does not contain one of the values in *`linkInternalFilters`* is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

## Example 1 {#section_504D163608E14B25A8B4CA9D615C6735}

The file types [!DNL jpg] and [!DNL aspx] are not included in *`linkDownloadFileTypes`* above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter *`linkLeaveQueryString`* modifies the logic used to determine exit links. When *`linkLeaveQueryString`*=false, exit links are determined using only the domain, path, and file portion of the link URL. When *`linkLeaveQueryString`*=true, the query string portion of the link URL is also used to determine an exit link.

## Example 2 {#section_25660B64E28248A0BC982B2AF5603C0E}

Con le seguenti impostazioni, l'esempio seguente verrà conteggiato come collegamento di uscita:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

## Example 3 {#section_2A78D05162D640169844A7D1E9799BAA}

Con le seguenti impostazioni, il collegamento seguente non viene conteggiato come collegamento di uscita:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

>[!NOTE]
>
>Un solo collegamento può essere tracciato solo come collegamento di file o di uscita, con il download di file prioritario. If a link is both an exit link and file download based on the parameters *`linkDownloadFileTypes`* and *`linkInternalFilters`*, it is tracked and reported as a file download and not an exit link. La tabella seguente riepiloga il tracciamento automatico dei download dei file e i collegamenti di uscita.

## Manual Link Tracking Using Custom Link Code {#concept_7113B5D037BE4622B6934554C6D18F96}

Il codice di collegamento personalizzato consente di scaricare i file, di uscire dai collegamenti e di tenere traccia dei collegamenti personalizzati in situazioni in cui il tracciamento automatico non è sufficiente o applicabile.

<!-- 

link_manual.xml

 -->

Custom link code is typically implemented by adding an [!UICONTROL onClick] event handler to a link or by adding code to an existing routine. Può essere implementato da qualsiasi gestore o funzione di evento javascript.

Link Tracking consists of calling the [!DNL AppMeasurement] for JavaScript function whenever the user performs actions that generate data you want to capture. This function, [!UICONTROL s.tl()], is either called directly in an event handler, such as [!UICONTROL onClick] or [!UICONTROL onChange], or from within a separate function. [!UICONTROL s.tl()] Questa funzione ha cinque argomenti. I primi tre sono obbligatori:

```js
s.tl(this,linkType,linkName, variableOverrides, doneAction)
```

## Custom Link Tracking on FireFox and WebKit Browsers {#section_F2B9A2A3CC1F4BB9A64456BC39FC50B9}

Javascript H .25 include un aggiornamento per garantire che il tracciamento dei collegamenti sia completato correttamente sui browser webkit (Safari e Chrome). Javascript H .26 include un aggiornamento per verificare che il tracciamento dei collegamenti sia completato correttamente su firefox 20 +.

After this update, download and exit links that are automatically tracked (determined by [!DNL s.trackDownloadLinks]and [!DNL s.trackExternalLinks]) are tracked successfully. Se tieni traccia dei collegamenti personalizzati utilizzando chiamate javascript manuali, devi modificare la modalità di esecuzione di tali chiamate. Ad esempio, i collegamenti di uscita e scaricamento vengono spesso tracciati utilizzando un codice simile a quanto segue:

```js
<a href="https://anothersite.com" onclick="s.tl(this,'e','AnotherSite',null)">
```

Internet Explorer esegue la chiamata di collegamento di tracciamento e apre la nuova pagina. Altri browser potrebbero annullare l'esecuzione della chiamata di collegamento di tracciamento quando si apre la nuova pagina. Ciò spesso impedisce il completamento delle chiamate di collegamento.

To work around this behavior, H.25 (released July 2012) includes an overloaded track link method ( [!DNL s.tl]) that forces browsers with this behavior to wait for the track link call to complete. Questo nuovo metodo esegue la chiamata di collegamento di tracciamento e gestisce l'evento di navigazione, anziché utilizzare l'azione del browser predefinita. This overloaded method requires an additional parameter, called [!UICONTROL doneAction], to specify the action to take when the link tracking call completes.

To use this new method, update calls to [!DNL s.tl] with an additional [!UICONTROL doneAction] parameter, similar to the following:

```js
<a href="https://anothersite.com"  
onclick="s.tl(this,'e','AnotherSite',null,'navigate');return false">
```

Passing navigate as the [!UICONTROL doneAction] mirrors the default browser behavior and opens the URL specified by the href attribute when the tracking call completes.

In JavaScript H.25.4 (released February 2013), the following scope limitations were added to links tracked when `useForcedLinkTracking` is enabled. Il tracciamento automatico dei collegamenti si applica solo a:

* `<A>` e `<AREA>` tag.
* The tag must have an `HREF` attribute.
* The `HREF` can't start with `#`, `about:`, or `javascript:`.
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

## Link Tracking Using an Image Request {#concept_FF31C8D1B3DF483D853BF0A9D637F02F}

I collegamenti possono essere tracciati senza chiamare la funzione s. tl () mediante la costruzione di una richiesta di immagine.

<!-- 

link_img.xml

 -->

Le richieste di immagine sono codificate in modo da aggiungere il parametro "pe" al parametro src dell'immagine, come segue:

```
pe=[type]
```

Where `[type]` is replaced with the type of link you want to track:

* lnk_ d = download
* lnk_ e = exit
* lnk_ o = personalizzato

Inoltre, è possibile specificare un URL collegamento passando l'URL nel parametro pev 1:

```
pev1=mylink.com
```

Per specificare un nome di collegamento, passate il nome nel parametro pev 2:

```
pev2=My%20Link
```

Ad esempio:

```
<img src="https://collectiondomain.112.2o7.net/b/ss/reportsuite/1/H.25.3--NS/0?pe=lnk_e&pev1=othersite.com&pev2=Offsite%20Link" width="1" height="1" border="0" />
```

## Setting Additional Variables for File Downloads, Exit Links, and Custom Links {#concept_8DD06387D5234A52A6E361572FAA2DF6}

Two parameters (  and ) control which [!DNL Analytics] variables are set for file downloads, exit links, and custom links.

<!-- 

link_variables.xml

 -->

Per impostazione predefinita sono impostate all'interno del file JS come segue:

```js
s.linkTrackVars="None"
```

```js
s.linkTrackEvents="None"
```

The *`linkTrackVars`* parameter should include each variable that you want to track with every file download, exit link, and custom link. The *`linkTrackEvents`* parameter should include each event you want to track with every file download, exit link, and custom link. Quando si verifica uno di questi tipi di collegamenti, viene tracciato il valore corrente di ciascuna variabile identificata.

Ad esempio, per monitorare prop 1, evar 1 e event 1 con ogni download file, collegamento exit e collegamento personalizzato, utilizzate le seguenti impostazioni nel file JS globale:

```js
s.linkTrackVars="prop1,eVar1,events"
```

```js
s.linkTrackEvents="event1"
```

>[!NOTE]
>
>The variable *`pageName`* cannot be set for a file download, exit link, or custom link, because each of the link types is not a page view and does not have an associated page name.

>[!NOTE]
>
>If *`linkTrackVars`* (or *`linkTrackEvents`*) is null (or an empty string), all [!DNL Analytics] variables (or events) that are defined for the current page are tracked. Questo rende più semplice l'uso inavvertitamente delle istanze di ciascuna variabile e dovrebbe essere evitata.

## Best practice {#section_DA3CA596792E4BD6B5FFE89BCE0E617D}

The settings for *`linkTrackVars`* and *`linkTrackEvents`* within the JS file affect every file download, exit link, and custom link. Le istanze di ogni variabile e evento possono essere ingrandite in situazioni in cui la variabile (o l'evento) si applica alla pagina corrente, ma non al download di file, al collegamento di uscita o al collegamento personalizzato.

To ensure that the proper variables are set with custom link code, Adobe recommends setting *`linkTrackVars`* and *`linkTrackEvents`* within the custom link code, as follows:

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

The values of *`linkTrackVars`* and *`linkTrackEvents`* override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

>[!NOTE]
>
>Nell'esempio precedente, il valore per prop 1 è impostato all'interno del codice di collegamento personalizzato stesso. Il valore di prop 2 deriva dal valore corrente della variabile impostato sulla pagina.

## Using Function Calls with Custom Link Code {#concept_DB662C93B3ED415DB72C80270502BE5D}

Due to the complex nature of custom link code, you can consolidate the code into a self-contained JavaScript function (defined on the page or in a linked JavaScript file) and make calls to the function within the [!UICONTROL onClick] handler.

<!-- 

link_functions.xml

 -->

For example, you could insert the following two functions in your `AppMeasurement.js` file, just below the `s_doPlugins()` function, and then use them throughout your site:

```js
/* Set Click Interaction values (with timeout - H25 code and higher*/ 

function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction',null,'navigate'); 
}
```

```js
/* Set Click Interaction values (without timeout - pre H25 code*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction'); 
}
```

>[!NOTE]
>
>Se necessario, è possibile trasmettere il tipo di collegamento e il nome del collegamento come parametri aggiuntivi per la funzione javascript.

Potete usare codice simile a quanto segue per chiamare queste funzioni:

```
<a href=”https://www.your-site.com/some_page.php” onclick=”trackClickInteraction('this.href');”>Link Text</a>
```

## Avoiding Duplicate Link Counts {#section_9C3F73DE758F4727943439DED110543C}

È possibile che il collegamento venga conteggiato due volte in situazioni in cui il collegamento viene normalmente acquisito dal tracciamento automatico dei file o da un tracciamento di uscita dei collegamenti.

Ad esempio, se monitori automaticamente i download PDF, il seguente codice restituisce un numero di download duplicato:

```js
function trackDownload(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 s.tl(obj,'d','PDF Document'); 
}
```

Per verificare che il conteggio doppio del collegamento non si verifichi, utilizzare la seguente funzione javascript modificata:

```js
<script language=JavaScript> 
function linkCode(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 var lt=obj.href!=null?s.lt(obj.href):""; 
 if (lt=="") { s.tl(obj,'d','PDF Document'); } 
}
```

Le ultime due righe del codice precedente modificano il comportamento del codice di collegamento personalizzato in modo che si verifichi solo il comportamento automatico di tracciamento, eliminando eventuali possibili conteggio.

## Popup Windows with useForcedLinkTracking {#concept_0AC4BA3A64B84CCB8D9A6021A022D1C3}

When `useForcedLinkTracking` is enabled, [!DNL AppMeasurement] overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. [!DNL AppMeasurement] esegue la chiamata di collegamento di tracciamento e gestisce l'evento di navigazione manualmente, anziché utilizzare l'azione del browser predefinita.

<!-- 

link_popups.xml

 -->

When tracking some links that open a popup window, the Chrome built-in popup blocker might prevent [!DNL AppMeasurement] from opening a popup window that would normally be allowed. To avoid this, add a `target="_blank"` attribute to calls that open a window:

```
<a href="./popup.html" target="_blank" onClick="<a href="./popup.html" onclick="s.tl(this,'o','popup',null,'navigate');javascript:window.open('./popup.html','popup','width=550,height=450'); 
return false;">
```

Questo consente di tenere traccia del collegamento e di caricarlo come previsto.

## Links from URL Shorteners {#concept_CD792362A8E04448B452BE9A18772024}

I collegamenti dai servizi di abbreviazione URL (ad esempio, bit. ly) in genere non vengono tracciati come visualizzazioni di pagina o come referenti. Questi servizi restituiscono reindirizzamenti 301/302 con l'URL completo del browser Web, che quindi invia una nuova richiesta separata all'URL completo. Il referente originale viene mantenuto in quanto l'abbreviazione non è più nel ciclo e non esiste un'indicazione sulla richiesta di utilizzare un servizio di reindirizzamento per ottenere l'URL.

<!-- 

link_shortener.xml

 -->

A causa della varietà di servizi disponibili, consigliamo di sottoporre a test i particolari scenari utilizzati sul sito per determinare il meccanismo di reindirizzamento utilizzato dal servizio.

## Link Tracking Variables in doPlugins {#concept_B5AC1D4372AA4A7D8C7871453A4F1215}

To help manage link tracking, these following variables are populated before the `doPlugins` function runs.

<!-- 

util_linkhandler.xml

 -->

Inside of `doPlugins`, you can use the following values to modify link tracking behavior. Ad esempio, puoi interrompere il tracciamento o aggiungere ulteriori variabili alle richieste di tracciamento.

<table id="table_55CCF4F2BF474FD3B703C926B896B392"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabile </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
   <th colname="col3" class="entry"> Impatto </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> linkType </td> 
   <td colname="col2"> <p>Contiene il tipo di collegamento determinato automaticamente, se presente. Può essere impostato su uno dei seguenti elementi: </p> 
    <ul id="ul_81ACB5D00D774E86AFD22C61AD4D0E2C"> 
     <li id="li_52B6F2B124024DEFB422D1E9E97254C0">d (download) </li> 
     <li id="li_E842C2E64F034181A364C639C30451FD">e (exit) </li> 
     <li id="li_3263F378CE65407E81B6C5C597CED1E8">o (personalizzato/altro) </li> 
    </ul> <p>This is the <code> pe </code> parameter in the image request. </p> </td> 
   <td colname="col3"> <p>If set with <code> linkURL </code> or <code> linkName </code>, a server call is sent as a download, custom, or exit link. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkName </td> 
   <td colname="col2"> <p>Nome che verrà visualizzato nel rapporto sul collegamento personalizzato, di download o di uscita. Troncati a 100 caratteri. Può essere impostato su qualsiasi stringa. </p> <p>This is the <code> pev2 </code> parameter in the image request. </p> </td> 
   <td colname="col3"> <p> If set with <code> linkType </code> , an image request will be sent as a download, custom or exit link </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkURL </td> 
   <td colname="col2"> <p>L'URL del collegamento, che funge da nome se un linkname non esiste. Può essere impostato su qualsiasi stringa URL. </p> <p>This is the <code> pev1 </code> parameter in the image request. </p> </td> 
   <td colname="col3"> <p>If set with <code> linkType </code>, an image request will be sent as a download, custom or exit link </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Linkobject </td> 
   <td colname="col2"> <p>L'oggetto selezionato come riferimento. Questa funzione è di sola lettura. </p> </td> 
   <td colname="col3"> <p>Nessun impatto diretto sulla misurazione. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Esempio**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

## Validating File Downloads, Exit Links, and Custom Links {#concept_0B43AD582D3E470899FCCB58E44D3D49}

Per convalidare completamente i collegamenti di download, uscita e personalizzati, Adobe consiglia di utilizzare un analizzatore di pacchetti per esaminare i collegamenti in tempo reale.

<!-- 

downloads_validate.xml

 -->

File downloads, exit links, and custom links are not page views, so the [!UICONTROL DigitalPulse Debugger] tool cannot be used to verify parameters and variable settings. You must use a [Packet Analyzer](../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258) to view track link data.
