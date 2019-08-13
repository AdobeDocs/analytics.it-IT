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
source-git-commit: 0143edbcbab3450f6932367f51e9e4c79bc1ae63

---


# AppMeasurement per JavaScript{#appmeasurement-for-javascript}

Note sulla versione cumulative per [!DNL AppMeasurement] javascript.

<!-- 

<p>https://wiki.corp.adobe.com/display/omtrcache/AppMeasurement+Change+Log </p>

 -->

L'ultima versione di ciascuna libreria può essere scaricata in **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Code Manager]**.

## Versione 2.16.0

Release Date: **August 15, 2019**

| Funzione | Descrizione |
| -----------| ---------- |
| Supporto di `sendBeacon` per i collegamenti in uscita | In `sendBeacon` è stato implementato il supporto di [!UICONTROL AppMeasurement] per i collegamenti di uscita. Questo migliorerà il tracciamento dei collegamenti in uscita e determinerà probabilmente un aumento del traffico. `SendBeacon` non viene eseguito nel contesto di una pagina ma nel contesto del browser. Se una pagina viene scaricata con `sendBeacon`, la richiesta sarà comunque completata. Questo è molto utile per i collegamenti exit, perché rende molto più probabile che la richiesta di collegamento exit venga completata. |
| Valori ECID/fid | I valori ECID/fid ora sono memorizzati nella cache al primo hit anche se le impostazioni Opt-In cambiano. |
| DIL 9.3 | Il modulo Gestione dell’audience è stato aggiornato a DIL 9.3 |
| Tracciamento della portata di scorrimento | È stato esposto uno switch in s.ActivityMap.trackScrollReach per attivare o disattivare il tracciamento della portata di scorrimento. |
| Servizio ID visitatori 4.4.0 | AppMeasurement è stato aggiornato per utilizzare il servizio ID visitatori 4.4.0. |

## Versione 2.15.0

Data di rilascio:**15 luglio 2019**

* È stato aggiunto il tracciamento della portata di scorrimento activitymap all'estensione Activity Map (AN -172949)
* Aggiunto DIL 9.2 ad appmeasurement (AN -182472)

## Versione 2.14.0

Release Date: **May 21, 2019**

* Risolti i problemi relativi alla gestione dello stato dei parametri del tracker quando più hit sono in sospeso. (AN-176931, AN-176629, DTM-12758)
* Aggiornato AppMeasurement per includere Visitor.js 4.3.0 (AN-180049)

## Versione 2.13.0

Data di rilascio:**10 aprile 2019**

Correzione di molti problemi segnalati con clearvars. Il problema si verifica quando gli hit vengono inviati prima che il tracciamento sia pronto. Quando il tracciamento diventa pronto, la libreria può impostare variabili che sono state già cancellate o modificate. (AN-176931, AN-176629, DTM-12758).

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

## Versione 2.10.0 {#section_0788526EF23049C9AEB1EE5E8FC985DD}

Release Date: **09/20/2018**

This release ensures that the [!DNL AppMeasurement] library submits cookies correctly for all connection types.

* [!DNL AppMeasurement] blocca la trasmissione dei cookie durante richieste POST. (AN-165538)
* È stato interrotto il supporto per XDomainRequest. (AN-165733)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)
* Remove the Media Module from the Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## Versione 2.9.0 {#section_E973B8A628F348AA9A1A1599CFE37DB9}

Release Date: **05/24/2018**

>[!NOTE]
>
>Visitor API 3.0 or higher is required for customers using the [!DNL Experience Cloud] ID Service. Adobe consiglia di eseguire l'aggiornamento alla versione più recente dell'API visitatore ogni volta che le librerie di codice associate vengono aggiornate ([!DNL at.js] e così via).[!DNL AppMeasurement.js]

* Updated [!DNL AppMeasurement] to use the updated Visitor interface for requesting IDs. (AN-151483)
* È stato corretto un problema a causa del quale i cookie di tracciamento dei collegamenti venivano scritti dopo la disattivazione del tracciamento dei collegamenti. (AN-156332)
* È stato risolto un problema che causava `registerPreTrackCallback` la `registerPostTrackCallback` firma di una firma di callback quando veniva richiamata più volte. (AN-158566)

