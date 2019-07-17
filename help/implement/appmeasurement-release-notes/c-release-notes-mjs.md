---
description: Note sulla versione cumulative per appmeasurement per javascript.
seo-description: Note sulla versione cumulative per appmeasurement per javascript.
seo-title: AppMeasurement per JavaScript
solution: Analytics
subtopic: Note sulla versione
title: AppMeasurement per JavaScript
topic: Sviluppatore e implementazione
uuid: 1440013 d-d 266-4 dce -9807-8 b 9 adac 73315
translation-type: tm+mt
source-git-commit: 12f8d0017acfad36f3445cd31a629725dd737686

---


# AppMeasurement per JavaScript{#appmeasurement-for-javascript}

Cumulative release notes for [!DNL AppMeasurement] for JavaScript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

The latest version of each library can be downloaded in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.

## Versione 2.15.0

Data di rilascio:**15 luglio 2019**

* È stato aggiunto il tracciamento della portata di scorrimento activitymap all'estensione Activity Map (AN -172949)
* Aggiunto DIL 9.2 ad appmeasurement (AN -182472)

## Versione 2.14.0

Release Date: **May 21, 2019**

* Risolti problemi relativi alla gestione dello stato dei parametri del tracciatore quando sono in sospeso più hit. (AN -176931, AN -176629, DTM -12758)
* Aggiornato appmeasurement per includere Visitor. js 4.3.0 (AN -180049)

## Versione 2.13.0

Data di rilascio:**10 aprile 2019**

Correzione di molti problemi segnalati con clearvars. Il problema si verifica quando gli hit vengono inviati prima che il tracciamento sia pronto. Quando il tracciamento diventa pronto, la libreria può impostare variabili che sono state già cancellate o modificate. (AN -176931, AN -176629, DTM -12758).

## Versione 2.12.0

Release Date: **02/22/2019**

* Il modulo Gestione dell'audience è stato aggiornato a DIL 9.1. (AN-175255)
* Il criterio di sicurezza GTM non consente l’esecuzione del modulo Activity Map. (AN-174679)
* Appmeasurement migliorato per rispettare la rinuncia quando il servizio identità non viene approvato nell'optedin. (AN-175259)

## Versione 2.11.0

Release Date: **02/11/2019**

* Aggiunto supporto per la nuova funzionalità servizi Opt-in di Adobe in AppMeasurement. (AN-163546)
* Aggiunto supporto per l’archiviazione dei dati di tracciamento collegamenti in memoria sessione. (AN-162272)
* Aggiunto supporto per il tipo di flusso multimediale per Audio Analytics. (AN-173265)

## Version 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Release Date: **09/20/2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] blocca la trasmissione dei cookie durante richieste POST. (AN-165538)
* È stato interrotto il supporto per XDomainRequest. (AN-165733)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## Version 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

Release Date: **05/24/2018**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. Adobe recommends upgrading to the latest Visitor API version whenever associated code libraries are updated ( [!DNL at.js], [!DNL AppMeasurement.js], and so forth.)

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483)
* È stato corretto un problema a causa del quale i cookie di tracciamento dei collegamenti venivano scritti dopo la disattivazione del tracciamento dei collegamenti. (AN-156332)
* Fixed an issue where `registerPreTrackCallback` and `registerPostTrackCallback` breaks callback function signature when called multiple times. (AN-158566)

## Version 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

Release Date: **04/12/2018**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483)
* Il cookie di tracciamento dei collegamenti viene scritto anche dopo la disattivazione della funzione di tracciamento dei collegamenti. (AN-156332)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## Version 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

Release Date: **03/29/2018**

Rebundle Visitor API 3.1.0 (AN -159524), che include i seguenti hotfix: (CORE -11390, CORE -10634)

## Version 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

Release Date: **03/15/2018**

Rebundle Visitor API 3.1.0 (AN -159524), che include i seguenti hotfix: (CORE -11390, CORE -10634)

