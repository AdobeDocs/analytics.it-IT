---
title: ' compatibilità dimensioni Analytics'
description: Riferimento per  dimensioni e rapporti Analytics.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '985'
ht-degree: 18%

---


#  compatibilità dimensioni Analytics

In questa pagina sono elencate le dimensioni supportate nelle rispettive funzionalità  Analytics.

>[!NOTE]
>
>Nomi di variabili personalizzate, classificazioni e attributi del visitatore vengono omessi da questo elenco. Questi valori di dimensione sono specifici delle singole suite di rapporti.

>[!NOTE]
>
>Esistono sovrapposizioni in cui  strumenti Analytics utilizzano termini diversi per dimensioni simili. Ad esempio, Reports &amp;  Analytics utilizza `browserwidth` mentre  Analysis Workspace utilizza `browserwidthbucketed`.

## Dimensioni supportate sia in Reporting e  Analytics che  Analysis Workspace

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|---|---|
|  Analytics per Target | `targetraw` |
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
| Variabili di conversione personalizzate | `evar1`, `evar2`ecc. |
| Custom Insight Vars | `prop1`, `prop2`ecc. |
| Collegamento personalizzato | `customlink` |
| Giorni precedenti al primo acquisto | `daysbeforefirstpurchase` |
| Giorni dall&#39;ultimo acquisto | `dayssincelastpurchase` |
| Dominio | `filtereddomain` |
| Collegamento di download | `downloadlink` |
| Pagina di ingresso | `entrypage` |
| Pagina di entrata originale | `entrypageoriginal` |
| Collegamento di uscita | `exitlink` |
| Primo canale touch | `firsttouchchannel` |
| Primo dettaglio canale touch | `firsttouchchanneldetail` |
| Java abilitato | `javaenabled` |
| Lingua | `language` |
| Ultimo canale touch | `lasttouchchannel` |
| Ultimo dettaglio canale touch | `lasttouchchanneldetail` |
| Variabili elenco | `listvariables` |
| Canale di marketing | `marketingchannel` |
| Supporto audio per dispositivi mobili | `mobileaudiosupport` |
| Gestore di telefonia mobile | `mobilecarrier` |
| Profondità colore mobile | `mobilecolordepth` |
| Supporto dei cookie per dispositivi mobili | `mobilecookiesupport` |
| Dispositivo mobile | `mobiledevicename` |
| Tipo di dispositivo mobile | `mobiledevicetype` |
| Lunghezza max e-mail mobile | `mobileemaillength` |
| Supporto per immagini mobili | `mobileimagesupport` |
| Produttore di dispositivi mobili | `mobilemanufacturer` |
| Sistema operativo mobile (obsoleto) | `mobileos` |
| Altezza schermo mobile | `mobilescreenheight` |
| Dimensioni dello schermo del dispositivo mobile | `mobilescreensize` |
| Larghezza schermo mobile | `mobilescreenwidth` |
| Lunghezza massima URL browser mobile | `mobileurllength` |
| Supporto per video per dispositivi mobili | `mobilevideosupport` |
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
| Cerca parola chiave | `searchenginekeyword` |
| Motore di ricerca - Naturale | `searchenginenatural` |
| Motore di ricerca - Pagato | `searchenginepaid` |
| Parola chiave di ricerca - Naturale | `searchenginenaturalkeyword` |
| Parola chiave di ricerca - pagata | `searchenginepaidkeyword` |
| Seleziona tutte le pagine di ricerca | `searchenginepagerank` |
| Server | `server` |
| Visite a pagina singola | `singlepagevisits` |
| Sezione del sito | `sitesections` |
| Tempo trascorso per visita - Granulare | `sitetime` |
| Codice di tracciamento | `campaign` |
| DMA USA | `geodma` |
| Stati Uniti | `state` |
| Tempo precedente all&#39;evento | `timeprior` |
| Tempo trascorso per visita - A intervalli | `timespent` |
| Profondità visita | `pathlength` |
| Numero visita | `visitnumber` |
| Codice postale | `zip` |