## Versione 2.8.2 {#section_B70EAEDAB087464482DB04EC4187200D}

Release Date: **04/12/2018**

* Update [!DNL AppMeasurement] to use the updated visitor interface for requesting IDs. (AN-151483)
* Il cookie di tracciamento dei collegamenti viene scritto anche dopo la disattivazione della funzione di tracciamento dei collegamenti. (AN-156332)
* Reduce [!DNL AppMeasurement] default cookie lifetime from five to two years. (AN-158572)

## Versione 2.8.1 {#section_6C1C4091F2EE4C90B6F3D7EE783DD884}

Release Date: **03/29/2018**

Rebundle Visitor API 3.1.0 (AN -159524), che include i seguenti hotfix: (CORE -11390, CORE -10634)

## Versione 2.8.0 {#section_A23AD604D34C497C9318D3EB211B7927}

Release Date: **03/15/2018**

Rebundle Visitor API 3.1.0 (AN -159524), che include i seguenti hotfix: (CORE -11390, CORE -10634)

* Bundle VAPI v 3.1 con [!DNL AppMeasurement] v 2.8. (AN-158353)
* Fattore di creazione del punto finale della raccolta dati per facilitare la condivisione. (AN-156647)
* Aggiungere metriche di temporizzazione round-trip a [!DNL AppMeasurement]. (AN-158343)

## Versione 2.7.0 {#section_2C047D410B614CEE950DBBC75F035033}

Release date: **01/18/2018**

* Fine del supporto per IE da 6 a 9
* Inclusione di Visitor API v3.0.0
* Inclusione di DIL v7.00 

## Versione 2.6.0 {#section_229356205EAB4D05890A00B39C42A650}

Release date: **11/09/2017**

Fixed an issue where [!DNL AppMeasurement] library does not always set the correct account combination when s_gl is called. (AN-152153)

## Versione 2.5.0 {#section_3C0006D526CA405FA0C47E2D991012BA}

Release date: **09/21/2017**

* Inclusion of [!DNL dil.js 6.12] ( [!DNL Audience Manager] module)

* Inclusione di Visitor API 2.5.0.

## Versione 2.4.0 {#section_60D01A128AEE4A97AC492DF8FBE1E7A3}

Release date: **08/17/2017**

* Inclusa dil.js v6.11
* Inclusa Visitor API 2.4.0

## Versione 2.3.0 {#section_D8F9BFF0D4E44E0F876840360D56E815}

Release date: **07/20/2017**

* È stato corretto un bug in cui [!DNL s.Util.getQueryParam] acquisiva #
* Added v6.10 of [!DNL dil.js] (AN-145701)

## Versione 2.2.0 {#section_5E23F21413B1443B9A3021CCC9578C4B}

Release date: **06/08/2017**

* Added support for multiple [!DNL AppMeasurement] instantiation order. (AN-138237)
* Inclusione della versione 2.2.0 dell'API visitatore. (AN-144042)

## Versione 2.1.0 {#section_5FE53738F9124C86811DFA08923B6F7B}

* Inclusa versione aggiornata di [!DNL dil.js] (AN-140396)
* Added support for `adobe_mc_ref` parameter which overrides the page referrer. (AN-131920)
* API 2.1.0 visitatore nuovamente inclusa. (AN-140873)
* `mcorgid` Aggiunto parametro. (AN-139586)
* Aggiunto parametro cp (customerPerspective). (AN-140897)

## Versione 2.0.0 {#section_4C4A502CDFC84F06914EB16CE77736D1}

Release date: **03/09/2017**

* È stato spostato a un nuovo processo di build che richiede un aggiornamento del numero di versione a 2.0.0. (AN-137878)
* È stata spostata la gestione di mboxMCSDID nella posizione della sezione corretta in cui viene effettuata la chiamata di tracciamento. (AN-138483)