* Bundle VAPI v3.1 with [!DNL AppMeasurement] v2.8. (AN-158353)
* Fattore di creazione del punto finale della raccolta dati per facilitare la condivisione. (AN-156647)
* Add request round-trip timing metrics to [!DNL AppMeasurement]. (AN-158343)

## Version 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

Release date: **01/18/2018**

* Fine del supporto per IE da 6 a 9
* Inclusione di Visitor API v3.0.0
* Inclusione di DIL v7.00 

## Version 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

Release date: **11/09/2017**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## Version 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

Release date: **09/21/2017**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module)

* Inclusione di Visitor API 2.5.0.

## Version 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

Release date: **08/17/2017**

* Inclusa dil.js v6.11
* Inclusa Visitor API 2.4.0

## Version 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

Release date: **07/20/2017**

* È stato corretto un bug in cui [!DNL s.Util.getQueryParam] acquisiva #
* Added v6.10 of [!DNL dil.js] (AN-145701)

## Version 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

Release date: **06/08/2017**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237)
* Inclusione della versione 2.2.0 dell'API visitatore. (AN-144042)

## Version 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* Inclusa versione aggiornata di [!DNL dil.js] (AN-140396)
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920)
* API 2.1.0 visitatore nuovamente inclusa. (AN-140873)
* `mcorgid` Aggiunto parametro. (AN-139586)
* Aggiunto parametro cp (customerPerspective). (AN-140897)

## Version 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

Release date: **03/09/2017**

* È stato spostato a un nuovo processo di build che richiede un aggiornamento del numero di versione a 2.0.0. (AN-137878)
* È stata spostata la gestione di mboxMCSDID nella posizione della sezione corretta in cui viene effettuata la chiamata di tracciamento. (AN-138483)

## Version 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

Release date: **01/19/2017**

* Includi visitorapi 2.0.0
* È stata modificata la sequenza di chiamate di funzioni e verifiche in modo che SDID viene consumato dopo il completamento della verifica di interruzione. (AN-134364)
* Sono stati aggiunti i seguenti hook di chiamate pre e post tracciamento. (AN-134567)

   * s.registerPreTrackCallback
   * s.registerPostTrackCallback
   Queste funzioni sono utilizzate come parametri: callback (una funzione) e i parametri a tale funzione. Ad esempio:

   ```
   s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
       console.log("pre track callback"); 
       console.dir(requestUrl); // Request URL 
       console.dir(a); // param1 
       console.dir(b); // param2 
       console.dir(c); // param3 
   }, "param1", "param2", "param3");
   ```

   The callback is invoked with the `requestUrl` and any parameters passed in when the callback is registered. Ciò si verifica prima o dopo la chiamata di tracciamento, a seconda del metodo utilizzato per registrare il callback. L'ordine in cui tali callback vengono invocati non è garantito. I callback registrati nella funzione pranziana vengono invocati dopo la creazione dell'URL di tracciamento finale. I callback post vengono chiamati a seguito di una chiamata di tracciamento completata (se la chiamata di tracciamento non riesce, queste funzioni non vengono chiamate). Any callback registered with `registerPreTrackCallback` do not affect the tracking call. Inoltre, la chiamata di qualsiasi metodo di tracciamento in qualsiasi callback registrato non è consigliata e potrebbe provocare un ciclo infinito.

## Version 1.7.0 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

Updated: **11/10/2016**

* Inclusa Visitor API 1.10.1.

## Version 1.7.0 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

Updated: **10/20/2016**

* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusione di Visitor API 1.9.0. (AN-132072)

## Version 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

Updated: **9/15/2016**

* Update [!DNL AppMeasurement] [!DNL Audience Manager] Module with DIL 6.5 and Additional Configurations (AN-129411)

* Inclusione dell’API del visitatore API 1.8.0 (AN-129887)

## Version 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

