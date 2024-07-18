---
title: Compatibilità dei Dimension Analytics
description: Riferimento per dimensioni e rapporti di Analytics.
feature: Dimensions
exl-id: 1884bc20-b04d-4f9a-b057-2b2fbe53190d
source-git-commit: 4633225cc35658a7de39a40cd77df00137a54461
workflow-type: tm+mt
source-wordcount: '890'
ht-degree: 33%

---

# Compatibilità dei Dimension Analytics

In questa pagina sono elencate le [dimensioni](overview.md) supportate nelle rispettive funzionalità di Analytics.

>[!NOTE]
>
>I nomi delle variabili, le classificazioni e gli attributi dei visitatori personalizzati vengono omessi da questo elenco. Questi elementi dimensionali sono specifici per le singole suite di rapporti.

## Dimension supportati in Analysis Workspace

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|---|---|
| Analytics for Target | `targetraw` |
| ID tipi di pubblico | `mcaudiences` |
| Browser | `browser` |
| Tipo di browser | `browsertype` |
| Categoria | `category` |
| Città | `geocity` |
| Profondità colore | `colordepth` |
| Tipo di connessione | `connectiontype` |
| Supporto per cookie | `cookie` |
| Paesi | `geocountry` |
| Fedeltà del cliente | `customerloyalty` |
| Variabili di conversione personalizzate | `evar1`, `evar2`, ecc. |
| Variabili Custom Insight | `prop1`, `prop2`, ecc. |
| Collegamento personalizzato | `customlink` |
| Giorni precedenti al primo acquisto | `daysbeforefirstpurchase` |
| Giorni dall’ultimo acquisto | `dayssincelastpurchase` |
| Dominio | `filtereddomain` |
| Collegamento di download. | `downloadlink` |
| Pagina di ingresso | `entrypage` |
| Pagina di ingresso originale | `entrypageoriginal` |
| Collegamento di uscita. | `exitlink` |
| Canale di primo contatto | `firsttouchchannel` |
| Dettaglio canale di primo contatto | `firsttouchchanneldetail` |
| Java abilitato | `javaenabled` |
| Lingua | `language` |
| Canale ultimo contatto | `lasttouchchannel` |
| Dettaglio canale ultimo contatto | `lasttouchchanneldetail` |
| Variabili elenco | `listvariables` |
| Canale di marketing | `marketingchannel` |
| Supporto audio per dispositivi mobili | `mobileaudiosupport` |
| Operatore telefonia mobile | `mobilecarrier` |
| Profondità colore mobile | `mobilecolordepth` |
| Supporto per cookie mobili | `mobilecookiesupport` |
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
| Supporto video per dispositivi mobili | `mobilevideosupport` |
| Risoluzione monitor | `monitorresolution` |
| Sistemi operativi | `operatingsystem` |
| Dominio di riferimento originale | `referringdomainoriginal` |
| Pagina | `page` |
| Pagine non trovate | `pagesnotfound` |
| Prodotto | `product` |
| Pagina di provenienza | `referrer` |
| Tipo di referrer | `referrertype` |
| Dominio di riferimento | `referringdomain` |
| Aree geografiche | `georegion` |
| Frequenza di ritorno | `returnfrequency` |
| SC-TnT | `tntbase` |
| Motore di ricerca | `searchengine` |
| Parola chiave di ricerca | `searchenginekeyword` |
| Motore di ricerca - Naturale | `searchenginenatural` |
| Motore di ricerca - A pagamento | `searchenginepaid` |
| Parola chiave di ricerca - Naturale | `searchenginenaturalkeyword` |
| Parola chiave di ricerca - A pagamento | `searchenginepaidkeyword` |
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
| AM/PM | `timepartampm` |
| Altezza browser - Bucket | `browserheightbucketed` |
| Larghezza browser - Bucket | `browserwidthbucketed` |
| Giorno | `daterangeday` |
| Giorno del mese | `timepartdayofmonth` |
| Giorno della settimana | `dayofweek` |
| Giorno della settimana | `timepartdayofweek` |
| Giorno dell’anno | `timepartdayofyear` |
| Giorni dall’ultima visita | `dayssincelastvisit` |
| Immissione di approfondimenti personalizzati | `entryprops` |
| Variabili elenco voci | `entrylistvariables` |
| Server di ingresso | `entryserver` |
| Sezione sito di ingresso | `entrysitesections` |
| Esci da Approfondimenti personalizzati | `exitprops` |
| Esci da variabili elenco | `exitlistvariables` |
| Esci da pagina | `exitpage` |
| Esci dal server | `exitserver` |
| Esci dalla sezione del sito | `exitsitesections` |
| Profondità di hit | `hitdepth` |
| Tipo di hit | `hittype` |
| Ora | `daterangehour` |
| Ora del giorno | `timeparthourofday` |
| Dettagli canale di marketing | `marketingchanneldetail` |
| Minuto | `daterangeminute` |
| Lunghezza massima segnalibro mobile | `mobilebookmarklength` |
| Numero dispositivo mobile | `mobiledevicenumber` |
| DRM mobile | `mobiledrm` |
| Mobile Information Services | `mobileinformationservices` |
| VM Java mobile | `mobilejavavm` |
| Decoration Mail mobile | `mobilemaildecoration` |
| Protocolli di rete mobile | `mobilenetprotocols` |
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

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| XY ACTIVITY MAP | `clickmapxy` |
| ID sessione multimediale | `videosessionid` |
| Metodo di accesso Nielsen | `nielsenaccmethod` |
| ID app Nielsen | `nielsenappid` |
| Risorsa di canale Nielsen | `nielsenchannelasset` |
| Tipo di contenuto Nielsen | `nielsencontenttype` |

