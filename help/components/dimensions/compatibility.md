---
title: Compatibilità Dimension di Analytics
description: Riferimento per dimensioni e rapporti di Analytics.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 26%

---

# Compatibilità Dimension di Analytics

Questa pagina elenca le dimensioni supportate nelle rispettive funzionalità di Analytics.

>[!NOTE]
>
>I nomi delle variabili personalizzate, le classificazioni e gli attributi dei visitatori vengono omessi da questo elenco. Questi elementi dimensionali sono specifici delle singole suite di rapporti.

>[!NOTE]
>
>Ci sono alcune sovrapposizioni in cui gli strumenti di Analytics utilizzano termini diversi per dimensioni simili. Ad esempio, Reports &amp; Analytics utilizza `browserwidth` mentre Analysis Workspace utilizza `browserwidthbucketed`.

## Dimension supportati sia in Reports &amp; Analytics che in Analysis Workspace

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|---|---|
| Analytics for Target | `targetraw` |
| ID pubblico | `mcaudiences` |
| Browser | `browser` |
| Tipo di browser | `browsertype` |
| Categoria | `category` |
| Città | `geocity` |
| Profondità colore | `colordepth` |
| Tipo connessione | `connectiontype` |
| Supporto per cookie | `cookie` |
| Paesi | `geocountry` |
| Fedeltà cliente | `customerloyalty` |
| Variabili di conversione personalizzate | `evar1`, `evar2`, ecc. |
| Var Custom Insight | `prop1`, `prop2`, ecc. |
| Collegamento personalizzato | `customlink` |
| Giorni precedenti al primo acquisto | `daysbeforefirstpurchase` |
| Giorni dall&#39;ultimo acquisto | `dayssincelastpurchase` |
| Dominio | `filtereddomain` |
| Collegamento di download. | `downloadlink` |
| Pagina di ingresso | `entrypage` |
| Pagina di ingresso originale | `entrypageoriginal` |
| Collegamento di uscita. | `exitlink` |
| Canale primo contatto | `firsttouchchannel` |
| Dettaglio del canale di primo contatto | `firsttouchchanneldetail` |
| Java abilitato | `javaenabled` |
| Lingua | `language` |
| Canale ultimo contatto | `lasttouchchannel` |
| Dettaglio canale ultimo contatto | `lasttouchchanneldetail` |
| Variabili elenco | `listvariables` |
| Canale di marketing | `marketingchannel` |
| Supporto audio per dispositivi mobili | `mobileaudiosupport` |
| Gestore di telefonia mobile | `mobilecarrier` |
| Profondità colore mobile | `mobilecolordepth` |
| Supporto per cookie per dispositivi mobili | `mobilecookiesupport` |
| Dispositivo mobile | `mobiledevicename` |
| Tipo di dispositivo mobile | `mobiledevicetype` |
| Lunghezza massima e-mail mobile | `mobileemaillength` |
| Supporto immagini per dispositivi mobili | `mobileimagesupport` |
| Produttore di dispositivi mobili | `mobilemanufacturer` |
| Sistema operativo mobile (obsoleto) | `mobileos` |
| Altezza schermo mobile | `mobilescreenheight` |
| Dimensioni dello schermo del dispositivo mobile | `mobilescreensize` |
| Larghezza schermo mobile | `mobilescreenwidth` |
| Lunghezza massima URL browser mobile | `mobileurllength` |
| Supporto video mobile | `mobilevideosupport` |
| Risoluzione monitor | `monitorresolution` |
| Sistemi operativi | `operatingsystem` |
| Dominio di riferimento originale | `referringdomainoriginal` |
| Pagina | `page` |
| Pagine non trovate | `pagesnotfound` |
| Prodotto | `product` |
| Referrer | `referrer` |
| Tipo di riferimento | `referrertype` |
| Dominio di riferimento | `referringdomain` |
| Aree geografiche | `georegion` |
| Frequenza di ritorno | `returnfrequency` |
| SC-TnT | `tntbase` |
| Motore di ricerca | `searchengine` |
| Parola chiave di ricerca | `searchenginekeyword` |
| Motore di ricerca - Naturale | `searchenginenatural` |
| Motore di ricerca - Pagato | `searchenginepaid` |
| Parola chiave di ricerca - Naturale | `searchenginenaturalkeyword` |
| Parola chiave di ricerca - Pagato | `searchenginepaidkeyword` |
| Classificazione di tutte le pagine di ricerca | `searchenginepagerank` |
| Server | `server` |
| Visite a pagina singola | `singlepagevisits` |
| Sezione del sito | `sitesections` |
| Tempo trascorso per visita - Granulare | `sitetime` |
| Codice di tracciamento | `campaign` |
| DMA Stati Uniti | `geodma` |
| Stati degli Stati Uniti | `state` |
| Tempo precedente all’evento | `timeprior` |
| Tempo trascorso per ciascuna visita - Bucket | `timespent` |
| Profondità della visita | `pathlength` |
| Numero di visite | `visitnumber` |
| Codice postale | `zip` |