Updated: **8/18/2016**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098)
* Inclusione di Visitor API 1.7.0.

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Marketing Cloud ID service.

## Version 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

Updated: **8/4/2016**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Marketing Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Marketing Cloud ID service, please make sure you are using [!DNL AppMeasurement] code verison 1.6.3 or higher.

## Version 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

Data di rilascio:**21 luglio 2016**

* Inclusione di Visitor API 1.6.0.
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006)
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa. 
</note>

 -->

## Version 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

Data di rilascio: **16 giugno 2016**

Inclusione di Visitor API 1.5.7.

## Version 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

Release Date: **May 19, 2016**

[!DNL JavaScript] versione 1.5.6

* Inclusione di Visitor API 1.5.6
* Risoluzione della gestione del tracciamento del clic su collegamento in Firefox che non attivava l'evento completo. 

## Version 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

Data di rilascio:**21 aprile 2016**

* [!DNL AppMeasurement][!DNL Activity Map] Il modulo è stato integrato nel modulo [!DNL AppMeasurement] standard, per fare in modo che sia necessario fare riferimento a un [!DNL .js] solo file. [!DNL Activity Map] Inoltre, il tracciamento è attivato per impostazione predefinita. (AN-112689)

* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## Version 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

Release Date: **March 17, 2016**

* Inclusione di Visitor API 1.5.4
* Supporto per la rinuncia API visitatore 1.5.4 +

## Version 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

Release Date: **January 21, 2016**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381)
* Il resto dell'URL della pagina ("-g") è stato spostato alla fine della stringa di query della richiesta di tracciamento. (AN-114647)

## Version 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

Data di rilascio: **5 novembre 2015**

* Inclusione di Visitor API 1.5.3.
* Rilevamento fisso di IE 11 per il Truncation 2047 (AN -114914)

## Version 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

Release Date: **September 17, 2015**

* Inclusione di API visitatore 1.5.2

## Version 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

Release Date: **August 29, 2015**

* Inclusione di API visitatore 1.5.1.

## Version 1.5.1 {#section_3C9637EDB058479184731067897E857C}

Data di rilascio:**16 luglio 2015**

* Updated [!DNL Audience Manager] module to use AAM DIL 6.2 - getCustomer IDs from VisitorAPI.js and pass them in /event call to AAM. (AN-104978)

## Version 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

Data di rilascio: **18 giugno 2015**

* Support for Visitor API 1.5, which uses the *`getCustomerIDs`* method to gather Customer IDs and authenticated state, and sends the IDs in with data collection requests.
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1)
* Risolto il problema noto descritto nella release 1.4.5.

## Version 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

Release Date: **May 21, 2015**

<table id="table_E0F3EF51FED44420AC97ACF0684554D0"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Funzione </th> 
   <th colname="col2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"></span> Estensione iOS </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> iOS </span> SDK version 4.5, a new <span class="keyword"> iOS </span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS </span> extension apps. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external"> iOS Extension Implementation </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Estensione </span> wearable Android </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> Android </span> SDK version 4.5, a new <span class="keyword"> Android </span> extension lets you collect data from your <span class="keyword"> Android </span> Wearable app. </p> <p>See <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external"> Android Wearable Extension </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

* Inclusione di Visitor API 1.4.
* È stato aggiornato il modulo audiencemanagement per utilizzare DIL versione 6.0.

**Problema noto**

In the Visitor API / [!DNL AppMeasurement] [!DNL Audience Manager] Module integrations, there will be two destination publishing iFrame requests made in IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` and  `//fast.<subdomain>.demdex.net/dest4.html`. Come visto negli altri browser, la procedura corretta prevede di caricare solo `//fast.<subdomain>.demdex.net/dest5.html`.

## Version 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

Data di rilascio:**16 aprile 2015**