## Dimensioni in base al contenuto supportate da Analysis Workspace

### Video (componente aggiuntivo Streaming Media Collection)

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Contenuto | `video` |
| Segmento di contenuto | `videosegment` |
| Tipo di contenuto | `videocontenttype` |
| Nome del lettore dell’annuncio | `videoadplayername` |
| Annuncio in posizione pod | `videoadinpod` |
| Frame rilasciati | `videoqoedroppedframecountevar` |
| Errori | `videoqoeerrorcountevar` |
| Bitrate medio | `videoqoebitrateaverageevar` |
| Modifiche bitrate | `videoqoebitratechangecountevar` |
| Durata totale buffer | `videoqoebuffertimeevar` |
| Eventi buffer | `videoqoebuffercountevar` |
| Tempo di avvio | `videoqoetimetostartevar` |
| Pod annuncio | `videoadpod` |
| Percorso file multimediale | `videopath` |
| Annuncio | `videoad` |
| Nome del lettore di contenuti | `videoplayername` |
| Canale del contenuto | `videochannel` |
| Capitolo | `videochapter` |
| Nome contenuto (variabile) | `videoname` |
| Lunghezza del contenuto (variabile) | `videolength` |
| Nome annuncio (variabile) | `videoadname` |
| Lunghezza annuncio (variabile) | `videoadlength` |
| Spettacolo | `videoshow` |
| Stagione | `videoseason` |
| Episodio | `videoepisode` |
| Rete | `videonetwork` |
| Tipo di spettacolo | `videoshowtype` |
| Caricamenti annunci | `videoadload` |
| MVPD | `videomvpd` |
| Fascia oraria | `videodaypart` |
| Inserzionista | `videoadadvertiser` |
| ID campagna | `videoadcampaign` |
| Genere | `videogenre` |
| Tipo di flusso | `videostreamtype` |
| ID errore SDK del lettore | `videoqoeplayersdkerrors` |
| ID errore esterni | `videoqoeextneralerrors` |
| Tipo di feed multimediale | `videofeedtype` |
| Percorso file multimediale di ingresso | `entryvideopath` |
| Esci da percorso file multimediale | `exitvideopath` |
| Genere voce | `entryvideogenre` |
| Genere di uscita | `exitvideogenre` |
| ID degli errori SDK del lettore della voce | `entryvideoqoeplayersdkerrors` |
| ID degli errori dell’SDK di uscita dal lettore | `exitvideoqoeplayersdkerrors` |
| ID errore esterni di immissione | `entryvideoqoeextneralerrors` |
| Esci da ID errore esterni | `exitvideoqoeextneralerrors` |

