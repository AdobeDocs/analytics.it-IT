---
title: Compatibilità delle dimensioni di Analytics
description: Riferimento per dimensioni e rapporti di Analytics.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: 7609ecb3c34fb0bc8293fc1ecd409cfabb327295
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 19%

---

# Compatibilità delle dimensioni di Analytics

In questa pagina sono elencate le [dimensioni](overview.md) supportate nelle rispettive funzionalità di Analytics.

>[!NOTE]
>
>I nomi delle variabili, le classificazioni e gli attributi dei visitatori personalizzati vengono omessi da questo elenco. Questi elementi dimensionali sono specifici per le singole suite di rapporti.

## Dimensioni supportate in Analysis Workspace

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|---|---|
| Analytics for Target | `targetraw` |
| ID tipi di pubblico | `mcaudiences` |
| [Browser](browser.md) | `browser` |
| [Tipo di browser](browser-type.md) | `browsertype` |
| [Categoria](category.md) | `category` |
| [Città](cities.md) | `geocity` |
| [Profondità colore](color-depth.md) | `colordepth` |
| [Tipo connessione](connection-type.md) | `connectiontype` |
| [Supporto per cookie](cookie-support.md) | `cookie` |
| [Paesi](countries.md) | `geocountry` |
| [Fedeltà cliente](customer-loyalty.md) | `customerloyalty` |
| [Variabili di conversione personalizzate](evar.md) | `evar1`, `evar2`, ecc. |
| [Variabili Custom Insight](prop.md) | `prop1`, `prop2`, ecc. |
| [Collegamento personalizzato](custom-link.md) | `customlink` |
| [Giorni precedenti al primo acquisto](days-before-first-purchase.md) | `daysbeforefirstpurchase` |
| [Giorni dall&#39;ultimo acquisto](days-since-last-purchase.md) | `dayssincelastpurchase` |
| [Dominio](domain.md) | `filtereddomain` |
| [Collegamento di download](download-link.md) | `downloadlink` |
| [Pagina di ingresso](entry-dimensions.md) | `entrypage` |
| [Pagina di ingresso originale](entry-dimensions.md) | `entrypageoriginal` |
| [Collegamento di uscita](exit-link.md) | `exitlink` |
| [Canale primo contatto](first-touch-channel.md) | `firsttouchchannel` |
| [Dettagli canale di primo contatto](first-touch-detail.md) | `firsttouchchanneldetail` |
| [Java abilitato](java-enabled.md) | `javaenabled` |
| [Lingua](language.md) | `language` |
| [Canale ultimo contatto](last-touch-channel.md) | `lasttouchchannel` |
| [Dettaglio canale ultimo contatto](last-touch-detail.md) | `lasttouchchanneldetail` |
| Variabili elenco | `listvariables` |
| [Canale di marketing](marketing-channel.md) | `marketingchannel` |
| [Supporto audio mobile](mobile-dimensions.md) | `mobileaudiosupport` |
| [Gestore di telefonia mobile](mobile-dimensions.md) | `mobilecarrier` |
| [Profondità colore mobile](mobile-dimensions.md) | `mobilecolordepth` |
| [Supporto per cookie mobile](mobile-dimensions.md) | `mobilecookiesupport` |
| [Dispositivo mobile](mobile-dimensions.md) | `mobiledevicename` |
| [Tipo di dispositivo mobile](mobile-dimensions.md) | `mobiledevicetype` |
| [Lunghezza massima e-mail mobile](mobile-dimensions.md) | `mobileemaillength` |
| [Supporto immagini per dispositivi mobili](mobile-dimensions.md) | `mobileimagesupport` |
| [Produttore di dispositivi mobili](mobile-dimensions.md) | `mobilemanufacturer` |
| [Sistema operativo mobile (obsoleto)](mobile-dimensions.md) | `mobileos` |
| [Altezza schermo mobile](mobile-dimensions.md) | `mobilescreenheight` |
| [Dimensioni schermo dispositivo mobile](mobile-dimensions.md) | `mobilescreensize` |
| [Larghezza schermo mobile](mobile-dimensions.md) | `mobilescreenwidth` |
| [Lunghezza massima URL browser mobile](mobile-dimensions.md) | `mobileurllength` |
| [Supporto video mobile](mobile-dimensions.md) | `mobilevideosupport` |
| [Risoluzione monitor](monitor-resolution.md) | `monitorresolution` |
| [Sistemi operativi](operating-systems.md) | `operatingsystem` |
| [Dominio di riferimento originale](original-referring-domain.md) | `referringdomainoriginal` |
| [Pagina](page.md) | `page` |
| [Pagine non trovate](pages-not-found.md) | `pagesnotfound` |
| [Prodotto](product.md) | `product` |
| [Referrer](referrer.md) | `referrer` |
| [Tipo di riferimento](referrer-type.md) | `referrertype` |
| [Dominio di riferimento](referring-domain.md) | `referringdomain` |
| [Aree geografiche](regions.md) | `georegion` |
| [Restituisci frequenza](return-frequency.md) | `returnfrequency` |
| SC-TnT | `tntbase` |
| [Motore di ricerca](search-engine.md) | `searchengine` |
| [Parola chiave di ricerca](search-keyword.md) | `searchenginekeyword` |
| [Motore di ricerca - Naturale](search-engine.md) | `searchenginenatural` |
| [Motore di ricerca - Pagato](search-engine.md) | `searchenginepaid` |
| [Parola chiave di ricerca - Naturale](search-keyword.md) | `searchenginenaturalkeyword` |
| [Parola chiave di ricerca - Pagato](search-keyword.md) | `searchenginepaidkeyword` |
| [Classificazione di tutte le pagine di ricerca](all-search-page-rank.md) | `searchenginepagerank` |
| [Server](server.md) | `server` |
| [Visite a pagina singola](single-page-visits.md) | `singlepagevisits` |
| [Sezione sito](site-section.md) | `sitesections` |
| [Tempo trascorso per visita - Granulare](time-spent-per-visit.md) | `sitetime` |
| [Codice di tracciamento](tracking-code.md) | `campaign` |
| [DMA Stati Uniti](us-dma.md) | `geodma` |
| [Stati Uniti](us-states.md) | `state` |
| [Tempo precedente all&#39;evento](time-prior-to-event.md) | `timeprior` |
| [Tempo trascorso per visita - Bucket](time-spent-per-visit.md) | `timespent` |
| [Profondità visita](visit-depth.md) | `pathlength` |
| [Numero visita](visit-number.md) | `visitnumber` |
| [Codice postale](zip-code.md) | `zip` |
| [AM / PM](am-pm.md) | `timepartampm` |
| [Altezza browser - Bucket](browser-height.md) | `browserheightbucketed` |
| [Larghezza browser - Bucket](browser-width.md) | `browserwidthbucketed` |
| [Giorno](day.md) | `daterangeday` |
| [Giorno del mese](day-of-month.md) | `timepartdayofmonth` |
| [Giorno della settimana](day-of-week.md) | `dayofweek` |
| [Giorno della settimana](day-of-week.md) | `timepartdayofweek` |
| [Giorno dell&#39;anno](day-of-year.md) | `timepartdayofyear` |
| [Giorni dall&#39;ultima visita](days-since-last-visit.md) | `dayssincelastvisit` |
| [Registrazioni personalizzate](entry-dimensions.md) | `entryprops` |
| [Variabili elenco voci](entry-dimensions.md) | `entrylistvariables` |
| [Server di ingresso](entry-dimensions.md) | `entryserver` |
| [Sezione sito di ingresso](entry-dimensions.md) | `entrysitesections` |
| [Esci da Approfondimenti personalizzati](exit-dimensions.md) | `exitprops` |
| [Esci da variabili elenco](exit-dimensions.md) | `exitlistvariables` |
| [Esci da pagina](exit-dimensions.md) | `exitpage` |
| [Esci dal server](exit-dimensions.md) | `exitserver` |
| [Esci da sezione sito](exit-dimensions.md) | `exitsitesections` |
| [Profondità di hit](hit-depth.md) | `hitdepth` |
| [Tipo di occorrenza](hit-type.md) | `hittype` |
| [Ora](hour.md) | `daterangehour` |
| [Ora del giorno](hour-of-day.md) | `timeparthourofday` |
| [Dettagli canale di marketing](marketing-detail.md) | `marketingchanneldetail` |
| [Minuto](minute.md) | `daterangeminute` |
| [Lunghezza massima segnalibro mobile](mobile-dimensions.md) | `mobilebookmarklength` |
| [Numero dispositivo mobile](mobile-dimensions.md) | `mobiledevicenumber` |
| [DRM mobile](mobile-dimensions.md) | `mobiledrm` |
| [Mobile Information Services](mobile-dimensions.md) | `mobileinformationservices` |
| [Macchina virtuale Java mobile](mobile-dimensions.md) | `mobilejavavm` |
| [Decorazione posta mobile](mobile-dimensions.md) | `mobilemaildecoration` |
| [Protocolli di rete mobile](mobile-dimensions.md) | `mobilenetprotocols` |
| [Push Mobile A Talk](mobile-dimensions.md) | `mobilepushtotalk` |
| [Mese](month.md) | `daterangemonth` |
| [Mese dell&#39;anno](month-of-year.md) | `timepartmonthofyear` |
| [Tipi di sistemi operativi](operating-system-types.md) | `operatingsystemgroup` |
| [Ricerca a pagamento](paid-search.md) | `paidsearch` |
| [Supporto per cookie persistenti](persistent-cookie-support.md) | `persistentcookie` |
| [Trimestre](quarter.md) | `daterangequarter` |
| [Trimestre dell&#39;anno](quarter-of-year.md) | `timepartquarterofyear` |
| Sondaggio | `surveybase` |
| [Tempo trascorso sulla pagina - Bucket](time-spent-on-page.md) | `averagepagetime` |
| [Tempo trascorso sulla pagina - Granulare](time-spent-on-page.md) | `pagetimeseconds` |
| [Tracking del motivo di rinuncia](tracking-opt-out-reason.md) | `optoutreason` |
| [Giorno feriale / Fine settimana](weekday-weekend.md) | `timepartweekdayweekend` |
| [Settimana](week.md) | `daterangeweek` |
| [Anno](year.md) | `daterangeyear` |

## Dimensioni in base al contenuto supportate solo in Analysis Workspace

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| ACTIVITY MAP XY | `clickmapxy` |
| ID sessione multimediale | `videosessionid` |
| Metodo di accesso Nielsen | `nielsenaccmethod` |
| ID app Nielsen | `nielsenappid` |
| Risorsa di canale Nielsen | `nielsenchannelasset` |
| Tipo di contenuto Nielsen | `nielsencontenttype` |

## Dimensioni in base al contenuto supportate da Analysis Workspace

### Video (servizi multimediali in streaming)

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| [Contenuto](sm-core.md) | `video` |
| [Segmento di contenuto](sm-core.md) | `videosegment` |
| [Tipo di contenuto](sm-core.md) | `videocontenttype` |
| [Nome Lettore Annuncio](sm-ads.md) | `videoadplayername` |
| [Annuncio in posizione pod](sm-ads.md) | `videoadinpod` |
| [Frame rilasciati](sm-quality.md) | `videoqoedroppedframecountevar` |
| [Errori](sm-quality.md) | `videoqoeerrorcountevar` |
| [Bitrate medio](sm-quality.md) | `videoqoebitrateaverageevar` |
| [Modifiche bitrate](sm-quality.md) | `videoqoebitratechangecountevar` |
| [Durata totale buffer](sm-quality.md) | `videoqoebuffertimeevar` |
| [Eventi buffer](sm-quality.md) | `videoqoebuffercountevar` |
| [Ora di inizio](sm-quality.md) | `videoqoetimetostartevar` |
| [Pod annuncio](sm-ads.md) | `videoadpod` |
| [Percorso file multimediale](sm-core.md) | `videopath` |
| [Annuncio](sm-ads.md) | `videoad` |
| [Nome lettore contenuti](sm-core.md) | `videoplayername` |
| [Canale contenuto](sm-core.md) | `videochannel` |
| [Capitolo](sm-chapters.md) | `videochapter` |
| [Nome contenuto (variabile)](sm-core.md) | `videoname` |
| [Lunghezza contenuto (variabile)](sm-core.md) | `videolength` |
| [Nome annuncio (variabile)](sm-ads.md) | `videoadname` |
| [Lunghezza annuncio (variabile)](sm-ads.md) | `videoadlength` |
| [Mostra](sm-video-metadata.md) | `videoshow` |
| [Stagione](sm-video-metadata.md) | `videoseason` |
| [Episodio](sm-video-metadata.md) | `videoepisode` |
| [Rete](sm-video-metadata.md) | `videonetwork` |
| [Mostra tipo](sm-video-metadata.md) | `videoshowtype` |
| [Caricamenti annuncio](sm-ads.md) | `videoadload` |
| [MVPD](sm-video-metadata.md) | `videomvpd` |
| [Fascia oraria](sm-video-metadata.md) | `videodaypart` |
| [Inserzionista](sm-ads.md) | `videoadadvertiser` |
| [ID campagna](sm-ads.md) | `videoadcampaign` |
| [Genere](sm-video-metadata.md) | `videogenre` |
| [Tipo di flusso](sm-core.md) | `videostreamtype` |
| [ID errore SDK del lettore](sm-quality.md) | `videoqoeplayersdkerrors` |
| [ID errore esterni](sm-quality.md) | `videoqoeextneralerrors` |
| [Tipo di feed multimediale](sm-video-metadata.md) | `videofeedtype` |
| [Percorso supporto di ingresso](entry-dimensions.md) | `entryvideopath` |
| [Esci dal percorso file multimediale](exit-dimensions.md) | `exitvideopath` |
| [Genere voce](entry-dimensions.md) | `entryvideogenre` |
| [Esci da genere](exit-dimensions.md) | `exitvideogenre` |
| [ID errore SDK lettore di ingresso](entry-dimensions.md) | `entryvideoqoeplayersdkerrors` |
| [ID errore uscita SDK lettore](exit-dimensions.md) | `exitvideoqoeplayersdkerrors` |
| [ID errore esterni voce](entry-dimensions.md) | `entryvideoqoeextneralerrors` |
| [Esci da ID errore esterni](exit-dimensions.md) | `exitvideoqoeextneralerrors` |

### Adobe Social

Adobe Social è ritirato.

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| Termini | `socialterm` |
| Piattaforme/proprietà social | `socialcontentprovider` |
| Autori | `socialauthor` |
| Lingua | `sociallanguage` |
| Latitudine/Longitudine | `sociallatlong` |
| Codici di tracciamento delle risorse | `socialassettrackingcode` |
| Proprietà social possedute | `socialaccountandappids` |
| ID dei post di proprietà | `socialownedpostids` |
| Definizioni social di proprietà | `socialinteractiontype` |
| ID proprietà possedute | `socialownedpropertyid` |
| Proprietà di proprietà e applicazione | `socialownedpropertypropertyvsapp` |
| Nome proprietà di proprietà | `socialownedpropertyname` |
| Proprietà definizione di proprietà e post | `socialowneddefinitionpropertyvspost` |
| Tipo Insight di definizione di proprietà | `socialowneddefinitioninsighttype` |
| Valore Insight della definizione di proprietà | `socialowneddefinitioninsightvalue` |
| Metrica di definizione di proprietà | `socialowneddefinitionmetric` |
| Risorsa | `socialmediaid` |

### Mobile SDK

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| [Data primo avvio](lifecycle-dimensions.md) | `mobileinstalldate` |
| [ID app](lifecycle-dimensions.md) | `mobileappid` |
| [Numero di avvii](lifecycle-dimensions.md) | `mobilelaunchnumber` |
| [Giorni dal primo utilizzo](lifecycle-dimensions.md) | `mobiledayssincefirstuse` |
| [Giorni dall’ultimo utilizzo](lifecycle-dimensions.md) | `mobiledayssincelastuse` |
| [Ora del giorno (SDK)](lifecycle-dimensions.md) | `mobilehourofday` |
| [Giorno della settimana (SDK)](lifecycle-dimensions.md) | `mobiledayofweek` |
| [Sistema operativo (SDK)](lifecycle-dimensions.md) | `mobileosenvironment` |
| [Giorni dall’ultimo aggiornamento](lifecycle-dimensions.md) | `mobiledayssincelastupgrade` |
| [Avvii dall’ultimo aggiornamento](lifecycle-dimensions.md) | `mobilelaunchessincelastupgrade` |
| [Nome dispositivo (SDK)](lifecycle-dimensions.md) | `mobiledevice` |
| [Versione sistema operativo (SDK)](lifecycle-dimensions.md) | `mobileosversion` |
| [Beacon principale](lifecycle-dimensions.md) | `mobilebeaconmajor` |
| [Beacon secondario](lifecycle-dimensions.md) | `mobilebeaconminor` |
| [UUID beacon](lifecycle-dimensions.md) | `mobilebeaconuuid` |
| [Prossimità beacon](lifecycle-dimensions.md) | `mobilebeaconproximity` |
| [Posizione (fino a 10 chilometri)](lifecycle-dimensions.md) | `latlon1` |
| [Posizione (fino a 100 m)](lifecycle-dimensions.md) | `latlon23` |
| [Posizione (fino a 1 m)](lifecycle-dimensions.md) | `latlon45` |
| [Nome del punto di interesse](lifecycle-dimensions.md) | `pointofinterest` |
| [Distanza dal centro del punto di interesse](lifecycle-dimensions.md) | `pointofinterestdistance` |
| [Precisione posizione](lifecycle-dimensions.md) | `mobileplaceaccuracy` |
| [Categoria luogo](lifecycle-dimensions.md) | `mobileplacecategory` |
| [ID luogo](lifecycle-dimensions.md) | `mobileplaceid` |
| [Beacon di ingresso principale](lifecycle-dimensions.md) | `entrymobilebeaconmajor` |
| [Esci da beacon principale](lifecycle-dimensions.md) | `exitmobilebeaconmajor` |
| [Beacon di ingresso secondario](lifecycle-dimensions.md) | `entrymobilebeaconminor` |
| [Esci da beacon secondario](lifecycle-dimensions.md) | `exitmobilebeaconminor` |
| [UUID beacon di ingresso](lifecycle-dimensions.md) | `entrymobilebeaconuuid` |
| [UUID beacon di uscita](lifecycle-dimensions.md) | `exitmobilebeaconuuid` |
| [Prossimità beacon di ingresso](lifecycle-dimensions.md) | `entrymobilebeaconproximity` |
| [Prossimità beacon di uscita](lifecycle-dimensions.md) | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| ID AMO EF | `amo_ef_id` |
| ID AMO | `amo_cid` |

### Activity Map

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| [Collegamento Activity Map Per Regione](activity-map-link-by-region.md) | `clickmaplinkbyregion` |
| [Area geografica Activity Map](activity-map-region.md) | `clickmapregion` |
| [Collegamento Activity Map](activity-map-link.md) | `clickmaplink` |
| [Pagina Activity Map](activity-map-page.md) | `clickmappage` |

### Integrazione Nielsen

Per ulteriori informazioni su come implementare questa integrazione, consulta l&#39;estensione [Nielsen](https://exchange.adobe.com/apps/ec/101361) su Adobe Exchange.

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| Modello annuncio Nielsen | `nielsenadmodel` |
| Nielsen, segmento C | `nielsensegmentc` |
| Nielsen, segmento B | `nielsensegmentb` |
| Nielsen, segmento A | `nielsensegmenta` |
| ID contenuto Nielsen | `nielsencontentid` |
| Risorsa/Programma Nielsen | `nielsenasset` |
| Nielsen VCID | `nielsenvcid` |
| Rinuncia di Nielsen | `nielsenoptout` |
| ID client Nielsen + VCID | `nielsenclientidvcid` |
| ID client Nielsen | `nielsenclientid` |
| Voce Nielsen - Rinuncia | `entrynielsenoptout` |
| Esci da Nielsen Opt Out | `exitnielsenoptout` |
| ID client Nielsen entry + VCID | `entrynielsenclientidvcid` |
| Esci da Nielsen Client ID + VCID | `exitnielsenclientidvcid` |
| ID client Nielsen voce | `entrynielsenclientid` |
| Esci da Nielsen Client ID | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| ID risorsa | `aemassetid` |
| Origine risorsa | `aemassetsource` |
| ID risorsa selezionata | `aemclickedassetid` |
| ID risorsa di ingresso | `entryaemassetid` |
| Esci da ID risorsa | `exitaemassetid` |

### Adobe Campaign

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | Dimension ID (utilizzato nelle richieste API) |
|--- |--- |
| ID consegna eseguita di Adobe Campaign | `ac_delivery_internal_name` |