<table frame="all" colsep="1" rowsep="1" id="table_812CAB7DDC364DAABB7CDEDE55532E39"> 
 <thead> 
  <tr rowsep="1"> 
   <th colname="1" class="entry"> Funzione </th> 
   <th colname="2" class="entry"> Descrizione </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr rowsep="1"> 
   <td colname="1"> <p> Dati personalizzati con metriche del ciclo di vita </p> </td> 
   <td colname="2"> <p>Ora puoi includere variabili di dati di contesto personalizzate con metriche del ciclo di vita. </p> </td> 
  </tr> 
  <tr rowsep="1"> 
   <td colname="1"> <p>Beacon tracking support in <span class="keyword"> PhoneGap </span> </p> </td> 
   <td colname="2"> <p>The <code> trackBeacon </code> and <code> clearCurrentBeacon </code> calls are now available in <span class="keyword"> PhoneGap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

A minor fix to clear the light-server call profile ID after the `trackLight` call.

## Version 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

Data di rilascio:**19 febbraio 2015**

* Tutta la gestione delle chiamate di monitoraggio ritardate è stata resa coerente. In tal modo vengono corretti i problemi con le variabili sottoposte a backup durante il ritardo, come l'oggetto selezionato con un clic.
* È stato modificato per non effettuare in maniera automatica il tracciamento del referente dopo la prima chiamata di tracciamento affinché la seconda, terza ecc. chiamata di tracciamento (solitamente tracciamento collegamenti) non conti due volte il referente quando *`s.referrer`* è stato impostato manualmente prima della prima chiamata di tracciamento.
* Lo zip di distribuzione è stato aggiornato per includere API Visitor 1.3.5.

## Version 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

Release Date: **January 15, 2015**

* Risoluzione della gestione del WebKit di pre-rendering per impedire il tracciamento di pagine sottoposte a pre rendering che non vengono visualizzate.
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

## Version 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

Release Date: **September 18, 2014**

* Aggiunta di una variabile `tagContainerMarker` che consente l'implementazione per specificare fino a 4 caratteri da aggiungere alla stringa della versione con un delimitatore di caratteri in forma di trattino. La variabile viene utilizzata per la gestione dinamica dei tag.

   ```js
   // JavaScript 
   s.tagContainerMarker = "D1.0"; 
   
   // Data Collection request 
   //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
   ```

   È possibile utilizzare 4 caratteri consentiti in percorsi di file URL, ad esempio caratteri alfanumerici e punto.