## Versione 1.8.0 {#section_617B2F09F3494C04901E364ACEDE17E1}

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

   La callback viene richiamata con i `requestUrl` parametri passati al momento della registrazione del callback. Ciò si verifica prima o dopo la chiamata di tracciamento, a seconda del metodo utilizzato per registrare il callback. L'ordine in cui tali callback vengono invocati non è garantito. I callback registrati nella funzione pranziana vengono invocati dopo la creazione dell'URL di tracciamento finale. I callback post vengono chiamati a seguito di una chiamata di tracciamento completata (se la chiamata di tracciamento non riesce, queste funzioni non vengono chiamate). Qualsiasi callback registrato non `registerPreTrackCallback` influisce sulla chiamata di tracciamento. Inoltre, la chiamata di qualsiasi metodo di tracciamento in qualsiasi callback registrato non è consigliata e potrebbe provocare un ciclo infinito.

## Versione 1.7.0 {#section_A93F24391B1043F4A435D1AA76D9E4F0}

Aggiornato: **11/10/2016**

* Inclusa Visitor API 1.10.1.

## Versione 1.7.0 {#section_107CDB8468AE4B06B900DCDEE5AD2F0A}

Aggiornato: **10/20/2016**

* Update [!DNL Audience Manager] module with Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusione di Visitor API 1.9.0. (AN-132072)

## Versione 1.7.0 {#section_945311938EE2480A9A697BFE1E5B2AA7}

Aggiornato: **9/15/2016**

* Modulo aggiornamento [!DNL AppMeasurement][!DNL Audience Manager] con DIL 6.5 e configurazioni aggiuntive (AN -129411)

* Inclusione dell’API del visitatore API 1.8.0 (AN-129887)

## Versione 1.6.4 {#section_7C40FE01EA5B43E486098FCAC8FA5EC3}

Aggiornato: **8/18/2016**

* Updated [!DNL AppMeasurement] to read and write AMCV cookies. (AN-127098)
* Inclusione di Visitor API 1.7.0.

>[!NOTE]
>
>Also see the following release notes for [!DNL JavaScript] version 1.6.3, which includes updated requirements for Marketing Cloud ID service.

## Versione 1.6.3 {#section_34C75470A84B461A89FEF8CFF7B94090}

Aggiornato: **8/4/2016**

* Fixed an issue where [!DNL AppMeasurement] prematurely terminated request connections. (AN-126448)

>[!IMPORTANT]
>
>Version 1.6.0 of the [!DNL Marketing Cloud] ID service *requires* [!DNL AppMeasurement] for [!DNL JavaScript] version 1.6.3 or higher. If you want to upgrade to version 1.6.0 of the Marketing Cloud ID service, please make sure you are using [!DNL AppMeasurement] code verison 1.6.3 or higher.

## Versione 1.6.2 {#section_419CBF264B5741DABB005AFDC6197C0D}

Data di rilascio:**21 luglio 2016**

* Inclusione di Visitor API 1.6.0.
* Fixed an issue causing [!DNL AppMeasurement] to call the wrong obfuscated method in the Visitor API. (AN-126006)
* Fixed an issue causing the [!DNL JavaScript] error: "Attribute only valid on v:image". (AN-124009)

<!-- 

<note type="important">
  Adobe strongly recommends upgrading to version 1.6.2 or higher. This version requires Visitor API 1.6.0, and vice-versa. 
</note>

 -->

## Versione 1.6.1 {#section_E69F5883F84F4D2CAE25D385F56C6AF6}

Data di rilascio: **16 giugno 2016**

Inclusione di Visitor API 1.5.7.

## Versione 1.6.1 {#section_5927689A57164EC99BA501B4FDF0AE8F}

Release Date: **May 19, 2016**

[!DNL JavaScript] versione 1.5.6

* Inclusione di Visitor API 1.5.6
* Risoluzione della gestione del tracciamento del clic su collegamento in Firefox che non attivava l'evento completo. 

## Versione 1.6 {#section_B132B272FC2E43E9A24198F459E29403}

Data di rilascio:**21 aprile 2016**

* [!DNL AppMeasurement][!DNL Activity Map] Il modulo è stato integrato nel modulo [!DNL AppMeasurement] standard, per fare in modo che sia necessario fare riferimento a un [!DNL .js] solo file. [!DNL Activity Map] Inoltre, il tracciamento è attivato per impostazione predefinita. (AN-112689)

