---
description: Note cumulative sulla versione per il codice JavaScript H legacy.
seo-description: Note cumulative sulla versione per il codice JavaScript H legacy.
seo-title: 'Codice H JavaScript: legacy'
solution: Analytics
subtopic: Note sulla versione
title: 'Codice H JavaScript: legacy'
topic: Sviluppatore e implementazione
uuid: 4586b250-0f1b-45b8-829c-18dc1201956f
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Codice H JavaScript: legacy{#javascript-h-code-legacy}

Note cumulative sulla versione per il codice JavaScript H legacy.

>[!NOTE]
>
>Per trovare la versione corrente della libreria, utilizzare [DigitalPulse Debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=debugger_about).

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

* È stato aggiunto il modulo Integrate a s_code.js nella versione precedente [!DNL AppMeasurement] per il file ZIP [!DNL JavaScript] H.X. (AN-101001)

## H.27.5 {#section_22DCF43169614B28BC17F46426C5D5B6}

Data di rilascio: 19 **febbraio 2015**

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

* È stata corretta la gestione dei flag di attesa e di completamento per i campi API del visitatore, come l’ID [!DNL Analytics] visitatore legacy, che causava degli errori.
* Supporto per le nuove funzioni nel servizio ID visitatore 1.3.

## H.27.1 {#section_CC2556C734EE4BAAB71D6A93095DB38F}

Data di rilascio: **11 giugno 2014**

* È stato risolto un problema nella [!DNL Analytics] per l’ [!DNL Target] integrazione che causava l’erronea unione di alcuni hit.

## H.27 {#section_023B6267C0DB424F99A23EBB732B8C69}

Release Date: **May 22, 2014**

* Supporto per il servizio [ID visitatori di](https://marketing.adobe.com/resources/help/en_US/mcvid/)Experience Cloud.
* Supporto per l'integrazione [di](https://marketing.adobe.com/resources/help/en_US/target/a4t/)Analytics per Target.

## H.26.2 {#section_DE82C8BC7645400785E5B136565616F1}

Data di rilascio: **17 ottobre 2013**

* Aggiunto `alt=""` a tutti gli oggetti Immagine per conformarsi alla Legge sulle comunicazioni e i video accessibili.

## H.26.1 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Data di rilascio:**18 luglio 2013**

* L'hash/frammento viene ora ignorato dal tracciamento automatico dei collegamenti. In precedenza veniva tracciato automaticamente il seguente URL, dal momento che l’intero URL `href` terminava con `.pdf`:

```js
  <a href="index.htm#anchor.pdf">Test Link</a>
```

Ora l'hash o il frammento viene ignorato e il collegamento viene tracciato solo quando il nome del file termina con un'estensione corrispondente.

## H.26 {#section_E25814ACC21E41718EE1741A85AE567B}

Data di rilascio:**29 aprile 2013**

* l' `useForcedLinkTracking` opzione descritta in Tracciamento [manuale dei collegamenti con codice](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_manuallinktrackcustomlink) di collegamento personalizzato ora si applica a Firefox 20+ (precedentemente applicata solo ai browser WebKit).

* La generazione dell'ID dell'oggetto immagine è ora univoca tra le istanze. In questo modo si evitano conflitti quando più istanze si trovano sulla stessa pagina.

## H.25.5 {#section_A528D1D5E84146F9A56680E4427B2750}

Data di rilascio:**19 aprile 2013**

* È stato risolto un problema relativo al [!DNL Windows]rilevamento forzato dei collegamenti che causava un [!DNL JavaScript] errore su alcuni dispositivi [!DNL Android] 2.2.

* Nel video con tracciamento automatico su Media Player, è stato risolto un problema di scorrimento che impediva il corretto tracciamento del tempo di riproduzione.

## H.25.4 {#section_009AF895C8DD47CABC9A3776D27E8300}

Release Date: **February 2013**

* È stato modificato il tracciamento automatico dei collegamenti di uscita per ignorare sempre i collegamenti con `HREF` gli attributi che iniziano con `#`, `about:`o `javascript:`.

* Ambito perfezionato degli eventi click interessati da `useForcedLinkTracking`. Il tracciamento automatico dei collegamenti forzati si applica solo a:

   * `<A>` e `<AREA>` tag

   * Il tag deve avere un `HREF` attributo
   * Non `HREF` puoi iniziare con `#`, `about:`, o `javascript:`

   * L' `TARGET` attributo non deve essere impostato, o `TARGET` deve fare riferimento alla finestra corrente ( `_self`, `_top`, o al valore di `window.name`)

## H.25.3 {#section_FA6A6F9F5D64455DA5A54C007081341A}

Release Date: **January 2013**

* È stato aggiunto il supporto per l’invio di URL superiori a 255 byte per supportare l’espansione del campo URL pagina nei server di raccolta dati Adobe. Gli URL di pagina di lunghezza superiore a 255 byte vengono suddivisi, con i primi 255 byte visualizzati nel `g=` parametro, con i rimanenti byte che vengono visualizzati successivamente nella stringa di query nel parametro di `-g=` query. In questo modo si evita che gli URL lunghi abbiano la precedenza rispetto ad altri dati nel caso di troncamento del browser, ma si possono comunque acquisire URL lunghi.

* È stata corretta la decodifica URL per le stringhe codificate con un uso misto di `escape` e `encodeURIComponent`.

* È stato risolto un problema nei browser WebKit che causava un errore di tracciamento dei collegamenti se la prima chiamata server sulla pagina si arrestava.
* È stato aggiunto un nuovo metodo di identificazione fallback del visitatore. Consulta [Identificazione di visitatori](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=c_identifying_unique_visitors)univoci.
* È stato aggiunto un nuovo `abort` flag che può essere impostato all'interno `doPlugins`. Impostando questo flag su true, la [!DNL AppMeasurement] libreria non continua con quella chiamata di tracciamento. Il flag abort viene reimpostato con ogni chiamata di tracciamento, quindi se è necessario interrompere anche una chiamata di tracciamento successiva, il flag dovrà essere nuovamente inserito all’interno `doPlugins`.

```js
  s.doPlugins = function(s) { 
       s.campaign = s.getQueryParam("cid"); 
       if ((!s.campaign) && (!s.events)) { 
            s.abort = true; 
       } 
  };
```

Questo consente di centralizzare la logica utilizzata per identificare l'attività che non si desidera tracciare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci visualizzati.

## H25.2 {#section_647D7638D0C04019B8C9986CD124914E}

Release Date: **October 2012**

* È stato aggiunto il supporto per la segnalazione di un numero di versione aggiuntivo nel rapporto sulla [!DNL JavaScript] versione. Precedentemente questa versione era limitata a 2 caratteri (ad esempio 1.8). È stato aggiunto il supporto per un numero di versione di 3 caratteri (ad esempio, 1.8.5).
* È stato risolto un problema [!DNL Tag Manager] che impediva l'invio di valori ripetuti nei blocchi di codice dipendenti.

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

In questo modo vengono risolti i problemi di memorizzazione dei caratteri non escape nel [!DNL ClickMap] `s_sq` cookie.

* È stato risolto un problema che poteva impedire l'invio dell'evento di completamento del video quando si utilizzava un `media.monitor` metodo personalizzato per tenere traccia dell'evento di chiusura del supporto:

```
  If(media.event==”CLOSE”) { 
  … 
  } 
  
```

## H.25 {#section_BE76FEDFE03B44658808B0BDF779DE97}

Release Date: **July 2012**

È stato effettuato un aggiornamento per garantire che il tracciamento dei collegamenti venga completato correttamente sui browser WebKit (Safari e Chrome). Dopo questo aggiornamento, i collegamenti di download e di uscita tracciati automaticamente (determinati da `s.trackDownloadLinks` e `s.trackExternalLinks`) vengono tracciati correttamente. Se monitori collegamenti personalizzati utilizzando [!DNL JavaScript] chiamate manuali, devi modificare la modalità di esecuzione di tali chiamate.

Ad esempio, i collegamenti di uscita e di download vengono spesso tracciati utilizzando un codice simile al seguente:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null)">
```

FireFox e Internet Explorer eseguono la chiamata di tracciamento collegamento e aprono la nuova pagina. Tuttavia, i browser WebKit potrebbero annullare l'esecuzione della chiamata di tracciamento collegamento quando si apre la nuova pagina. Ciò spesso impedisce il completamento delle chiamate di tracciamento dei collegamenti quando si utilizzano browser WebKit.

Per ovviare a questo comportamento, H.25 include un metodo di collegamento traccia sovraccarico ( `s.tl`) che forza i browser WebKit ad attendere il completamento della chiamata di tracciamento dei collegamenti. Questo nuovo metodo esegue la chiamata di tracciamento dei collegamenti e quindi gestisce l’evento di navigazione, invece di utilizzare l’azione browser predefinita. Questo metodo sovraccarico richiede un parametro aggiuntivo, denominato `doneAction`, per specificare l’azione da intraprendere al termine della chiamata di tracciamento del collegamento.

Per utilizzare questo nuovo metodo, aggiorna le chiamate a `s.tl` con un `doneAction` parametro aggiuntivo, simile al seguente:

```js
  <a href="http://anothersite.com" onclick="s.tl(this,'o','link name',null 
  <codeph outputclass="syntax"> ,'navigate');return false"> 
  </codeph outputclass="syntax">
