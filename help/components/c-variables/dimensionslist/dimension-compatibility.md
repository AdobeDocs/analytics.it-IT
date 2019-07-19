---
title: Compatibilità dimensioni analisi
seo-title: Dimensioni e rapporti di Analytics compatibili con Analysis Workspace, Reporting e analisi o con entrambi.
description: Riferimento per dimensioni e rapporti di Analytics.
seo-description: Dimensioni di Analysis Workspace, dimensioni e dimensioni di Reporting e analisi, dimensioni, dimensioni R e A, Dimensioni Workspace
translation-type: tm+mt
source-git-commit: e3b1ac3139f26ca3a97f3d2228276e690ec4cb79

---


# Compatibilità dimensioni analisi

Questo articolo di riferimento elenca le dimensioni/i report supportati in Reporting e analisi e Area di lavoro Analisi, solo in Analysis Workspace, e solo in Reporting e analisi.

Tenete presente che

* Non sono elenchi completi. Ogni suite di rapporti può avere o meno un determinato set di variabili di prodotto abilitate. Inoltre, una qualsiasi suite di rapporti può avere un numero qualsiasi di variabili personalizzate abilitate o disabilitate o mappate alle variabili di prodotto. Abbiamo anche abbandonato gli attributi dei visitatori e le classificazioni, perché sono univoci per ogni suite di rapporti.

* There are some cases of overlap, where Analytics tools use different terms for what is essentially the same thing, for example: `browserwidth` and `browserwidthbucketed`.

## Dimensioni supportate in Reporting e analisi e Analysis Workspace

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|---|---|
| Analytics per Target | targetraw |
| ID audience | mcaudiences |
| Browser | browser |
| Tipo di browser | browsertype |
| Categoria | categoria |
| Città | geocity |
| Profondità colore | colordepth |
| Tipo connessione | connectiontype |
| Supporto cookie | cookie |
| Paesi | geocountry |
| Fedeltà cliente | customerfedeltà |
| Variabili conversione personalizzate | evar 1, evar 2, ecc. |
| Custom Insight Vars | prop 1, prop 2, ecc. |
| Collegamento personalizzato | customlink |
| Giorni prima del primo acquisto | daysbeforefirstpurchase |
| Giorni dall'ultimo acquisto | dayssincelastpurchase |
| Dominio | filtereddomain |
| Collegamento download | downloadlink |
| Pagina di immissione | entrypage |
| Pagina di immissione originale | entrypageoriginal |
| Chiudi collegamento | exitlink |
| Primo canale touch | firsttouchchannel |
| Primo dettaglio canale touch | firsttouchchanneldetail |
| Java abilitato | javaenabled |
| Lingua | language |
| Ultimo canale touch | lasttouchchannel |
| Dettagli ultimo canale touch | dettagli su layout |
| Variabili elenco | listvariables |
| Canale di marketing | marketingchannel |
| Supporto audio per dispositivi mobili | supporto mobileaudiosupporto |
| Gestore di telefonia mobile | mobilecarrier |
| Profondità colore mobile | mobilecolordepth |
| Supporto per cookie mobili | mobilecookiesupport |
| Dispositivo mobile | mobiledevicename |
| Tipo dispositivo mobile | mobiledevicetype |
| Lunghezza e-mail max-mobile | mobileemaillength |
| Supporto per immagini mobili | mobileimagesupport |
| Produttore mobile | mobilemanufacturer |
| Sistema operativo mobile (obsoleto) | mobileos |
| Altezza schermo mobile | mobilescreenheight |
| Dimensioni dello schermo del dispositivo mobile | mobilescreensize |
| Larghezza schermo mobile | mobilescreenwidth |
| Lunghezza URL max browser mobile | mobileurllength |
| Supporto video per dispositivi mobili | mobilevideosupport |
| Risoluzione monitor | risoluzione dello spostamento |
| Sistemi operativi | operatingsystem |
| Dominio di riferimento originale | referringdomainoriginal |
| Pagina | page |
| Pagine non trovate | pagesnotfound |
| Prodotto | prodotto |
| Referrer | referrer |
| Tipo referente | referrertype |
| Dominio di riferimento | referringdomain |
| Aree geografiche | georegion |
| Restituisci frequenza | returnfrequency |
| SC-tnt | tntbase |
| Motore di ricerca | searchengine |
| Ricerca parola chiave | parola chiave searchengineering |
| Motore di ricerca - Naturale | searchenginenatural |
| Motore di ricerca - Paid | searchengineering searchenginepaid |
| Ricerca parola chiave - Naturale | searchenginenaturalkeyword |
| Parola chiave Cerca - Pagamento | searchengineering paidkeyword |
| Tutte le classificazioni di ricerca | searchengineering pagerank |
| Server | server |
| Visite a pagina singola | singlepagevisit |
| Sezione sito | sezioni di siti |
| Tempo trascorso per visita - Granulare | sitetime |
| Codice di tracciamento | campaign |
| DMA USA | geodma |
| Stati Uniti | state |
| Tempo precedente all'evento | timebefore |
| Tempo trascorso per visita - Perforato | timapent |
| Profondità visita | pathlength |
| Numero visita | visitnumber |
| Codice postale | zip |