* Fixed a truncation issue occurring with the order of query-string variables in [!DNL AppMeasurement], so that *`pageURLRest`* is last. (AN-114647)

## Versione 1.5.4 {#section_A230E5F656734ABD9917388790A37B5D}

Release Date: **March 17, 2016**

* Inclusione di Visitor API 1.5.4
* Supporto per la rinuncia API visitatore 1.5.4 +

## Versione 1.5.3 {#section_796927A1BBF74DF6A1A4B9477E0BD20E}

Release Date: **January 21, 2016**

* Fixed handling of [!DNL Audience Manager] module when POSTs are used for tracking calls. (AN-115381)
* Il resto dell'URL della pagina ("-g") è stato spostato alla fine della stringa di query della richiesta di tracciamento. (AN-114647)

## Versione 1.5.2 {#section_17CFD0BBC8744447BDFCC833883BC93E}

Data di rilascio: **5 novembre 2015**

* Inclusione di Visitor API 1.5.3.
* Rilevamento fisso di IE 11 per il Truncation 2047 (AN -114914)

## Versione 1.5.1 {#section_432F3C69DDBB49C983D7CB0876C2152F}

Release Date: **September 17, 2015**

* Inclusione di API visitatore 1.5.2

## Versione 1.5.1 {#section_077DA135C1A5466EB00C44A3C3E472F8}

Release Date: **August 29, 2015**

* Inclusione di API visitatore 1.5.1.

## Versione 1.5.1 {#section_3C9637EDB058479184731067897E857C}

Data di rilascio:**16 luglio 2015**

* Modulo aggiornato [!DNL Audience Manager] per utilizzare AAM DIL 6.2 - getcustomer ID da visitorapi. js e passarli in /event call to AAM. (AN-104978)

## Versione 1.5 {#section_8809DBD822E440C6B5B7FF41E5DF3015}

Data di rilascio: **18 giugno 2015**

* Supporto per l'API visitatore 1.5 che utilizza il metodo *`getCustomerIDs`* per raccogliere gli ID del cliente e lo stato autenticato e invia tali ID con le richieste di raccolta dei dati.
* Fixed the creation of duplicate destinationing iframe in **[!UICONTROL AudienceManagement]** module (DIL 6.1)
* Risolto il problema noto descritto nella release 1.4.5.

## Versione 1.4.5 {#section_FA2E94DF78614ACE9944660E14EF3A75}

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
   <td colname="col2"> <p> Starting in <span class="keyword"> iOS </span> SDK version 4.5, a new <span class="keyword"> iOS </span> extension lets you collect usage data from your Apple Watch Apps, Today Widgets, Photo Editing widgets, and all the other <span class="keyword"> iOS </span> extension apps. </p> <p>Consultate <a href="https://marketing.adobe.com/resources/help/en_US/mobile/ios/?f=ios_ext" format="https" scope="external"> Implementazione </a>estensione iOS. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="keyword"> Estensione </span> wearable Android </p> </td> 
   <td colname="col2"> <p> Starting in <span class="keyword"> Android </span> SDK version 4.5, a new <span class="keyword"> Android </span> extension lets you collect data from your <span class="keyword"> Android </span> Wearable app. </p> <p>Consultate <a href="https://marketing.adobe.com/resources/help/en_US/mobile/android/?f=android_wearable" format="https" scope="external"> Estensione indossabile Android </a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

* Inclusione di Visitor API 1.4.
* È stato aggiornato il modulo audiencemanagement per utilizzare DIL versione 6.0.

**Problema noto**

Nelle integrazioni API/ [!DNL AppMeasurement][!DNL Audience Manager] Modulo Visitor, ci sono due destinazioni che pubblicano le richieste iframe effettuate in IE 6-9: `//fast.<subdomain>.demdex.net/dest5.html` e `//fast.<subdomain>.demdex.net/dest4.html`. Come visto negli altri browser, la procedura corretta prevede di caricare solo `//fast.<subdomain>.demdex.net/dest5.html`.