## Dimension supportati solo in Analysis Workspace

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| AM/PM | `timepartampm` |
| Altezza browser - Bucket | `browserheightbucketed` |
| Larghezza browser - Bucket | `browserwidthbucketed` |
| Giorno | `daterangeday` |
| Giorno del mese | `timepartdayofmonth` |
| Giorno della settimana | `dayofweek` |
| Giorno della settimana | `timepartdayofweek` |
| Giorno dell’anno | `timepartdayofyear` |
| Giorni dall&#39;ultima visita | `dayssincelastvisit` |
| Approfondimenti personalizzati voce | `entryprops` |
| Variabili elenco voci | `entrylistvariables` |
| Server di ingresso | `entryserver` |
| Sezione sito di ingresso | `entrysitesections` |
| Esci da approfondimenti personalizzati | `exitprops` |
| Variabili elenco di uscita | `exitlistvariables` |
| Pagina di uscita | `exitpage` |
| Esci dal server | `exitserver` |
| Esci dalla sezione del sito | `exitsitesections` |
| Profondità di hit | `hitdepth` |
| Tipo di hit | `hittype` |
| Ora | `daterangehour` |
| Ora del giorno | `timeparthourofday` |
| Dettaglio del canale di marketing | `marketingchanneldetail` |
| Minuto | `daterangeminute` |
| Lunghezza massima segnalibro mobile | `mobilebookmarklength` |
| Numero dispositivo mobile | `mobiledevicenumber` |
| DRM mobile | `mobiledrm` |
| Mobile Information Services | `mobileinformationservices` |
| Java VM mobile | `mobilejavavm` |
| Decoration Mail mobile | `mobilemaildecoration` |
| Protocolli di rete per dispositivi mobili | `mobilenetprotocols` |
| Push-to-talk per dispositivi mobili | `mobilepushtotalk` |
| Mese | `daterangemonth` |
| Mese dell’anno | `timepartmonthofyear` |
| Tipi di sistemi operativi | `operatingsystemgroup` |
| Ricerca a pagamento | `paidsearch` |
| Supporto per cookie persistenti | `persistentcookie` |
| Trimestre | `daterangequarter` |
| Trimestre dell’anno | `timepartquarterofyear` |
| Sondaggio | `surveybase` |
| Tempo trascorso sulla pagina - Bucket | `averagepagetime` |
| Tempo trascorso sulla pagina - Granulare | `pagetimeseconds` |
| Tracking del motivo di rinuncia | `optoutreason` |
| Giorno feriale/Fine settimana | `timepartweekdayweekend` |
| Settimana | `daterangeweek` |
| Anno | `daterangeyear` |

## Dimensioni in base al contenuto supportate solo in Analysis Workspace

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Activity Map XY | `clickmapxy` |
| ID sessione multimediale | `videosessionid` |
| Metodo di accesso Nielsen | `nielsenaccmethod` |
| ID app Nielsen | `nielsenappid` |
| Risorsa canale Nielsen | `nielsenchannelasset` |
| Tipo di contenuto Nielsen | `nielsencontenttype` |