* Correzione di un loop che potrebbe verificarsi durante il monitoraggio automatico dei collegamenti (download e uscita) con monitoraggio forzato dei collegamenti abilitato (impostazione predefinita in browser WebKit) in pagine con doppio tag e codice H. Per evitare tali loop, è stata inoltre aggiunta una protezione automatica generale per il monitoraggio automatico dei collegamenti. Questa protezione limita il monitoraggio automatico dei collegamenti di clic ripetuti sullo *stesso* oggetto a una volta ogni 10 secondi. La protezione si applica solo al monitoraggio automatico dei collegamenti, le chiamate al monitoraggio manuale dei collegamenti (s. tl) non sono limitate. La protezione non viene applicata a clic su oggetti diversi, che vengono invece monitorati.
* Correzione relativa alla gestione di elementi oggetti di clic in caso sia necessario applicare un ritardo.
* Risoluzione del problema che causava un doppio conteggio pagina-vista in caso di chiamata a s.tl da una funzione di collegamento OnClick, nel caso in cui l'API Visitatore non contenga ancora i valori necessari.
* Supporto HTTP POST.

   >[!IMPORTANT]
   >
   >For an [!DNL Analytics] call to use the POST method instead of the GET method in [!DNL AppMeasurement] (a method of solving [truncated URLs in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), you must be using the latest [Visitor ID Service](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) implementation for Marketing Cloud.

## Version 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

Release Date: **August 21, 2014**

* Rimosso il tracciamento dei plug-in del browser (parametro query `p`) poiché i plug-in non sono più segnalati nella versione 15.
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.

Added support for [additional eVars](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=evars_events) (76 - 250) and events (101-1000).

>[!NOTE]
>
>Il codice H-Code non supporta evar ed eventi aggiuntivi.

[!DNL JavaScript]

## Version 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Data di rilascio: **19 giugno 2014**

* Fixed handling of done and waiting flags for Visitor API fields such as the legacy [!DNL Analytics] Visitor ID, that was causing errors.
* Supporto per nuove funzioni nel servizio ID visitatore 1.3.

## Version 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

Release Date: **May 22, 2014**

* [!DNL AppMeasurement] per [!DNL JavaScript]`s_gi` la funzione non individuava correttamente le istanze create utilizzando il codice `s_gi`H. Note that this issue only impacted some dual tagging implementations where [!DNL AppMeasurement] for [!DNL JavaScript] and H code were on the same page with separate instances, and `s_gi` was being used to find instances by report suite.

## Version 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

Data di rilascio:**17 aprile 2014**

* Support for the [Marketing Cloud Visitor ID service](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Version 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

Release Date: **March 13, 2014**

* Correzioni di bug per video heartbeat.

## Version 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

Data di rilascio:**20 febbraio 2014**

* Correzioni di bug per video heartbeat.

## Version 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

Data di rilascio:**6 febbraio 2014**

* Fixed a compatibility issue with the [!DNL Audience Manager] DIL module. [!DNL Audience Manager] i clienti devono inoltre aggiornare alla versione 4.8 del modulo DIL.

## Version 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

Data di rilascio: **15 novembre 2013**

* Fixed page events that are used for [heartbeat video measurement](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

## Version 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

Data di rilascio: **14 novembre 2013**

* Added support for [heartbeat video measurement](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* [!DNL VisitorAPI.js] è stato aggiunto per supportare [il servizio ID visitatori](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#).

## Version 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* Non è stata possibile inviare una chiamata di tracciamento del collegamento dai browser Opera per i collegamenti che iniziano con «opera: " ("opera: " è simile a "about" and "chrome: " in altri browser).
* Added `alt=""` to all Image objects to comply with Accessible Video and Communications Act.

## Version 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

Release Date: **September 18, 2013**

* Fixed support for placing the library and page code in the `head` tag.
* Added missing module `onLoad` support.

## Version 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

Release Date: **August 15, 2013**

* È stato aggiunto il supporto per la distribuzione tramite gestione tag Adobe.
* Fixed an issue that prevented hierarchy variables from being set on the [!DNL AppMeasurement] object.

## Version 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Data di rilascio:**18 luglio 2013**

* L'hash/frammento viene ora ignorato mediante il tracciamento automatico dei collegamenti. Previously the following URL was automatically tracked since the entire `href` ended in `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Ora l'hash/frammento viene ignorato in modo che il collegamento venga tracciato solo quando il nome del file termina in un'estensione corrispondente.

## Version 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

Release Date: **May 23, 2013**

A new [!DNL JavaScript] [!DNL AppMeasurement] library is now available in Code Manager. This library provides the same core functionality of [!DNL s_code.js], but is lighter and faster for use on both mobile and desktop sites.

* 3-7 x più veloce del codice H .25.
* Solo 21 k non compressa e 8 kzicompressa (il codice H .25 è di 33 k non compresso e 13 k è decompressa).
* Supporto nativo per ottenere parametri di query, leggere e scrivere cookie ed eseguire il tracciamento avanzato dei collegamenti.
* Sufficientemente veloce e veloce da usare con siti mobili e sufficientemente robusti da utilizzare sul web desktop completo, consentendoti di sfruttare una singola libreria in tutti gli ambienti web.

See [AppMeasurement for Javascript](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=appmeasure_mjs) in the [!DNL Analytics] Implementation Guide.

>[!NOTE]
>
>Alcuni plug-in non sono supportati in questa nuova versione. See [Plug-in Support](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=plugins_support) for details.