## Dimensioni supportate solo in Analysis Workspace

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| AM/PM | timepartampm |
| Altezza browser - Bande | browserheightbucketed |
| Larghezza browser - Bande | browserwidthbucketed |
| Giorno | daterangeday |
| Giorno del mese | timepartdayofmonth |
| Giorno della settimana | dayofweek |
| Giorno della settimana | timepartdayofweek |
| Giorno dell’anno | timepartdayofyear |
| Giorni dall'ultima visita | dayssincelastvisit |
| Approfondimenti personalizzati | entryprop |
| Variabili elenco di voci | entrylistvariables |
| Server di immissione | entryserver |
| Sezione Site Site | sezioni entrysitesections |
| Esci da approfondimenti personalizzati | exitprop |
| Esci da variabili elenco | exitlistvariables |
| Esci da pagina | exitpage |
| Exit Server | exitserver |
| Esci da sezione del sito | exitsitesezioni |
| Profondità hit | hitdepth |
| Tipo di hit | hittype |
| Ora | daterangehour |
| Ora del giorno | timeparthourofday |
| Dettaglio canale marketing | dettagli su marketingchanneldetail |
| Minuto | daterangeminute |
| Lunghezza segnalibro max. mobile | mobilebookmarklength |
| Numero dispositivo mobile | mobiledevicenumber |
| DRM Mobile | mobiledrm |
| Mobile Information Services | mobileinformationservices |
| Mobile Java VM | mobilejavavm |
| Decorazione di Mobile Mail | mobilemaildecoration |
| Protocolli di Mobile Net | mobilenetprotocolli |
| Push Push per parlare | mobilepushtospeak |
| Mese | daterangemonth |
| Mese dell’anno | timepartmonthofyear |
| Tipi di sistemi operativi | operatingsystemgroup |
| Ricerca pagata | paidsearch |
| Supporto cookie persistente | persistentcookie |
| Trimestre | daterangequarter |
| Trimestre dell’anno | timepartquarterofyear |
| Sondaggio | querybase |
| Tempo trascorso sulla pagina - Piegato | averagepagetime |
| Tempo trascorso sulla pagina - Granulare | pagetimeseconds |
| Motivo di rifiuto del tracciamento | optoutreason |
| Settimana/fine settimana | timepartweekdayweekend |
| Settimana | daterangeweek |
| Anno | daterangeyear |

## Dimensioni basate sul contenuto supportate solo in Analysis Workspace

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| Activity Map XY | clickmapxy |
| ID sessione multimediale | videosessionid |
| Metodo di accesso Nielsen | nielsenaccmethod |
| Nielsen App ID | nielsenappid |
| Nielsen Channel Asset | nielsenchannelasset |
| Nielsen Content Type | nielsencontenttype |

## Dimensioni supportate solo in Reporting e analisi

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| Altezza browser | browserheight |
| Larghezza browser | browserwidth |
| Clienti univoci giornalieri | dailyuniquecustomers |
| JavaScript | javascriptsupport |
| JavaScript versione | javascriptversion |
| Clienti univoci mensili | monthlyustomers |
| Clienti unici trimestrali | quarterlyuniquecustomers |
| Fusi orari | timezone |
| Domini di livello principale | topleveldomain |
| Stato visitatore | legacystate |
| Clienti univoci settimanali | weeklyuniquecustomers |
| Clienti annuali univoci | yearlyuniquecustomers |

## Report pre-configurati in Reporting e analisi

Reporting e analisi contiene più rapporti preconfigurati che non possono essere mappati su una dimensione specifica oppure se il rapporto utilizza una classe di dimensioni. Questi rapporti sono elencati qui:

