---
title: Note sulla versione di AppMeasurement per JavaScript
description: Note cumulative sulla versione di AppMeasurement per JavaScript.
feature: Appmeasurement Implementation
exl-id: 80b935f0-3ec5-4ffa-9858-f83ae9a6b763
role: Admin, Developer, Leader, User
source-git-commit: 886c6070936275cf1df269a951b87d041fcf7b8c
workflow-type: tm+mt
source-wordcount: '2726'
ht-degree: 86%

---

# Note sulla versione di AppMeasurement per JavaScript

>[!IMPORTANT]
>
>A partire da marzo 2025, questo articolo non sarà più aggiornato. Puoi visualizzare le note sulla versione di e scaricare la versione più recente di AppMeasurement da [GitHub](https://github.com/adobe/appmeasurement/releases).


## Versione 2.27.0

Data di rilascio: **martedì 12 agosto 2024**

* Il cookie `s_ac` è ora scritto con il flag `secure` se `writeSecureCookies` è stato abilitato.
* È stato corretto un errore di inizializzazione che si verificava quando la libreria era incorporata in linea.
* È stato corretto un errore se `localStorage` o `sessionStorage` è stato disabilitato.
* Gli User-Agent Hints ad alta entropia sono ora inclusi nelle chiamate di tracciamento dei collegamenti (`tl`) se `collectHighEntropyUserAgentHints` è stato abilitato.

## Versione 2.26.0

Data di rilascio: **martedì 4 marzo 2024**

* AppMeasurement riconosce e utilizza automaticamente il dominio radice per i domini di livello principale del codice del paese, che in precedenza richiedeva configurazioni specifiche del dominio dei cookie. L&#39;aggiornamento può avere implicazioni a causa di questo riconoscimento automatico. Per ulteriori informazioni, vedere [`cookieDomainPeriods`](/help/implement/vars/config-vars/cookiedomainperiods.md).
* La distribuzione include Identity Service Library 5.5.0 e Data Integration Library 9.6.

## Versione 2.25.0

Data di rilascio: **mercoledì 12 settembre 2023**

* È stato aggiunto il metodo opzionale [`bufferRequests()`](vars/functions/bufferrequests.md) per migliorare l&#39;affidabilità dell&#39;acquisizione delle richieste quando un browser non supporta l&#39;API Beacon o annulla le richieste quando una pagina viene scaricata.
* Sono state aggiunte delle protezioni per impedire più callback di post-tracciamento per una singola richiesta di tracciamento.

## Versione 2.24.0

Data di rilascio:**mercoledì 18 luglio 2023**

* È stata aggiunta la variabile di configurazione facoltativa [`decodeLinkParameters`](vars/config-vars/decodelinkparameters.md) per decodificare gli URL di collegamento che includono caratteri con codifica doppio byte.
* È stata aggiunta una gestione aggiuntiva degli errori per i browser con API di hint client dell’agente utente ad alta entropia errate.
* Intestazione POST Content-Type modificata per utilizzare `x-www-form-urlencoded` per impostazione predefinita.

## Versione 2.23.0

Data di rilascio: **23 settembre 2022**

* AppMeasurement ora supporta la raccolta di hint client ad alta entropia dall’agente utente utilizzati dai browser Chromium (Google Chrome e Microsoft Edge) per fornire informazioni sul dispositivo. È possibile configurare gli hint client tramite Tag o utilizzare la variabile di configurazione [`collectHighEntropyUserAgentHints`](vars/config-vars/collecthighentropyuseragenthints.md). La raccolta di hint ad alta entropia è disabilitata per impostazione predefinita. Ulteriori informazioni sugli [hint client](/help/technotes/client-hints.md) dell’agente utente.

## Versione 2.22.4

Data di rilascio: **18 gennaio 2022**

* La chiamata di tracciamento dei collegamenti `s.tl()` verifica se l’oggetto trasmesso contiene un attributo `href` di tipo `string`. Se non è un `string`, l&#39;attributo `href` verrà ignorato invece di generare un errore. Questo scenario può verificarsi quando trasmetti `svg` oggetti alla chiamata di tracciamento dei collegamenti.

## Versione 2.22.3

Data di rilascio: **11 ottobre 2021**

* Sono stati aggiornati i collegamenti nei file che facevano riferimento alla documentazione.

## Versione 2.22.2

Data di rilascio: **7 settembre 2021**

* Con questo aggiornamento, `opt.dmp` e `opt.sell` vengono sempre inclusi durante il tracciamento dei collegamenti. Per ulteriori informazioni, consulta la [segnalazione della privacy](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md) nella guida utente dell&#39;amministratore.

## Versione 2.22.1

Data di rilascio: **17 agosto 2021**

* I clienti che utilizzano la funzione di rinuncia potrebbero aver riscontrato che i parametri di rinuncia per l’inoltro lato server non venivano rispettati durante il tracciamento dei collegamenti. Le correzioni in questa versione causano l’invio dei flag di rinuncia se presenti durante il tracciamento dei collegamenti.

## Versione 2.22.0

Data di rilascio: **4 agosto 2020**

* È stata introdotta una correzione relativa al referente mancante quando il primo hit non veniva inviato a causa delle preferenze di rinuncia dell&#39;utente.

## Versione 2.21.0

Data di rilascio: **24 giugno 2020**

* È stato risolto un problema a causa del quale il filtro linkExclusions di Activity Map non veniva sempre applicato a Firefox.

## Versione 2.20.0

Data di rilascio: **5 marzo 2020**

* È stato risolto un problema relativo alla sicurezza aggiornando il rilevamento di Internet Explorer per sopprimere l’avvertenza JSLint.

## Versione 2.19.0

Data di rilascio:**21 febbraio 2020**

* Il modulo Gestione dell’audience è stato aggiornato a DIL 9.4. (AN-209341)

## Versione 2.18.0

Data di rilascio:**13 febbraio 2020**

* AppMeasurement può ora forzare i cookie a includere l’attributo Secure impostando la variabile [`writeSecureCookies`](vars/config-vars/writesecurecookies.md). Il requisito per questa variabile è che l’intero sito web client venga servito in modo sicuro (HTTPS). (AN-204604)

## Versione 2.17.0

Data di rilascio: **23 agosto 2019**

* È stato aggiunto un supporto per il riordino delle stringhe di query Baidu. (AN-182483)
* È stato corretto un errore che generava valori dei visitatori non aggiornati nei riscontri messi in coda in attesa di consenso. (AN-184391)

## Versione 2.16.0

Data di rilascio: **15 agosto 2019**

* In `sendBeacon` è stato implementato il supporto di [!UICONTROL AppMeasurement] per i collegamenti di uscita. Se un hit utilizza `sendBeacon` e la pagina viene scaricata, la richiesta viene comunque completata. Questo risulta piuttosto utile per i collegamenti di uscita perché è più probabile che l’hit raggiunga i server di raccolta dati. (AN-175142)
* I valori ECID/fid ora sono memorizzati nella cache al primo hit, anche se le impostazioni Opt-In dovessero cambiare. (AN-175142)
* Il modulo Gestione dell’audience è stato aggiornato a DIL 9.3. (AN-182704)
* È stato esposto uno switch in `s.ActivityMap.trackScrollReach` per attivare o disattivare il tracciamento della portata di scorrimento. (AN-182754)
* AppMeasurement è stato aggiornato per utilizzare il servizio ID visitatori 4.4.0. (AN-182912)

## Versione 2.15.0

Data di rilascio: **15 luglio 2019**

* Aggiunto il tracking della portata di scorrimento all’estensione di ActivityMap (AN-172949)
* Aggiunto DIL 9.2 ad AppMeasurement (AN-182472)

## Versione 2.14.0

Data di rilascio: **21 maggio 2019**

* Risolti i problemi relativi alla gestione dello stato dei parametri del tracker quando più hit sono in sospeso. (AN-176931, AN-176629, DTM-12758)
* Aggiornato AppMeasurement per includere Visitor.js 4.3.0 (AN-180049)

## Versione 2.13.0

Data di rilascio: **10 aprile 2019**

* Correzione di molti problemi segnalati con clearVars. Il problema si verifica quando gli hit vengono inviati prima che il tracciamento sia pronto. Quando il tracciamento è disponibile, la libreria può impostare le variabili che sono già state eliminate o modificate. (AN-176931, AN-176629, DTM-12758).

## Versione 2.12.0

Data di rilascio: **22 febbraio 2019**

* Il modulo Gestione dell’audience è stato aggiornato a DIL 9.1. (AN-175255)
* Il criterio di sicurezza GTM non consente l’esecuzione del modulo Activity Map. (AN-174679)
* AppMeasurement è stato migliorato per rispettare eventuali rinunce (opt-out) quando Identity Service non è approvato in consenso (opt-in). (AN-175259)

## Versione 2.11.0

Data di rilascio: **11 febbraio 2019**

* Aggiunto supporto per la nuova funzionalità servizi Opt-in di Adobe in AppMeasurement. (AN-163546)
* È stato aggiunto supporto per l’archiviazione dei dati di tracciamento dei collegamenti in memoria sessione. (AN-162272)
* Aggiunto supporto per il tipo di flusso multimediale per Audio Analytics. (AN-173265)

## Versione 2.10.0

Data di rilascio: **20 settembre 2018**

Questa versione assicura che la libreria di [!DNL AppMeasurement] esegua correttamente l’invio dei cookie per tutti i tipi di connessione.

* [!DNL AppMeasurement] blocca la trasmissione dei cookie durante richieste POST. (AN-165538)
* È stato interrotto il supporto per XDomainRequest. (AN-165733)
* In [!DNL AppMeasurement] la durata predefinita del cookie è stata ridotta da cinque a due anni. (AN-158572)
* È stato rimosso il modulo Media da Code Manager ( [!DNL AppMeasurement]) (AN-166590)

## Versione 2.9.0

Data di rilascio: **24 maggio 2018**

>[!NOTE]
>
>Per i clienti che utilizzano il servizio [!DNL Experience Cloud] ID è richiesto l’API Visitor 3.0 o versione successiva. Adobe consiglia di eseguire l’aggiornamento alla versione più recente dell’API Visitor ogni volta che le librerie di codice associate vengono aggiornate ([!DNL at.js], [!DNL AppMeasurement.js] e così via).

* Il file [!DNL AppMeasurement] è stato aggiornato in modo da utilizzare la versione aggiornata dell’interfaccia Visitor per la richiesta degli ID. (AN-151483)
* È stato corretto un problema in cui il cookie di tracciamento dei collegamenti viene scritto anche dopo la disattivazione della funzione di tracciamento dei collegamenti. (AN-156332)
* È stato risolto un problema per il quale `registerPreTrackCallback` e `registerPostTrackCallback` interrompevano la firma della funzione di callback, in caso di chiamate multiple. (AN-158566)

## Versione 2.8.2

Data di rilascio: **12 aprile 2018**

* Il file [!DNL AppMeasurement] è stato aggiornato in modo da utilizzare la versione aggiornata dell’interfaccia Visitor per la richiesta degli ID. (AN-151483)
* Il cookie di tracciamento dei collegamenti viene scritto anche dopo la disattivazione della funzione di tracciamento dei collegamenti. (AN-156332)
* In [!DNL AppMeasurement] la durata predefinita del cookie è stata ridotta da cinque a due anni. (AN-158572)

## Versione 2.8.1

Data di rilascio: **29 marzo 2018**

Nuovo bundle dell’API Visitor 3.1.0 (AN-159524), che include gli hot fix: (CORE-11390, CORE-10634)

## Versione 2.8.0

Data di rilascio: **15 marzo 2018**

Nuovo bundle dell’API Visitor 3.1.0 (AN-159524), che include gli hot fix: (CORE-11390, CORE-10634)

* Bundle VAPI v3.1 con [!DNL AppMeasurement] v2.8. (AN-158353)
* Rifattorizzare la creazione dell’endpoint per la raccolta dati in modo da facilitare la condivisione. (AN-156647)
* Aggiungi metriche di timing round trip a [!DNL AppMeasurement]. (AN-158343)

## Versione 2.7.0

Data di rilascio: **18 gennaio 2018**

* Fine del supporto per IE da 6 a 9
* Inclusione di Visitor API v3.0.0
* Inclusione di DIL v7.00

## Versione 2.6.0

Data di rilascio: **9 novembre 2017**

È stato risolto un problema dove la libreria [!DNL AppMeasurement] non imposta sempre la giusta combinazione di account quando viene chiamato s_gl. (AN-152153)

## Versione 2.5.0

Data di rilascio: **21 settembre 2017**

* Inclusione di [!DNL dil.js 6.12] (modulo [!DNL Audience Manager])
* Inclusione di API Visitor 2.5.0.

## Versione 2.4.0

Data di rilascio: **17 agosto 2017**

* Inclusa dil.js v6.11
* Inclusa API Visitor 2.4.0

## Versione 2.3.0

Data di rilascio: **20 luglio 2017**

* È stato corretto un bug in cui `s.Util.getQueryParam` acquisiva `#`
* È stata aggiunta la versione 6.10 di `dil.js` (AN-145701)

## Versione 2.2.0

Data di rilascio: **8 giugno 2017**

* È stato aggiunto il supporto per più ordini di creazione istanze [!DNL AppMeasurement]. (AN-138237)
* Inclusione dell’API Visitor versione 2.2.0. (AN-144042)

## Versione 2.1.0

Data di rilascio: **20 aprile 2017**

* Inclusa versione aggiornata di `dil.js` (AN-140396)
* Aggiunto supporto per il parametro `adobe_mc_ref` che si sovrappone al referente pagina. (AN-131920)
* API 2.1.0 visitatore nuovamente inclusa. (AN-140873)
* È stato aggiunto il parametro `mcorgid`. (AN-139586)
* Aggiunto parametro cp (customerPerspective). (AN-140897)

## Versione 2.0.0

Data di rilascio: **9 marzo 2017**

* È stato spostato a un nuovo processo di build che richiede un aggiornamento del numero di versione a 2.0.0. (AN-137878)
* È stata spostata la gestione di mboxMCSDID nella posizione della sezione corretta in cui viene effettuata la chiamata di tracciamento. (AN-138483)

## Versione 1.8.0

Data di rilascio: **19 gennaio 2017**

* Include Visitor API 2.0.0
* È stata modificata la sequenza di chiamate di funzioni e verifiche in modo che SDID viene consumato dopo il completamento della verifica di interruzione. (AN-134364)
* È stato aggiunto `s.registerPreTrackCallback` e gli hook di `s.registerPostTrackCallback`. (AN-134567)

## Versione 1.7.0

Aggiornato il **11 novembre 2016**

* Inclusa API Visitor 1.10.1.
* Aggiornamento del modulo [!DNL Audience Manager] con Demdex Integration Library (DIL) 6.6. (AN-132065)
* Inclusione di API Visitor 1.9.0. (AN-132072)
* Aggiornamento del modulo [!DNL AppMeasurement] [!DNL Audience Manager] con DIL 6.5 e configurazioni aggiuntive (AN-129411)
* Inclusione di API Visitor 1.8.0 (AN-129887)

## Versione 1.6.4

Aggiornato il **18 agosto 2016**

* Aggiornamento di [!DNL AppMeasurement] per consentire la lettura e scrittura di cookie AMCV. (AN-127098)
* Inclusione di API Visitor 1.7.0.

>[!NOTE]
>
>Consulta anche le seguenti note sulla versione per [!DNL JavaScript] versione 1.6.3, che includono i requisiti aggiornati per il servizio Experience Cloud ID.

## Versione 1.6.3

Aggiornato il **4 agosto 2016**

* È stato risolto un problema che causava la chiusura anticipata delle connessioni richieste da [!DNL AppMeasurement]. (AN-126448)

>[!IMPORTANT]
>
>La versione 1.6.0 del servizio [!DNL Experience Cloud] ID *richiede* [!DNL AppMeasurement] per [!DNL JavaScript] versione 1.6.3 o successiva. Se vuoi eseguire l’aggiornamento alla versione 1.6.0 del servizio ID di Experience Cloud, assicurati di utilizzare la versione di AppMeasurement 1.6.3 o successiva.

## Versione 1.6.2

Data di rilascio: **21 luglio 2016**

* Inclusione di API Visitor 1.6.0.
* Risolto un problema che causava la chiamata del metodo offuscato errato in API Visitor da parte di [!DNL AppMeasurement]. (AN-126006)
* Risolto un problema che causava l’errore [!DNL JavaScript]: “Attribute only valid on v:image” (Attributo valido solo in v:image). (AN-124009)

## Versione 1.6.1

Data di rilascio: **16 giugno 2016**

* Inclusione di API Visitor 1.5.7.
* Risoluzione della gestione del tracciamento del clic su collegamento in Firefox che non attivava l’evento completo.

## Versione 1.6

Data di rilascio: **21 aprile 2016**

* Il modulo Activity Map di [!DNL AppMeasurement] è stato integrato nel modulo standard [!DNL AppMeasurement], affinché tu possa fare riferimento a un solo file [!DNL .js]. Inoltre, il monitoraggio di Activity Map è attivato per impostazione predefinita. (AN-112689)
* È stato risolto un problema di troncamento che si verificava con l&#39;ordine delle variabili delle stringhe query in [!DNL AppMeasurement], così che *`pageURLRest`* risulti ultimo. (AN-114647)

## Versione 1.5.4

Data di rilascio: **17 marzo 2016**

* Inclusione di API Visitor 1.5.4
* Supporto per l’opt-out di API Visitor 1.5.4+

## Versione 1.5.3

Data di rilascio: **21 gennaio 2016**

* È stata corretta la gestione del modulo [!DNL Audience Manager] di quando i POST vengono utilizzate per il tracciamento delle chiamate. (AN-115381)
* Il resto dell’URL della pagina (&quot;-g&quot;) è stato spostato alla fine della stringa di query della richiesta di tracciamento. (AN-114647)

## Versione 1.5.2

Data di rilascio: **5 novembre 2015**

* Inclusione di API Visitor 1.5.3.
* È stato risolto il rilevamento di IE11 per il troncamento URL 2047 (AN-114914)

## Versione 1.5.1

Data di rilascio: **17 settembre 2015**

* Inclusione di API Visitor 1.5.2
* Il modulo [!DNL Audience Manager] è stato aggiornato per utilizzare Adobe Audience Manager DIL 6.2 - getCustomer ID da VisitorAPI.js e trasmetterli nella chiamata /event a Adobe Audience Manager. (AN-104978)

## Versione 1.5

Data di rilascio: **18 giugno 2015**

* Supporto per API Visitor 1.5 che utilizza il metodo *`getCustomerIDs`* per raccogliere gli ID del cliente e lo stato autenticato e invia tali ID con le richieste di raccolta dei dati.
* Risoluzione della creazione di iframe di destinazione duplicati nel modulo di **[!UICONTROL AudienceManagement]** (DIL 6.1)
* È stato risolto il problema noto descritto nella release 1.4.5.

## Versione 1.4.5

Data di rilascio: **21 maggio 2015**

* A partire dalla versione 4.5 di iOS SDK, una nuova estensione iOS consente di raccogliere i dati di utilizzo dalle app Apple Watch, dai widget Oggi, dai widget per l’editing di foto e da tutte le altre app di estensione iOS.
* A partire dalla versione 4.5 di Android SDK, una nuova estensione Android consente di raccogliere dati dall&#39;app Android Wearable.
* Inclusione di API Visitor 1.4.
* Il modulo AudienceManagement è stato aggiornato per l’utilizzo di DIL versione 6.0.

>[!NOTE]
>
>**Problema noto**: nelle integrazioni con il modulo API Visitor/ [!DNL AppMeasurement] [!DNL Audience Manager], sono disponibili due destinazioni per la pubblicazione delle richieste iFrame effettuate in IE6-9: `//fast.<subdomain>.demdex.net/dest5.html` e `//fast.<subdomain>.demdex.net/dest4.html`. Come visto negli altri browser, la procedura corretta prevede di caricare solo `//fast.<subdomain>.demdex.net/dest5.html`.

## Versione 1.4.4

Data di rilascio: **16 aprile 2015**

* Ora puoi includere variabili di dati contestuali personalizzate con le metriche del ciclo di vita.
* Le chiamate `trackBeacon` e `clearCurrentBeacon` adesso sono disponibili in PhoneGap.
* Correzione di lieve entità per cancellare l’ID del profilo di chiamata del server light dopo la chiamata `trackLight`.

## Versione 1.4.3

Data di rilascio: **19 febbraio 2015**

* Tutta la gestione delle chiamate di monitoraggio ritardate è stata resa coerente. In tal modo vengono corretti i problemi con le variabili sottoposte a backup durante il ritardo, come l’oggetto selezionato con un clic.
* È stato modificato per non effettuare in modo automatico il tracciamento del referente dopo la prima chiamata di tracciamento affinché la seconda, terza ecc. chiamata di tracciamento (solitamente tracciamento collegamenti) non conti due volte il referente quando *`s.referrer`* è stato impostato manualmente prima della prima chiamata di tracciamento.
* Lo zip di distribuzione è stato aggiornato per includere API Visitor 1.3.5.

## Versione 1.4.2

Data di rilascio: **15 gennaio 2015**

* Risoluzione della gestione del WebKit di pre-rendering per impedire il tracciamento di pagine sottoposte a pre rendering che non vengono visualizzate.
* Lo zip di distribuzione è stato aggiornato per includere API Visitor 1.3.4., aggiungendo un modulo aggiornato di **[!UICONTROL AudienceManagement]** che include la versione 5.5 di DIL.

## Versione 1.4.1

Data di rilascio: **18 settembre 2014**

* Aggiunta di una variabile `tagContainerMarker` che consente l’implementazione per specificare fino a 4 caratteri da aggiungere alla stringa della versione con un delimitatore di caratteri in forma di trattino. La variabile viene utilizzata per la gestione dinamica dei tag.

  ```js
  // JavaScript
  s.tagContainerMarker = "D1.0";
  
  // Data Collection request
  //.../b/ss/myrsid/1/JS-1.4.1-D1.0/s43317392037311?...
  ```

  È possibile utilizzare 4 caratteri consentiti in percorsi di file URL, ad esempio caratteri alfanumerici e punto.

* Correzione di un loop che potrebbe verificarsi durante il monitoraggio automatico dei collegamenti (download e uscita) con monitoraggio forzato dei collegamenti abilitato (impostazione predefinita in browser WebKit) in pagine con doppio tag e codice H. Per evitare tali loop, è stata inoltre aggiunta una protezione automatica generale per il monitoraggio automatico dei collegamenti. Questa protezione limita il monitoraggio automatico dei collegamenti di clic ripetuti sullo *stesso* oggetto a una volta ogni 10 secondi. La protezione si applica solo al monitoraggio automatico dei collegamenti, le chiamate al monitoraggio manuale dei collegamenti (s. tl) non sono limitate. La protezione non viene applicata a clic su oggetti diversi, che vengono invece monitorati.
* Correzione relativa alla gestione di elementi oggetti di clic in caso sia necessario applicare un ritardo.
* Risoluzione del problema che causava un doppio conteggio pagina-vista in caso di chiamata a s.tl da una funzione di collegamento OnClick, nel caso in cui l’API Visitor non contenesse ancora i valori necessari.
* Supporto HTTP POST.

  >[!IMPORTANT]
  >
  >Affinché una chiamata [!DNL Analytics] possa utilizzare il metodo POST invece del metodo GET in [!DNL AppMeasurement] (un metodo per risolvere gli [URL troncati](https://helpx.adobe.com/it/analytics/kb/shortening-image-request-urls.html) in IE), devi usare l’implementazione più recente del servizio ID visitatori per Experience Cloud.

## Versione 1.4

Data di rilascio: **21 agosto 2014**

* Rimosso il tracciamento dei plug-in del browser (parametro query `p`) poiché i plug-in non sono più segnalati nella versione 15.
* Aggiunta del modulo **[!UICONTROL AudienceManagement]** nello zip di download.
* È stato aggiunto il supporto per eVar (76 - 250) ed eventi aggiuntivi (101-1000).

>[!NOTE]
>
>H-Code non supporta eVar ed eventi aggiuntivi.

## Versione 1.3.2

Data di rilascio: **19 giugno 2014**

* È stata corretta la gestione dei flag di attesa e di fine per i campi di API Visitor, come l’ID visitatore legacy [!DNL Analytics], che causava errori.
* Supporto delle nuove funzioni del servizio ID visitatore 1.3.

## Versione 1.3.1

Data di rilascio: **22 maggio 2014**

* La funzione [!DNL AppMeasurement] per [!DNL JavaScript] `s_gi` non stava trovando correttamente le istanze create utilizzando codice H `s_gi`. Questo problema ha interessato solo alcune implementazioni di doppio tag in cui [!DNL AppMeasurement] per [!DNL JavaScript] e codice H si trovavano sulla stessa pagina con istanze separate e `s_gi` veniva utilizzato per trovare le istanze per suite di report.

## Versione 1.3

Data di rilascio: **17 aprile 2014**

* Supporto per il servizio [ID visitatore di Experience Cloud](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Versione 1.2.4

Data di rilascio: **13 marzo 2014**

* Correzioni di bug per i video heartbeat.

## Versione 1.2.3

Data di rilascio: **20 febbraio 2014**

* Correzioni di bug per i video heartbeat.

## Versione 1.2.2

Data di rilascio:**6 febbraio 2014**

* È stato risolto un problema di compatibilità con il modulo DIL di [!DNL Audience Manager]. I clienti [!DNL Audience Manager] devono anche eseguire l’aggiornamento alla versione 4.8 del modulo DIL.

## Versione 1.2.1

Data di rilascio: **15 novembre 2013**

* Sono stati corretti gli eventi di pagina utilizzati per la misurazione video Heartbeat.

## Versione 1.2

Data di rilascio: **14 novembre 2013**

* È stato aggiunto il supporto per la misurazione video [Heartbeat](https://experienceleague.adobe.com/docs/media-analytics/using/media-overview.html?lang=it).
* È stato aggiunto `VisitorAPI.js` per il supporto del [servizio ID visitatori](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=it).

## Versione 1.1.1

* È stato impedito l’invio di una chiamata di tracciamento dei collegamenti dai browser Opera per i collegamenti che iniziano con “opera:” (“opera:” è simile ad “about:” e “chrome:” negli altri browser).
* `alt=""` è stato aggiunto a tutti gli oggetti Immagine per conformarsi alla legge Accessible Video and Communications Act.

## Versione 1.1

Data di rilascio: **18 settembre 2013**

* È stato corretto il supporto per il posizionamento della libreria e del codice della pagina nel tag `head`.
* È stato aggiunto il supporto del modulo mancante `onLoad`.

## Versione 1.0.3

Data di rilascio: **15 agosto 2013**

* È stato aggiunto il supporto per la distribuzione tramite la gestione dei tag Adobe.
* È stato risolto un problema che impediva l’impostazione di variabili gerarchiche sull’oggetto [!DNL AppMeasurement].

## Versione 1.0.2

Data di rilascio:**18 luglio 2013**

* L’hash/frammento ora viene ignorato dal tracciamento automatico dei collegamenti. In precedenza veniva tracciato automaticamente il seguente URL, dal momento che l’intero `href` terminava con `.pdf`:

  ```js
  <a href="index.htm#anchor.pdf">Test Link</a>
  ```

  Ora l’hash o il frammento viene ignorato e il collegamento viene tracciato solo quando il nome del file termina con un’estensione corrispondente.

## Versione 1.0.1

Data di rilascio: **23 maggio 2013**

In Code Manager è ora disponibile una nuova libreria [!DNL JavaScript] [!DNL AppMeasurement]. Questa libreria offre le stesse funzionalità di base di [!DNL s_code.js], ma è più leggera e veloce da utilizzare sia sui siti mobili che su quelli desktop.

* 3-7 volte più veloce del codice H.25.
* Solo 21.000 non compressi e 8.000 in formato gzip (il codice H.25 corrisponde a una dimensione non compressa di 33.000 e di 13.000 in formato gzip).
* Supporto nativo per ottenere parametri di query, cookie di lettura e scrittura e per l’esecuzione del tracciamento avanzato dei collegamenti.
* Abbastanza piccolo e veloce da poter essere utilizzato con i siti mobili e sufficientemente robusto da essere usato nell’intero web desktop, per sfruttare una singola libreria in tutti gli ambienti web.