## Dimensioni supportate solo in  Analysis Workspace

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| AM/PM | `timepartampm` |
| Altezza browser - Esteso | `browserheightbucketed` |
| Larghezza browser - Estremità | `browserwidthbucketed` |
| Day | `daterangeday` |
| Giorno del mese | `timepartdayofmonth` |
| Giorno della settimana | `dayofweek` |
| Giorno della settimana | `timepartdayofweek` |
| Giorno dell’anno | `timepartdayofyear` |
| Giorni dall&#39;ultima visita | `dayssincelastvisit` |
| Approfondimenti personalizzati | `entryprops` |
| Variabili elenco voci | `entrylistvariables` |
| Entry Server | `entryserver` |
| Sezione Sito di entrata | `entrysitesections` |
| Esci da approfondimenti personalizzati | `exitprops` |
| Variabili elenco di uscita | `exitlistvariables` |
| Esci da pagina | `exitpage` |
| Exit Server | `exitserver` |
| Esci dalla sezione del sito | `exitsitesections` |
| Profondità di hit | `hitdepth` |
| Tipo di occorrenza | `hittype` |
| Ora | `daterangehour` |
| Ora del giorno | `timeparthourofday` |
| Dettagli canale di marketing | `marketingchanneldetail` |
| Minuto | `daterangeminute` |
| Lunghezza massima segnalibro per dispositivi mobili | `mobilebookmarklength` |
| Numero dispositivo mobile | `mobiledevicenumber` |
| DRM mobile | `mobiledrm` |
| Mobile Information Services | `mobileinformationservices` |
| VM Java mobile | `mobilejavavm` |
| Decorazione di Mobile Mail | `mobilemaildecoration` |
| Protocolli di Mobile Net | `mobilenetprotocols` |
| Invio Per Dispositivi Mobili Per Parlare | `mobilepushtotalk` |
| Mese | `daterangemonth` |
| Mese dell’anno | `timepartmonthofyear` |
| Tipi di sistemi operativi | `operatingsystemgroup` |
| Ricerca pagata | `paidsearch` |
| Supporto Cookie Persistente | `persistentcookie` |
| Trimestre | `daterangequarter` |
| Trimestre dell’anno | `timepartquarterofyear` |
| Sondaggio | `surveybase` |
| Tempo trascorso sulla pagina - Interrotto | `averagepagetime` |
| Tempo trascorso sulla pagina - Granulare | `pagetimeseconds` |
| Motivo rifiuto tracciamento | `optoutreason` |
| Giorno feriale/Fine settimana | `timepartweekdayweekend` |
| Settimana | `daterangeweek` |
| Anno | `daterangeyear` |

## Dimensioni in base al contenuto supportate solo in  Analysis Workspace

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
|  Activity Map XY | `clickmapxy` |
| ID sessione multimediale | `videosessionid` |
| Metodo di accesso Nielsen | `nielsenaccmethod` |
| ID app Nielsen | `nielsenappid` |
| Risorsa canale Nielsen | `nielsenchannelasset` |
| Nielsen Content Type | `nielsencontenttype` |

## Dimensioni supportate solo in Reporting e  Analytics

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
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
| Clienti unici settimanali | `weeklyuniquecustomers` |
| Clienti univoci annuali | `yearlyuniquecustomers` |

## Dimensioni in base al contenuto supportate da Reporting e  Analytics e  Analysis Workspace

### Video ( multimediale Analytics)

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Contenuto | `video` |
| Segmento di contenuto | `videosegment` |
| Tipo di contenuto | `videocontenttype` |
| Nome lettore pubblicitario | `videoadplayername` |
| Aggiungi in posizione contenitore | `videoadinpod` |
| Fotogrammi rilasciati | `videoqoedroppedframecountevar` |
| Errori | `videoqoeerrorcountevar` |
| Bitrate medio | `videoqoebitrateaverageevar` |
| Modifiche bitrate | `videoqoebitratechangecountevar` |
| Durata totale buffer | `videoqoebuffertimeevar` |
| Eventi buffer | `videoqoebuffercountevar` |
| Ora di inizio | `videoqoetimetostartevar` |
| Ad Pod | `videoadpod` |
| Percorso supporto | `videopath` |
| Annuncio | `videoad` |
| Nome lettore contenuti | `videoplayername` |
| Canale contenuto | `videochannel` |
| Capitolo | `videochapter` |
| Nome contenuto (variabile) | `videoname` |
| Lunghezza contenuto (variabile) | `videolength` |
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
| ID errore SDK lettore | `videoqoeplayersdkerrors` |
| ID errore esterni | `videoqoeextneralerrors` |
| Tipo di feed multimediale | `videofeedtype` |
| Percorso file multimediali | `entryvideopath` |
| Esci dal percorso del supporto | `exitvideopath` |
| Genere di ingresso | `entryvideogenre` |
| Tipo di uscita | `exitvideogenre` |
| ID errore SDK del lettore entry-level | `entryvideoqoeplayersdkerrors` |
| Esci dagli ID errore SDK Player | `exitvideoqoeplayersdkerrors` |
| ID errore esterno voce | `entryvideoqoeextneralerrors` |
| Esci da ID errore esterni | `exitvideoqoeextneralerrors` |