* Lunghezza URL segnalibro
* Browser
* Tipi di browser
* Funnel di conversione campagna
* Funnel di conversione carrello
* Città
* Clic su pagina
* Paesi
* Cross-sell
* Funnel eventi personalizzati
* Supporto per Decoration Mail
* Trasmissione numero dispositivo (Attivato/Disattivato)
* Domains (Domini)
* DRM
* Pagine di immissione
* Esci da pagine
* Abbandono
* Percorsi completi
* Icities
* Servizi informativi
* Versione Java
* Lingue
* Percorsi più lunghi
* Visualizzatori simultanei
* Media giornaliero
* Dettagli file multimediali
* Panoramica file multimediali
* Risoluzioni monitor
* Protocolli di rete
* Plug-in Netscape
* Pagina successiva
* Flusso pagina successiva
* Sistemi operativi
* Tipi di sistemi operativi
* Profondità pagina
* Riepilogo pagina
* Pathfinder
* Flusso pagina precedente
* Pagina precedente
* PTT
* Funnel di conversione prodotti
* Funnel di conversione acquisto
* Domini di riferimento
* Aree geografiche
* Ricarica
* Motori di ricerca - Tutti
* Motori di ricerca - Naturale
* Motori di ricerca - Paid
* Cerca parole chiave - Tutto
* Ricerca parole chiave - Naturale
* Parole chiave Search - Paid
* Dettagli attività Target
* Tempo trascorso sulla pagina
* Fusi orari
* Domini di livello principale
* DMA USA
* Stati Stati Uniti
* Numero visita
* Home page visitatori

## Dimensioni basate sul contenuto supportate da Reporting e analisi e da Analysis Workspace

### Video (Media Analytics)

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| Contenuto | video |
| Segmento contenuto | videosegmento |
| Tipo di contenuto | videocontenttype |
| Nome lettore | videoadplayername |
| Annuncio nella posizione del contenitore | videoadinpod |
| Fotogrammi rilasciati | videoqoedroppedframecountevar |
| Errori | videoqoeerrorcountevar |
| Bitrate medio | videoqoebitrateaverageevar |
| Modifiche bitrate | videoqoebitratechangecountevar |
| Durata buffer totale | videoqoebuffertimeevar |
| Eventi buffer | videoqoebuffercountevar |
| Tempo di inizio | videoqoetimetostartevar |
| Ad pod | videoadpod |
| Percorso media | videopath |
| Annuncio | videoad |
| Nome lettore contenuto | videoplayername |
| Canale contenuto | videochannel |
| Capitolo | videocapitolo |
| Nome contenuto (variabile) | videoname |
| Lunghezza contenuto (variabile) | videolength |
| Nome annuncio (variabile) | videoadname |
| Lunghezza annuncio (variabile) | videoadlength |
| Mostra le informazioni | videoshow |
| Stagione | videoseason |
| Episodio | videoepisodio |
| Rete | videonetwork |
| Mostra tipo | videoshowtype |
| Caricamenti annunci | videoadload |
| MVPD | videomvpd |
| Part Part | videodaypart |
| Inserzionista | videoadadvertiser |
| ID campagna | videoadcampaign |
| Genere | videogenre |
| Tipo di flusso | videostreamtype |
| ID errore SDK di Player | videoqoeplayersdkerrors |
| ID errore esterni | videoqoeextneralerrors |
| Tipo feed multimediale | videofeedtype |
| Percorso media media | entryvideopath |
| Esci da percorso multimediale | exitvideopath |
| Voce di ingresso | entryvideogenre |
| Esci da genere | exitvideogenre |
| ID errore SDK di Adobe Entry Player | entryvideoqoeplayersdkerrors |
| ID errore SDK di uscita da Player | exitvideoqoeplayersdkerrors |
| ID errore esterni | entryvideoqoeextneralerrors |
| Uscire dagli ID errore esterni | exitvideoqoeextneralerrors |

