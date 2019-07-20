---
description: Note sulla versione cumulative per il codice H legacy javascript H.
seo-description: Note sulla versione cumulative per il codice H legacy javascript H.
seo-title: Codice H javascript - Legacy
solution: Analytics
subtopic: Note sulla versione
title: Codice H javascript - Legacy
topic: Sviluppatore e implementazione
uuid: 4586 b 250-0 f 1 b -45 b 8-829 c -18 dc 1201956 f
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# JavaScript H Code - Legacy{#javascript-h-code-legacy}

Note sulla versione cumulative per il codice H legacy javascript H.

>[!NOTE]
>
>To find the current library version, use [DigitalPulse Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=debugger_about).

<!-- 

https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=omtrcache&title=AppMeasurement+Change+Log

 -->

## H.27.5 - Update {#section_DB9535C7EC4A4DDE9BA56B6C02BE8327}

Data di rilascio: **16 giugno 2016**

Inclusione di Visitor API 1.5.7.

## H.25.5 - Update {#section_B10151D7718F4568AE523BE1553FCCB7}

Release Date: **May 19, 2016**

Inclusione di Visitor API 1.5.5.

## H.27.5 - Update {#section_AD73ECD5CDAB4E158B509BA7B4B8CC1F}

Data di rilascio: **5 novembre 2015**

* Inclusione di Visitor API 1.5.3.

## H.27.5 - Update {#section_8A94D8A74A39486AAE248A22D661A261}

Release Date: **September 17, 2015**

* Inclusione di API visitatore 1.5.2.

## H.27.5 - Update {#section_62D1787F90FB4730B5F0C79EC1EF84B1}

Release Date: **August 20, 2015**

* Inclusione di API visitatore 1.5.1.

## H.27.5 - Update {#section_F58AF8B7FAE9470ABCBF2AAD9E7AF881}

Data di rilascio: **18 giugno 2015**

* Inclusione di Visitor API 1.5.

## H.27.5 - Update {#section_B3E310AFF909480BAD59A7F87D298348}

Release Date: **May 21, 2015**

* Inclusione di Visitor API 1.4

## H.27.5 - Update {#section_E7006FC903064376A85D3EC2AC1D2544}

Data di rilascio:**16 aprile 2015**

* Added Integrate module to s_code.js in legacy [!DNL AppMeasurement] for [!DNL JavaScript] H.X ZIP file. (AN-101001)

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

Release Date: **February 19th, 2015**

* Inclusione di Visitor API 1.3.5.
* Changed to not perform automatic referrer tracking after first tracking call, so the 2nd, 3rd, etc., tracking call (usually link tracking) will not double count the referrer when *`s.referrer`* was manually set before the first tracking call. (AN-92647)

## H.27.4 - Update {#section_ED38D59E83B4417180877F7C10BE4582}

Release Date: **January 15, 2015**

* Lo zip di distribuzione è stato aggiornato per includere API Visitor 1.3.4.

Release Date: **September 18, 2014**

* Aggiunta di una variabile `tagContainerMarker` che consente l'implementazione per specificare fino a 4 caratteri da aggiungere alla stringa della versione con un delimitatore di caratteri in forma di trattino. La variabile viene utilizzata per la gestione dinamica dei tag.

```js
  //  
<keyword>
  JavaScript 
</keyword> 
  s.tagContainerMarker = "D1.0"; 
    
  // Data Collection request 
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
```

## H.27.3 {#section_B38C61EE3BEA49CAA7A664395C85E4CF}

Release Date: **August 21, 2014**

* Modifiche interne per supportare le prossime funzionalità.

## H.27.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Data di rilascio: **19 giugno 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Supporto per nuove funzioni nel servizio ID visitatore 1.3.

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

Data di rilascio: **11 giugno 2014**

* Fixed an issue in the [!DNL Analytics] for [!DNL Target] integration that caused some hits to incorrectly be merged.

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

Release Date: **May 22, 2014**