```

Passando 'navigate', il `doneAction` comportamento predefinito del browser viene rispecchiato e si apre l'URL specificato dall' `href` attributo al termine della chiamata di tracciamento.

La tabella seguente riassume le variabili di configurazione e gli aggiornamenti apportati a H.25 per supportare questa funzionalità.

<table id="table_E67157D710874146B26EFB7D84762542"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Variabile </p> </th> 
   <th colname="col2" class="entry"> <p>Descrizione </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>useForcedLinkTracking </p> </td> 
   <td colname="col2"> <p>Questo flag viene utilizzato per disabilitare il tracciamento forzato dei collegamenti per i browser WebKit. Il tracciamento forzato dei collegamenti è abilitato per impostazione predefinita per i browser WebKit e viene ignorato dagli altri browser. </p> <p> <b>Valore predefinito</b> </p> <p> <code> true </code> </p> <p> <b>Esempio</b> </p> 
    <code class="syntax javascript">
      s.useForcedLinkTracking&amp;nbsp;=&amp;nbsp;false </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>forceLinkTrackingTimeout </p> </td> 
   <td colname="col2"> <p>Il numero massimo di millisecondi di attesa del completamento del tracciamento prima di eseguire <code> doneAction </code> che è stato passato in <code> s.tl </code>. Questo valore specifica il tempo massimo di attesa. Se la chiamata di tracciamento dei collegamenti viene completata prima di tale timeout, l’ <code> azione completata </code> viene eseguita immediatamente. Se noti che le chiamate di tracciamento dei collegamenti non stanno completando, potresti dover aumentare questo timeout. </p> <p> <b>Valore predefinito</b> </p> <p>250 </p> <p> <b>Esempio</b> </p> 
    <code class="syntax javascript">
      s.forzatoLinkTrackingTimeout&amp;nbsp;=&amp;nbsp;500 </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> trackLink ( <code> s.tl </code>) </td> 
   <td colname="col2"> <p>Tiene traccia dei collegamenti di uscita, download e personalizzati. Fornisce un parametro opzionale per specificare un'azione di navigazione da eseguire al termine della chiamata di tracciamento dei collegamenti sui browser WebKit. </p> <p> <b>Sintassi</b> </p> 
    <code class="syntax javascript">
      s.tl(linkObject,linkType,linkName,variableOverrides,doneAction) </code> <p> <b>doneAction</b>: (facoltativo) Specifica l’azione da intraprendere dopo che la chiamata di tracciamento del collegamento è stata inviata o è scaduta (in base al valore specificato da <code> s.forzatoLinkTrackingTimeout </code>). L' <code> azione eseguita </code> può essere la stringa 'navigate', che causa l'impostazione del metodo <code> document.location </code> all' <code> attributo href </code> del <code> linkObject </code>. La funzione <code> doneAction</code> può anche consentire una personalizzazione avanzata. </p> <p>Se si fornisce un valore per <code> onclick </code> in un <code> evento di ancoraggio false </code> , è necessario restituire <code> s.tl </code> dopo la <code> chiamata href </code> per impedire la navigazione predefinita del browser. </p> <p> Per rispecchiare il comportamento predefinito e seguire l'URL specificato dall'attributo <code> doneAction </code> , immettete una stringa "navigate" come <code> action </code>. </p> <p>Facoltativamente, è possibile fornire la propria funzione per gestire l'evento di navigazione passando questa funzione come <code>$1</code>. </p> <p> <b>Esempi</b> </p> 
    <code class="syntax javascript">
      &lt;a&amp;nbsp;href="..."&amp;nbsp;onclick="s.tl(this,'o','MyLink',null,'navigate');return&amp;nbsp;false"&gt;Click&amp;nbsp;here&lt;/a&gt; </code> <code class="syntax javascript">&lt;a&amp;nbsp;href="#"&amp;nbsp;onbsp="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return&amp;nbsp;false"&gt;Click&amp;nbsp;Here&lt;/a&gt; </code> </td> 
  </tr> 
 </tbody> 
</table>

## H.24.4 {#section_1989179F10A34E88968CA5A5290CF17C}

Release Date: **April 2012**

Questo aggiornamento è consigliato per tutti i clienti.

* È stato apportato un miglioramento per rilevare quando viene eseguito il rendering di una pagina tramite Google Chrome Pre-ender ( [https://developers.google.com/chrome/whitepapers/prerender](https://developers.google.com/chrome/whitepapers/prerender)). Dal momento che prerender carica ed esegue [!DNL JavaScript] e altro codice, ciò potrebbe causare l'invio delle visualizzazioni di pagina prima che un utente faccia clic per visitare il sito. La [!DNL JavaScript] libreria attende che l'utente visiti il sito prima di inviare chiamate server per queste pagine prerendering.
* Aggiunta la `timestamp` variabile alla [!DNL JavaScript] libreria per i clienti che desiderano personalizzare i dati delle marche temporali in modo simile alle altre [!DNL AppMeasurement] librerie.

```js
  s.timestamp=Math.round((new Date()).getTime()/1000); 
  s.timestamp="2012-04-20T12:49:31-0700";