## Versione 1.4.4 {#section_C069FA04496C4F7DAC165B04E836CF1F}

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
   <td colname="1"> <p>Supporto di tracciamento Beacon in <span class="keyword"> phonegap </span> </p> </td> 
   <td colname="2"> <p>Le <code> chiamate trackbeacon </code> e <code> clearcurrentbeacon </code> sono ora disponibili in <span class="keyword"> phonegap </span>. </p> </td> 
  </tr> 
 </tbody> 
</table>

Una correzione secondaria per cancellare l'ID del profilo di chiamata del server chiaro dopo la `trackLight` chiamata.

## Versione 1.4.3 {#section_C307052BA42248ADB1969AE7A2593177}

Data di rilascio:**19 febbraio 2015**

* Tutta la gestione delle chiamate di monitoraggio ritardate è stata resa coerente. In tal modo vengono corretti i problemi con le variabili sottoposte a backup durante il ritardo, come l'oggetto selezionato con un clic.
* È stato modificato per non effettuare in maniera automatica il tracciamento del referente dopo la prima chiamata di tracciamento affinché la seconda, terza ecc. chiamata di tracciamento (solitamente tracciamento collegamenti) non conti due volte il referente quando *`s.referrer`* è stato impostato manualmente prima della prima chiamata di tracciamento.
* Lo zip di distribuzione è stato aggiornato per includere API Visitor 1.3.5.

## Versione 1.4.2 {#section_0A0BE40D32144A338231022F97B0E72B}

Release Date: **January 15, 2015**

* Risoluzione della gestione del WebKit di pre-rendering per impedire il tracciamento di pagine sottoposte a pre rendering che non vengono visualizzate.
* The distribution zip was updated to include Visitor API 1.3.4 and an updated **[!UICONTROL AudienceManagement]** module that includes DIL version 5.5.