### Adobe Social

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Termini | `socialterm` |
| Piattaforme/Proprietà social | `socialcontentprovider` |
| Autori | `socialauthor` |
| Lingua | `sociallanguage` |
| Latitudine/longitudine | `sociallatlong` |
| Codici di tracciamento delle risorse | `socialassettrackingcode` |
| Proprietà Social | `socialaccountandappids` |
| ID post di proprietà | `socialownedpostids` |
| Definizioni social network di proprietà | `socialinteractiontype` |
| ID proprietà | `socialownedpropertyid` |
| Proprietà di proprietà e applicazione | `socialownedpropertypropertyvsapp` |
| Nome proprietà | `socialownedpropertyname` |
| Proprietà definizione di proprietà e post | `socialowneddefinitionpropertyvspost` |
| Tipo di visione della definizione di proprietà | `socialowneddefinitioninsighttype` |
| Valore Insight definizione di proprietà | `socialowneddefinitioninsightvalue` |
| Metrica definizione di proprietà | `socialowneddefinitionmetric` |
| Risorsa | `socialmediaid` |

### Mobile SDK

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Data primo avvio | `mobileinstalldate` |
| ID app | `mobileappid` |
| Numero di avvii | `mobilelaunchnumber` |
| Giorni dal primo utilizzo | `mobiledayssincefirstuse` |
| Giorni dall’ultimo utilizzo | `mobiledayssincelastuse` |
| Ora del giorno (SDK) | `mobilehourofday` |
| Giorno della settimana (SDK) | `mobiledayofweek` |
| Sistema operativo (SDK) | `mobileosenvironment` |
| Giorni dall’ultimo aggiornamento | `mobiledayssincelastupgrade` |
| Avvii dall’ultimo aggiornamento | `mobilelaunchessincelastupgrade` |
| Nome dispositivo (SDK) | `mobiledevice` |
| Versione sistema operativo (SDK) | `mobileosversion` |
| Beacon principale | `mobilebeaconmajor` |
| Beacon minore | `mobilebeaconminor` |
| Beacon UUID | `mobilebeaconuuid` |
| Prossimità beacon | `mobilebeaconproximity` |
| Posizione (fino a 10 chilometri) | `latlon1` |
| Posizione (fino a 100 m) | `latlon23` |
| Posizione (fino a 1 m) | `latlon45` |
| Nome del punto di interesse | `pointofinterest` |
| Distanza dal centro del punto di interesse | `pointofinterestdistance` |
| Precisione posizione | `mobileplaceaccuracy` |
| Categoria posto | `mobileplacecategory` |
| ID posizione | `mobileplaceid` |
| Beacon principale voce | `entrymobilebeaconmajor` |
| Esci dal beacon principale | `exitmobilebeaconmajor` |
| Beacon voce secondaria | `entrymobilebeaconminor` |
| Esci da beacon secondario | `exitmobilebeaconminor` |
| UUID beacon voce | `entrymobilebeaconuuid` |
| Exit Beacon UUID | `exitmobilebeaconuuid` |
| Prossimità beacon di ingresso | `entrymobilebeaconproximity` |
| Esci da prossimità beacon | `exitmobilebeaconproximity` |

### Adobe  Advertising Cloud (AMO)

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| ID EF AMO | `amo_ef_id` |
| ID AMO | `amo_cid` |

### Activity Map

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Collegamento Activity Map  Per Regione | `clickmaplinkbyregion` |
|  Activity Map | `clickmapregion` |
| Collegamento alla Activity Map | `clickmaplink` |
| Pagina della Activity Map | `clickmappage` |

### Integrazione Nielsen

Per ulteriori informazioni su come implementare questa integrazione, consultate [Nielsen Extension](https://exchange.adobe.com/experiencecloud.details.101361.html).

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Modello pubblicitario Nielsen | `nielsenadmodel` |
| Segmento Nielsen C | `nielsensegmentc` |
| Segmento Nielsen B | `nielsensegmentb` |
| Segmento Nielsen A | `nielsensegmenta` |
| Nielsen Content ID | `nielsencontentid` |
| Risorse/Programma Nielsen | `nielsenasset` |
| Nielsen VCID | `nielsenvcid` |
| Rifiuto Nielsen | `nielsenoptout` |
| ID client Nielsen + VCID | `nielsenclientidvcid` |
| ID client Nielsen | `nielsenclientid` |
| Rifiuto Nielsen | `entrynielsenoptout` |
| Esci da Nielsen Rifiuta | `exitnielsenoptout` |
| ID client Nielsen + VCID | `entrynielsenclientidvcid` |
| Esci da ID client Nielsen + VCID | `exitnielsenclientidvcid` |
| ID client Nielsen | `entrynielsenclientid` |
| Esci dall&#39;ID client Nielsen | `exitnielsenclientid` |

### Adobe Experience Manager (AEM)

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| ID risorsa | `aemassetid` |
| Origine risorsa | `aemassetsource` |
| ID risorsa selezionata | `aemclickedassetid` |
| ID risorsa voce | `entryaemassetid` |
| Esci ID risorsa | `exitaemassetid` |

### Adobe Campaign

| Nome dimensione (visibile nell’interfaccia  Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| ID consegna eseguita di Adobe Campaign | `ac_delivery_internal_name` |