### Adobe Social

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Termini | `socialterm` |
| Piattaforme/Proprietà social | `socialcontentprovider` |
| Autori | `socialauthor` |
| Lingua | `sociallanguage` |
| Latitudine/Longitudine | `sociallatlong` |
| Codici di tracciamento risorse | `socialassettrackingcode` |
| Proprietà social possedute | `socialaccountandappids` |
| ID Post di proprietà | `socialownedpostids` |
| Definizioni social di proprietà | `socialinteractiontype` |
| ID proprietà possedute | `socialownedpropertyid` |
| Proprietà di proprietà e applicazione | `socialownedpropertypropertyvsapp` |
| Nome proprietà di proprietà | `socialownedpropertyname` |
| Proprietà di definizione di proprietà e Post | `socialowneddefinitionpropertyvspost` |
| Tipo di informazioni sulla definizione di proprietà | `socialowneddefinitioninsighttype` |
| Valore informazioni definizione di proprietà | `socialowneddefinitioninsightvalue` |
| Metrica di definizione di proprietà | `socialowneddefinitionmetric` |
| Risorsa | `socialmediaid` |

### Mobile SDK

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Data primo avvio | `mobileinstalldate` |
| ID app | `mobileappid` |
| Numero avvii | `mobilelaunchnumber` |
| Giorni dal primo utilizzo | `mobiledayssincefirstuse` |
| Giorni dall’ultimo utilizzo | `mobiledayssincelastuse` |
| Ora del giorno (SDK) | `mobilehourofday` |
| Giorno della settimana (SDK) | `mobiledayofweek` |
| Sistema operativo (SDK) | `mobileosenvironment` |
| Giorni dall&#39;ultimo aggiornamento | `mobiledayssincelastupgrade` |
| Avvii dall&#39;ultimo aggiornamento | `mobilelaunchessincelastupgrade` |
| Nome dispositivo (SDK) | `mobiledevice` |
| Versione sistema operativo (SDK) | `mobileosversion` |
| Beacon principale | `mobilebeaconmajor` |
| Beacon secondario | `mobilebeaconminor` |
| UUID beacon | `mobilebeaconuuid` |
| Prossimità beacon | `mobilebeaconproximity` |
| Posizione (fino a 10 chilometri) | `latlon1` |
| Posizione (fino a 100 m) | `latlon23` |
| Posizione (fino a 1 m) | `latlon45` |
| Nome del punto di interesse | `pointofinterest` |
| Distanza dal centro del punto di interesse | `pointofinterestdistance` |
| Precisione della posizione | `mobileplaceaccuracy` |
| Categoria del luogo | `mobileplacecategory` |
| ID luogo | `mobileplaceid` |
| Beacon di ingresso principale | `entrymobilebeaconmajor` |
| Esci da beacon principale | `exitmobilebeaconmajor` |
| Beacon di ingresso secondario | `entrymobilebeaconminor` |
| Esci da beacon secondario | `exitmobilebeaconminor` |
| UUID beacon di ingresso | `entrymobilebeaconuuid` |
| UUID beacon di uscita | `exitmobilebeaconuuid` |
| Prossimità beacon di ingresso | `entrymobilebeaconproximity` |
| Esci da prossimità beacon | `exitmobilebeaconproximity` |

### Adobe Advertising Cloud (AMO)

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| ID AMO EF | `amo_ef_id` |
| ID AMO | `amo_cid` |

### Activity Map

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| Collegamento Activity Map per area geografica | `clickmaplinkbyregion` |
| Area geografica di Activity Map | `clickmapregion` |
| Collegamento Activity Map | `clickmaplink` |
| Pagina di Activity Map | `clickmappage` |

### Integrazione Nielsen

Per ulteriori informazioni su come implementare questa integrazione, consulta l&#39;estensione [Nielsen](https://exchange.adobe.com/experiencecloud.details.101361.html).

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
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

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| ID risorsa | `aemassetid` |
| Origine risorsa | `aemassetsource` |
| ID risorsa selezionata | `aemclickedassetid` |
| ID risorsa di ingresso | `entryaemassetid` |
| Esci da ID risorsa | `exitaemassetid` |

### Adobe Campaign

| Nome Dimension (visibile nell’interfaccia utente di Analytics) | ID Dimension (utilizzato nelle richieste API) |
|--- |--- |
| ID consegna eseguita di Adobe Campaign | `ac_delivery_internal_name` |