## Versione 1.4.1 {#section_616FF936062F44E8B70032D18AAAFC5F}

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
   >Per [!DNL Analytics] una chiamata che utilizzi il metodo POST anziché il metodo GET in [!DNL AppMeasurement] (un metodo di risoluzione [degli URL troncati in IE](https://helpx.adobe.com/analytics/kb/shortening-image-request-urls.html)), devi utilizzare l'implementazione più recente [del servizio](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_implement) ID visitatore per Marketing Cloud.

## Versione 1.4 {#section_56ADFF9416B14ABCB3862B00F72B30A1}

Release Date: **August 21, 2014**

* Rimosso il tracciamento dei plug-in del browser (parametro query `p`) poiché i plug-in non sono più segnalati nella versione 15.
* Addition of the **[!UICONTROL AudienceManagement]** Module in the download zip.

Aggiunto supporto per [evar aggiuntivi](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=evars_events) (76 - 250) ed eventi (101-1000).

>[!NOTE]
>
>Il codice H-Code non supporta evar ed eventi aggiuntivi.

[!DNL JavaScript]

## Versione 1.3.2 {#section_402A4142C4B846DE945FD59DAD9D9298}

Data di rilascio: **19 giugno 2014**

* È stata risolta la gestione dei flag eseguiti e di attesa per i campi API visitatore, ad esempio l'ID [!DNL Analytics] visitatore legacy, che causava errori.
* Supporto per nuove funzioni nel servizio ID visitatore 1.3.

## Versione 1.3.1 {#section_5E65422B9C1E4437A2473B119A14163E}

Release Date: **May 22, 2014**

* [!DNL AppMeasurement] per [!DNL JavaScript]`s_gi` la funzione non individuava correttamente le istanze create utilizzando il codice `s_gi`H. Questo problema ha interessato solo alcune implementazioni di tag doppie, in cui [!DNL AppMeasurement] per il [!DNL JavaScript] codice H si trovavano sulla stessa pagina con istanze separate, e `s_gi` venivano utilizzate per trovare istanze per suite di rapporti.

## Versione 1.3 {#section_56B2C625368E4A5BA1E8770A8C78117D}

Data di rilascio:**17 aprile 2014**

* Supporto del servizio ID visitatori [di Marketing Cloud](https://marketing.adobe.com/resources/help/en_US/mcvid/).

## Versione 1.2.4 {#section_94D9521FDBAB4224994B1671A9BD036B}

Release Date: **March 13, 2014**

* Correzioni di bug per video heartbeat.

## Versione 1.2.3 {#section_7ED201192D05463DA9B1990EC281B142}

Data di rilascio:**20 febbraio 2014**

* Correzioni di bug per video heartbeat.

## Versione 1.2.2 {#section_E6CDDDB8EE214ADCBF3047EC42711F13}

Data di rilascio:**6 febbraio 2014**

* Risolto un problema di compatibilità con il [!DNL Audience Manager] modulo DIL. [!DNL Audience Manager] i clienti devono inoltre aggiornare alla versione 4.8 del modulo DIL.

## Versione 1.2.1 {#section_6DA9384BC2C84698952D51FFB3732019}

Data di rilascio: **15 novembre 2013**

* Sono stati corretti eventi di pagina che vengono [utilizzati per la misurazione del video heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).

## Versione 1.2 {#section_BDBE0C3D15F04856ABC6F111DDE6C8DB}

Data di rilascio: **14 novembre 2013**

* È stato aggiunto il supporto per [la misurazione del video heartbeat](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/).
* [!DNL VisitorAPI.js] è stato aggiunto per supportare [il servizio ID visitatori](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_service#).

## Versione 1.1.1 {#section_31F06384039648BB99F4BD630B685794}

* Non è stata possibile inviare una chiamata di tracciamento del collegamento dai browser Opera per i collegamenti che iniziano con «opera: " ("opera: " è simile a "about" and "chrome: " in altri browser).
* Aggiunto `alt=""` a tutti gli oggetti Immagine in conformità con i Video e le comunicazioni accessibili.

## Versione 1.1 {#section_4508FF0A14AE46DF96A08B5C6703E123}

Release Date: **September 18, 2013**

* È stato corretto il supporto per il posizionamento della libreria e del codice della pagina nel `head` tag.
* Supporto del modulo `onLoad` mancante.

## Versione 1.0.3 {#section_A74A78C30067480AB36C54A06706DF89}

Release Date: **August 15, 2013**

* È stato aggiunto il supporto per la distribuzione tramite gestione tag Adobe.
* È stato risolto un problema che impediva la configurazione delle variabili gerarchiche sull' [!DNL AppMeasurement] oggetto.

## Versione 1.0.2 {#section_C3BDD9A19EF84467A8FDC283AEAE2DB5}

Data di rilascio:**18 luglio 2013**

* L'hash/frammento viene ora ignorato mediante il tracciamento automatico dei collegamenti. In precedenza, l'URL seguente veniva tracciato automaticamente in seguito alla fine dell'intero `href` accesso `.pdf`:

   ```js
   <a href="index.htm#anchor.pdf">Test Link</a>
   ```

   Ora l'hash/frammento viene ignorato in modo che il collegamento venga tracciato solo quando il nome del file termina in un'estensione corrispondente.

## Versione 1.0.1 {#section_3758B0C47171436ABB4B29F5924BE893}

Release Date: **May 23, 2013**

In Code Manager è ora disponibile una nuova [!DNL JavaScript][!DNL AppMeasurement] libreria. Questa libreria fornisce la stessa funzionalità di base di [!DNL s_code.js], ma è più leggera e veloce per l'utilizzo sia sui siti mobili che sui siti desktop.

* 3-7 x più veloce del codice H .25.
* Solo 21 k non compressa e 8 kzicompressa (il codice H .25 è di 33 k non compresso e 13 k è decompressa).
* Supporto nativo per ottenere parametri di query, leggere e scrivere cookie ed eseguire il tracciamento avanzato dei collegamenti.
* Sufficientemente veloce e veloce da usare con siti mobili e sufficientemente robusti da utilizzare sul web desktop completo, consentendoti di sfruttare una singola libreria in tutti gli ambienti web.

Consulta [appmeasurement per Javascript](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=appmeasure_mjs) nella Guida [!DNL Analytics] all'implementazione.

>[!NOTE]
>
>Alcuni plug-in non sono supportati in questa nuova versione. Per [informazioni dettagliate, consultate Supporto](https://marketing.adobe.com/resources/help/en_US/sc/implement/index.html?f=plugins_support) plug-in.