* Support for the [Marketing Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).
* Support for the [Analytics for Target integration](https://marketing.adobe.com/resources/help/en_US/target/a4t/).

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

Data di rilascio: **17 ottobre 2013**

* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Data di rilascio:**18 luglio 2013**

* L'hash/frammento viene ora ignorato mediante il tracciamento automatico dei collegamenti. Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

Ora l'hash/frammento viene ignorato in modo che il collegamento venga tracciato solo quando il nome del file termina in un'estensione corrispondente.

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

Data di rilascio:**29 aprile 2013**

* the `useForcedLinkTracking` option that is described in [Manual Link Tracking Using Custom Link Code](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_manuallinktrackcustomlink) now applies to Firefox 20+ (previously this applied to WebKit browsers only).

* La generazione dell'ID oggetto immagine è ora univoca tra le istanze. Ciò impedisce la collisione quando più istanze si trovano sulla stessa pagina.

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

Data di rilascio:**19 aprile 2013**

* Fixed an issue in forced link tr [!DNL Windows]acking that caused a [!DNL JavaScript] error on some [!DNL Android] 2.2 Devices.

* Nel tracciamento automatico del video in Media Player, è stato risolto un problema nello scorrimento che causava il mancato tracciamento del tempo.

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

Release Date: **February 2013**

* Changed automatic exit link tracking to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

* Refined scope of click events affected by `useForcedLinkTracking`. Il tracciamento automatico dei collegamenti si applica solo a:

   * `<A>` e `<AREA>` tag

   * The tag must have an `HREF` attribute
   * The `HREF` can't start with `#`, `about:`, or `javascript:`

   * The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`)

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

Release Date: **January 2013**

* È stato aggiunto il supporto per l'invio di URL superiori a 255 byte per supportare l'espansione del campo URL pagina nei server di raccolta dati Adobe. Page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter. Questo consente di evitare che gli URL lunghi abbiano precedenza rispetto ad altri dati nel caso del troncamento del browser, ma consentano comunque l'acquisizione di URL lunghi.

* Fixed handling URL decoding for strings that are encoded with a mixed use of `escape` and `encodeURIComponent`.

* È stato risolto un problema nei browser webkit a causa del quale il tracciamento del collegamento non riusciva se la prima chiamata server sulla pagina era disabilitata.
* Aggiunto un nuovo metodo di identificazione del visitatore. See [Identifying Unique Visitors](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors).
* Added a new `abort` flag that can be set inside `doPlugins`. Setting this flag to true causes the [!DNL AppMeasurement] library to not continue with that tracking call. The abort flag is reset with every tracking call, so if a subsequent tracking call also needs to be aborted the flag will need to be set again inside `doPlugins`.

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

Questo consente di centralizzare la logica utilizzata per identificare l'attività che non desideri tracciare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci visualizzati.

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

Release Date: **October 2012**

* Added support for reporting an additional version number in the [!DNL JavaScript] version report. In precedenza era limitata a 2 caratteri (ad esempio, 1.8). È stato aggiunto il supporto per un numero di versione di 3 caratteri (ad esempio, 1.8.5).
* Fixed an issue with [!DNL Tag Manager] that prevented repeated values in Dependant Code blocks from being sent.

## H.25.1 {#section_680CE31CFA9945978F42612B684DB831}

Release Date: **September 2012**

* Codifica URL forzata per i seguenti caratteri:

```
  ~ 
  ! 
  * 
  ( 
  ) 
  '
```

This resolves issues with un-escaped characters being stored in the [!DNL ClickMap] `s_sq` cookie.

* Fixed an issue that might cause the video complete event to not be sent when using a custom `media.monitor` method that tracks the media close event:

```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

Release Date: **July 2012**

È stato effettuato un aggiornamento per garantire che il tracciamento dei collegamenti sia completato correttamente sui browser webkit (Safari e Chrome). After this update, download and exit links that are automatically tracked (determined by `s.trackDownloadLinks` and `s.trackExternalLinks`) are tracked successfully. If you are tracking custom links using manual [!DNL JavaScript] calls, you need to modify how these calls are made.

Ad esempio, i collegamenti di uscita e scaricamento vengono spesso tracciati utilizzando un codice simile a quanto segue:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

Firefox e Internet Explorer eseguono la chiamata di collegamento di tracciamento e aprono la nuova pagina. Tuttavia, i browser webkit potrebbero annullare l'esecuzione della chiamata di collegamento di tracciamento quando si apre la nuova pagina. Ciò spesso impedisce il completamento delle chiamate di collegamento di tracciamento quando si utilizzano browser webkit.

To workaround this behavior, H.25 includes an overloaded track link method ( `s.tl`) that forces WebKit browsers to wait for the track link call to complete. Questo nuovo metodo esegue la chiamata di collegamento di tracciamento e quindi gestisce l'evento di navigazione, anziché l'azione predefinita del browser. This overloaded method requires an additional parameter, called `doneAction`, to specify the action to take when the link tracking call completes.

To use this new method, update calls to `s.tl` with an additional `doneAction` parameter, similar to the following:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

Passing 'navigate' as the `doneAction` mirrors the default browser behavior and opens the URL specified by the `href` attribute when the tracking call completes.

La tabella seguente riepiloga le variabili di configurazione e gli aggiornamenti apportati a H .25 per supportare questa funzionalità.

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variabile </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Useforcedlinktracking </p> </td> 
   <td colname="col2"> <p>Questo flag viene utilizzato per disattivare il tracciamento forzato dei collegamenti per i browser webkit. Il tracciamento forzato dei collegamenti è abilitato per impostazione predefinita per i browser webkit e viene ignorato da altri browser. </p> <p> <b>Valore predefinito</b> </p> <p> <code> true </code> </p> <p> <b>Esempio</b> </p> 
    <code class="syntax javascript">s. useforcedlinktracking &amp; amp; nbsp; = &amp; amp; nbsp; false </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Forcedlinktrackingtimeout </p> </td> 
   <td colname="col2"> <p>The maximum number of milliseconds to wait for tracking to finish before performing the <code> doneAction </code> that was passed into <code> s.tl </code>. Questo valore specifica il tempo massimo di attesa. If the track link call completes before this timeout the <code> doneAction </code> is executed immediately. Se notate che le chiamate di collegamento non sono state completate, potresti dover aumentare il timeout. </p> <p> <b>Valore predefinito</b> </p> <p>250 </p> <p> <b>Esempio</b> </p> 
    <code class="syntax javascript">s. forcedlinktrackingtimeout &amp; amp; nbsp; = &amp; amp; nbsp; 500 </code>
  </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink ( <code> s.tl </code>) </td> 
   <td colname="col2"> <p>Traccia uscita, download e collegamenti personalizzati. Fornisce un parametro opzionale per specificare un'azione di navigazione da eseguire dopo il completamento della chiamata al collegamento di tracciamento su browser webkit. </p> <p> <b>Sintassi</b> </p> 
    <code class="syntax javascript">s. tl (linkobject, linktype, linkname, variableoverrides, doneaction) </code>
  <p> <b>Doneaction</b>: (Facoltativo) Specifica l'azione da intraprendere dopo che la chiamata alla traccia di collegamento è stata inviata o è scaduta (in base al valore specificato da <code> s. forcedlinktrackingtimeout </code>). The <code> doneAction </code> can be the string 'navigate', which causes the method to set <code> document.location </code> to the <code> href </code> attribute of <code> linkObject </code>. The <code> doneAction</code> can also be a function allowing for advanced customization. </p> <p>If providing a value for <code> onclick </code> in an anchor <code> false </code> event, you must return <code> s.tl </code> after the <code> href </code> call to prevent the default browser navigation. </p> <p> To mirror the default behavior and follow the URL specified by the <code> doneAction </code> attribute, provide a string of 'navigate' as the <code> doneAction </code>. </p> <p>Optionally, you can provide your own function to handle the navigation event by passing this function as the <code>$1</code>. </p> <p> <b>Esempi</b> </p> 
    <code class="syntax javascript">&lt; a &amp; amp; nbsp; href = "…" &amp; amp; nbsp; onclick = "s. tl (this,'o ','mylink ', null,'navigatè); return &amp; amp; nbsp; false " &gt; Click &amp; amp; nbsp; Qui &lt;/a &gt; </code><code class="syntax javascript">
 
 
 &lt; a &amp; amp; nbsp; href = " #" &amp; amp; nbsp; onclick = "s. tl (this,'o ','mylink ', null, function () {if ('continue? '))document.location=...});return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; 
    </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

Release Date: **April 2012**

Questo aggiornamento è consigliato per tutti i clienti.

* Made an enhancement to detect when a page is prerendered using Google Chrome Prerender ( [https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender)). Since Prerender loads and executes [!DNL JavaScript] and other code, this could result in page views being sent before a user clicks to visit your site. [!DNL JavaScript] La libreria ora attende che l'utente visita il sito prima di inviare chiamate server per queste pagine pre-passo.
* Added the `timestamp` variable to the [!DNL JavaScript] library for customers who want to customize timestamp data similar to other [!DNL AppMeasurement] libraries.

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

Release Date: **February 2012**

* Fixed an issue that caused extra data to be included in the image request for customers using Javascript `Object.prototype` overrides. All `Object.prototype` usage is now skipped when handling context data variables.
* Fixed an issue that caused the `pe` query parameter to be passed twice with the same value in some circumstances.
* Fix to [!DNL ClickMap] tracking in [!DNL JavaScript] to ignore clicks to the body tag, even when the tag has an `onClick` event handler.
* Added time stamp to variables used with light tracking calls ( `trackLight`).

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

Release Date: **January 2012**

* Aggiornamento del monitoraggio video con un nuovo metodo per tenere traccia delle visualizzazioni video complete.
* Fixed an issue that caused an "Attribute only valid on v:image" [!DNL JavaScript] error for `OnClick` events on VML elements in IE.
* Fixed a bug where context data variables were not included in link server calls, despite being referenced in `linkTrackVars`. Le variabili di dati di contesto vengono utilizzate con le regole di elaborazione.

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

Release Date: **November 2011**

* Tracciamento video aggiornato per combinare hit per segmenti e pietre miliari che si verificano contemporaneamente.

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

Release Date: **November 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

Release Date: **November 2011**

* Internal updates to support [!DNL Adobe Tag Manager].

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

Release Date: **October 2011**

* Fixed an issue that caused the `linkTrackVars=none` and `linkTrackEvents=none` settings to not apply when using automatic exit link tracking. Queste impostazioni vengono ora applicate per i collegamenti di uscita automatica, in modo che prop, evar ed eventi non vengano inviati con la richiesta di immagine collegamento.

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

Release Date: **September 2011**

* Sono stati rimossi gli attributi dei bordi dai tag immagine sui dispositivi mobili in conformità con gli standard WML (Wireless Markup Language). Questo risolve problemi di rendering su alcuni dispositivi mobili.

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

Release Date: **August 2011**

È stata corretta la precisione delle misure percentuali nel tracciamento video.

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

Release Date: **July 2011**

* È stato aggiunto supporto per [!DNL Adobe Tag Manager].

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

Release Date: **June 2011**

* Fixed an issue that caused [!DNL JavaScript] errors when accessing certain properties of Vector Markup Language (VML) shape elements.
* Le stringhe di riferimento che hanno oltre 255 caratteri ora sono troncate e abbreviano il percorso anziché la stringa di query. Queste problemi risolti erano parametri di stringa di query troncati e non raccolti.

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

Release Date: **May 2011**

* È stato risolto un problema che impediva l'invio della variabile di tracciamento video (pev 3).
* Fixed an issue that prevented the `s_gi` call from enabling code to be compatible with both G and H code. Quando passate un 1 come secondo parametro a questa chiamata, il codice ora è configurato per essere compatibile con entrambe le versioni.

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

Release Date: **April 2011**

* Supporto per contextdata che fornisce regole di elaborazione lato server (solo v 15).
* Supporto per chiamate server chiaro (solo v 15).
* Supporto per l'assegnazione di un valore diverso da 1 a un evento contatore nell'elenco degli eventi.
* Supporto per il nuovo metodo di tracciamento video utilizzando evar ed eventi di conversione (attualmente in versione beta).
* Rimosso il supporto per l'impostazione di Media. trackkhareplaying su false. Sarà sempre true.
* Aggiunto flag debugtracking per abilitare l'accesso alle richieste inviate alla console Firebug come le altre piattaforme.
* Accertatevi che " +" sia sempre codificato URL, indipendentemente dal browser.