## Dimension supportati solo in Reports &amp; Analytics

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Altezza browser | `browserheight` |
| Larghezza browser | `browserwidth` |
| Clienti univoci giornalieri | `dailyuniquecustomers` |
| JavaScript | `javascriptsupport` |
| JavaScript versione | `javascriptversion` |
| Clienti univoci mensili | `monthlyuniquecustomers` |
| Clienti univoci trimestrali | `quarterlyuniquecustomers` |
| Fusi orari | `timezone` |
| Domini di livello principali | `topleveldomain` |
| Stato visitatore | `legacystate` |
| Clienti univoci settimanali | `weeklyuniquecustomers` |
| Clienti univoci annuali | `yearlyuniquecustomers` |

## Dimensioni in base al contenuto supportate da Reports &amp; Analytics e Analysis Workspace

### Video (Media Analytics)

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Contenuto | `video` |
| Segmento di contenuto | `videosegment` |
| Tipo di contenuto | `videocontenttype` |
| Nome del lettore pubblicitario | `videoadplayername` |
| Aggiungi in posizione contenitore | `videoadinpod` |
| Frame rilasciati | `videoqoedroppedframecountevar` |
| Errori | `videoqoeerrorcountevar` |
| Bitrate medio | `videoqoebitrateaverageevar` |
| Modifiche bitrate | `videoqoebitratechangecountevar` |
| Durata totale buffer | `videoqoebuffertimeevar` |
| Eventi buffer | `videoqoebuffercountevar` |
| Ora di inizio | `videoqoetimetostartevar` |
| Ad Pod | `videoadpod` |
| Percorso multimediale | `videopath` |
| Annuncio | `videoad` |
| Nome del lettore di contenuti | `videoplayername` |
| Canale del contenuto | `videochannel` |
| Capitolo | `videochapter` |
| Nome contenuto (variabile) | `videoname` |
| Lunghezza del contenuto (variabile) | `videolength` |
| Nome annuncio (variabile) | `videoadname` |
| Lunghezza annuncio (variabile) | `videoadlength` |
| Mostra le informazioni | `videoshow` |
| Stagione | `videoseason` |
| Episodio | `videoepisode` |
| Rete  | `videonetwork` |
| Mostra tipo | `videoshowtype` |
| Caricamenti annunci | `videoadload` |
| MVPD | `videomvpd` |
| Parte giorno | `videodaypart` |
| Inserzionista | `videoadadvertiser` |
| ID campagna | `videoadcampaign` |
| Genere | `videogenre` |
| Tipo di flusso | `videostreamtype` |
| ID errore SDK del lettore | `videoqoeplayersdkerrors` |
| ID errore esterni | `videoqoeextneralerrors` |
| Tipo di feed multimediale | `videofeedtype` |
| Percorso file multimediali in ingresso | `entryvideopath` |
| Esci dal percorso multimediale | `exitvideopath` |
| Genere di ingresso | `entryvideogenre` |
| Tipo di uscita | `exitvideogenre` |
| ID errore SDK del lettore di ingresso | `entryvideoqoeplayersdkerrors` |
| Esci dagli ID errore SDK del lettore | `exitvideoqoeplayersdkerrors` |
| ID errore esterno voce | `entryvideoqoeextneralerrors` |
| Esci dagli ID errore esterni | `exitvideoqoeextneralerrors` |

### Adobe Social

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Termini | `socialterm` |
| Piattaforme/proprietà social | `socialcontentprovider` |
| Autori | `socialauthor` |
| Lingua | `sociallanguage` |
| Latitudine/longitudine | `sociallatlong` |
| Codici di tracciamento delle risorse | `socialassettrackingcode` |
| Proprietà social possedute | `socialaccountandappids` |
| ID post di proprietà | `socialownedpostids` |
| Definizioni sociali di proprietà | `socialinteractiontype` |
| ID proprietà posseduti | `socialownedpropertyid` |
| Proprietà di proprietà e applicazione | `socialownedpropertypropertyvsapp` |
| Nome proprietà posseduto | `socialownedpropertyname` |
| Proprietà definizione posseduta e post | `socialowneddefinitionpropertyvspost` |
| Tipo di visione della definizione di proprietà | `socialowneddefinitioninsighttype` |
| Valore di conoscenza della definizione di proprietà | `socialowneddefinitioninsightvalue` |
| Metrica di definizione di proprietà | `socialowneddefinitionmetric` |
| Risorsa | `socialmediaid` |