```

## H.24.3 {#section_F3D471B201F54C089320D3CE6D441DC0}

Release Date: **February 2012**

* È stato risolto un problema che causava l’inclusione di dati aggiuntivi nella richiesta di immagini per i clienti che utilizzavano `Object.prototype` le sostituzioni JavaScript. Tutto `Object.prototype` l'utilizzo ora viene ignorato quando si gestiscono le variabili di dati di contesto.
* È stato risolto un problema che causava il doppio invio del parametro di `pe` query con lo stesso valore in alcune circostanze.
* Correzione del [!DNL ClickMap] tracciamento in [!DNL JavaScript] modo da ignorare i clic sul tag body, anche quando il tag include un gestore `onClick` eventi.
* Aggiunta di marca temporale alle variabili utilizzate con le chiamate di tracciamento della luce ( `trackLight`).

## H.24.2 {#section_91CF07C2BC9B4C8BA0235DFDFB95A4D9}

Release Date: **January 2012**

* È stato aggiornato il tracciamento video con un nuovo metodo per tenere traccia delle visualizzazioni video complete.
* È stato risolto un problema che causava un errore di tipo "Attribute only valid on v:image" (Attributo valido solo in v:image) [!DNL JavaScript] per `OnClick` gli eventi su elementi VML in IE.
* È stato corretto un bug a causa del quale le variabili dei dati di contesto non venivano incluse nelle chiamate del server dei collegamenti, nonostante fosse presente un riferimento in `linkTrackVars`. Le variabili di dati di contesto vengono utilizzate con le regole di elaborazione.

## H.24.1 {#section_967356D219FE4E9CAA110D03EDF4C8B1}

Release Date: **November 2011**

* È stato aggiornato il tracciamento video per combinare gli hit per segmenti e pietre miliari che si verificano contemporaneamente.

## H.24 {#section_78FF9B245643406BB7E9967E784A90AE}

Release Date: **November 2011**

* Aggiornamenti interni per il supporto [!DNL Adobe Tag Manager].

## H.23.9 {#section_3834625A639A47428683E08A472359C7}

Release Date: **November 2011**

* Aggiornamenti interni per il supporto [!DNL Adobe Tag Manager].

## H.23.8 {#section_FF3CEEAB6C6744D6B5EE314A0B5841CA}

Release Date: **October 2011**

* È stato risolto un problema che impediva l'applicazione delle impostazioni `linkTrackVars=none` e `linkTrackEvents=none` le impostazioni quando si utilizzava il tracciamento automatico dei collegamenti di uscita. Queste impostazioni si applicano ora ai collegamenti di uscita automatici in modo che proprietà, eVar ed eventi non vengano inviati con la richiesta di immagine del collegamento di uscita.

## H.23.7 {#section_D9D0CF343EBF49D9844C6BDA0C3C7A2E}

Release Date: **September 2011**

* Sono stati rimossi gli attributi del bordo dai tag immagine sui dispositivi mobili per conformarsi agli standard WML (Wireless Markup Language). Questo risolve i problemi di rendering su alcuni dispositivi mobili.

## H.23.6 {#section_461A208BE1B64EDDA87A8D7C4FD5456C}

Release Date: **August 2011**

Corretta la precisione delle percentuali di misurazioni nel tracciamento video.

## H.23.5 {#section_FCE48EE33C9A42F08386FA30037BF4E0}

Release Date: **July 2011**

* È stato aggiunto supporto per [!DNL Adobe Tag Manager].

## H.23.4 {#section_E9152B4437C24107A68D264F70361930}

Release Date: **June 2011**

* È stato risolto un problema che causava [!DNL JavaScript] errori durante l'accesso a determinate proprietà degli elementi forma VML (Vector Markup Language).
* Le stringhe di riferimento con più di 255 caratteri ora vengono troncate abbreviando il percorso anziché la stringa di query. Questi problemi risolti erano parametri di stringa query troncati e non raccolti.

## H.23.3 {#section_EAB0602E07EE4A5CA6521351F461D22D}

Release Date: **May 2011**

* È stato risolto un problema che impediva l'invio della variabile di tracciamento video (pev3).
* È stato risolto un problema che impediva alla `s_gi` chiamata di abilitare il codice in modo che fosse compatibile con il codice G e H. Quando passi un 1 come secondo parametro a questa chiamata, il codice ora è configurato per essere compatibile con entrambe le versioni.

## H.23.2 {#section_274143E83A8D42F1AD40CAE4326E99CE}

Release Date: **April 2011**

* Supporto per contextData che supporta le regole di elaborazione lato server (solo v15).
* Supporto per chiamate server di luce (solo v15).
* Supporto per l'assegnazione di un valore diverso da 1 a un evento contatore nell'elenco degli eventi.
* Supporto per un nuovo metodo di tracciamento dei video mediante eVar di conversione ed eventi (attualmente in versione beta).
* È stato rimosso il supporto per l’impostazione di Media.trackWhenPlaying su false. Sarà sempre vero.
* È stato aggiunto il flag debugTracking per abilitare la registrazione delle richieste inviate alla console Firebug come le altre piattaforme.
* Accertatevi che "+" sia sempre con codifica URL, indipendentemente dal browser.