### Adobe Social

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| Termini | socialterm |
| Piattaforme/proprietà social | socialcontentprovider |
| Autori | socialauthor |
| Lingua | sociallanguage |
| Latitudine/longitudine | sociallatlong |
| Codici di tracciamento risorse | socialassettrackingcode |
| Proprietà social di proprietà | socialaccountandappids |
| ID post di proprietà | socialownedpostids |
| Definizioni social di proprietà | socialinteractiontype |
| ID proprietà di proprietà | socialownedpropertyid |
| Proprietà di proprietà rispetto all'applicazione | socialownedpropertypropertyvsapp |
| Nome proprietà di proprietà | socialownedpropertyname |
| Proprietà di definizione di proprietà rispetto Post | socialowneddefinitionpropertyvspost |
| Tipo di Visual Insight di proprietà | socialowneddefinitioninsighttype |
| Valore di Insight definizione di proprietà | socialowneddefinitioninsightvalue |
| Metrica di definizione di proprietà | socialowneddefinitionmetric |
| Risorsa | socialmediaid |

### SDK di Mobile

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| Data primo avvio | mobileinstall data |
| ID app | mobileappid |
| Numero di avvii | mobilelaunchnumber |
| Giorni dal primo utilizzo | mobiledayssincefirstuse |
| Giorni dall'ultimo utilizzo | mobiledayssincelastuse |
| Ora del giorno (SDK) | mobilehourofday |
| Giorno della settimana (SDK) | mobiledayofweek |
| Sistema operativo (SDK) | mobileosenvironment |
| Giorni dall'ultimo aggiornamento | mobiledayssincelastupgrade |
| Avvii dall'ultimo aggiornamento | mobilelaunchessincelastupgrade |
| Nome dispositivo (SDK) | mobiledevice |
| Versione sistema operativo (SDK) | mobileosversion |
| Beacon Major | mobilebeaconmajor |
| Beacon secondario | mobilebeacon |
| UUCON BEUID | mobilebeaconuuid |
| Prossimità beacon | mobilebeaconproximity |
| Posizione (fino a 10 chilometri) | latlon1 |
| Posizione (fino a 100 m) | latlon23 |
| Posizione (fino a 1 m) | latlon45 |
| Nome del punto di interesse | pointofinterest |
| Distanza dal centro del punto di interesse | pointofinterestdistance |
| Precisione posizione | precisione mobileplace |
| Categoria Inserisci | mobileplacecategory |
| Inserisci ID | mobileplaceid |
| Grande beacon di ingresso | entrymobilebeacon |
| Exit Beacon Major | exitmobilebeacon |
| Beacon di ingresso | entrymobilebeacon |
| Esci da beacon secondario | exitmobilebeacon |
| UUID Beacon | entrymobilebeaconuuid |
| Exit Beacon UUID | exitmobilebeacon uuid |
| Prossimità beacon di ingresso | entrymobilebeacon |
| Chiudi vicinanza beacon | exitmobilebeacon |

### Adobe Advertising Cloud (AMO)

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| AMO EF ID | amo_ ef_ id |
| ID AMO | amo_ cid |

### Activity Map

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| Collegamento mappa dell'attività per regione | clickmaplinkbyarea |
| Regione Activity Map | clickmapregion |
| Collegamento alla Activity Map | clickmaplink |
| Pagina della Activity Map | clickmappage |

### Integrazione Nielsen

For more information on how to implement this integration, see [Nielsen partnership](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html).

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| Nielsen Ad Model | nielsenadmodel |
| Segmento Nielsen C | nielsensegmentc |
| Segmento Nielsen B | nielsensegmentb |
| Segmento Nielsen A | nielsensegmenta |
| ID contenuto Nielsen | nielsencontentid |
| Nielsen Asset/Program | nielsenasset |
| Nielsen VCID | nielsenvcid |
| Nielsen Opout | nielsenoptout |
| Nielsen Client ID + VCID | nielsenclientidvcid |
| ID client Nielsen | nielsenclientid |
| Voce Nielsen | entrynielsenoptout |
| Esci da Nielsen Opout | exitnielsenoptout |
| Voce Nielsen Client ID + VCID | entrynielsenclientidvcid |
| Exit Nielsen Client ID + VCID | exitnielsenclientidvcid |
| ID client Nielsen | entrynielsenclientid |
| Esci da ID client Nielsen | exitnielsenclientid |

### Adobe Experience Manager (AEM)

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| ID risorsa | aemassetid |
| Origine risorse | aemassetsource |
| ID risorsa con clic | aemclickedassetid |
| ID risorsa di ingresso | entryaemassetid |
| Exit Asset ID | exitaemassetid |

### Adobe Campaign

| Nome dimensione (visibile nell'interfaccia utente di Analytics) | ID dimensione (usato nelle richieste API) |
|--- |--- |
| ID consegna eseguito Adobe Campaign | ac_ delivery_ internal_ name |