### Mobile SDK

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Data primo avvio | `mobileinstalldate` |
| Id App | `mobileappid` |
| Numero di avvii | `mobilelaunchnumber` |
| Giorni dal primo utilizzo | `mobiledayssincefirstuse` |
| Giorni dall’ultimo utilizzo | `mobiledayssincelastuse` |
| Ora del giorno (SDK) | `mobilehourofday` |
| Giorno della settimana (SDK) | `mobiledayofweek` |
| Sistema operativo (SDK) | `mobileosenvironment` |
| Giorni dall’ultimo aggiornamento | `mobiledayssincelastupgrade` |
| Avvii dall’ultimo aggiornamento | `mobilelaunchessincelastupgrade` |
| Nome del dispositivo (SDK) | `mobiledevice` |
| Versione del sistema operativo (SDK) | `mobileosversion` |
| Beacon principale | `mobilebeaconmajor` |
| Beacon minore | `mobilebeaconminor` |
| UUID beacon | `mobilebeaconuuid` |
| Prossimità beacon | `mobilebeaconproximity` |
| Posizione (fino a 10 chilometri) | `latlon1` |
| Posizione (fino a 100 m) | `latlon23` |
| Posizione (fino a 1 m) | `latlon45` |
| Nome del punto di interesse | `pointofinterest` |
| Distanza dal centro del punto di interesse | `pointofinterestdistance` |
| Precisione della posizione | `mobileplaceaccuracy` |
| Categoria posto | `mobileplacecategory` |
| ID posizione | `mobileplaceid` |
| Beacon principale di ingresso | `entrymobilebeaconmajor` |
| Esci dal beacon principale | `exitmobilebeaconmajor` |
| Beacon di ingresso secondario | `entrymobilebeaconminor` |
| Esci beacon secondario | `exitmobilebeaconminor` |
| UUID beacon di ingresso | `entrymobilebeaconuuid` |
| Esci da UUID beacon | `exitmobilebeaconuuid` |
| Prossimità beacon di ingresso | `entrymobilebeaconproximity` |
| Esci da prossimità beacon | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| ID EF AMO | `amo_ef_id` |
| ID AMO | `amo_cid` |

### Activity Map

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Collegamento Activity Map per area geografica | `clickmaplinkbyregion` |
| Area geografica di Activity Map | `clickmapregion` |
| Collegamento alla Activity Map | `clickmaplink` |
| Pagina della Activity Map | `clickmappage` |

### Integrazione Nielsen

Per ulteriori informazioni su come implementare questa integrazione, consulta la sezione [Estensione Nielsen](https://exchange.adobe.com/experiencecloud.details.101361.html).

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Modello di annunci Nielsen | `nielsenadmodel` |
| Segmento Nielsen C | `nielsensegmentc` |
| Segmento Nielsen B | `nielsensegmentb` |
| Segmento Nielsen A | `nielsensegmenta` |
| ID contenuto Nielsen | `nielsencontentid` |
| Risorsa/programma Nielsen | `nielsenasset` |
| Nielsen VCID | `nielsenvcid` |
| Nielsen Opt Out | `nielsenoptout` |
| ID client Nielsen + VCID | `nielsenclientidvcid` |
| ID client Nielsen | `nielsenclientid` |
| Ingresso Nielsen Opt Out | `entrynielsenoptout` |
| Esci da Nielsen Opt Out | `exitnielsenoptout` |
| ID client Nielsen + VCID | `entrynielsenclientidvcid` |
| Esci dall’ID client Nielsen + VCID | `exitnielsenclientidvcid` |
| ID client Nielsen di ingresso | `entrynielsenclientid` |
| Esci dall’ID client Nielsen | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| ID risorsa | `aemassetid` |
| Origine risorsa | `aemassetsource` |
| ID risorsa selezionato | `aemclickedassetid` |
| ID risorsa di ingresso | `entryaemassetid` |
| Esci da ID risorsa | `exitaemassetid` |

### Adobe Campaign

| Nome del Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| ID consegna eseguita di Adobe Campaign | `ac_delivery_internal_name` |
