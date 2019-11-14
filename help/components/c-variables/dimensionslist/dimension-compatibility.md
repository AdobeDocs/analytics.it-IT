---
title: Compatibilità delle dimensioni di Analytics
description: Riferimento per le dimensioni e i report di Analytics.
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Compatibilità delle dimensioni di Analytics

Questo articolo di riferimento elenca le dimensioni/i rapporti supportati sia in Reporting e analisi che in Analysis Workspace, solo in Analysis Workspace e solo in Reporting e analisi.

Ricorda che

* Non si tratta di elenchi esaustivi. Ciascuna suite di rapporti può avere o meno attivato un determinato set di variabili di prodotto. Inoltre, qualsiasi suite di rapporti può avere un numero qualsiasi di variabili personalizzate abilitate o disabilitate o mappate a variabili di prodotto. Abbiamo anche omesso gli attributi e le classificazioni dei visitatori, poiché sono univoci per ogni suite di rapporti.

* Esistono alcuni casi di sovrapposizione, in cui gli strumenti Analytics utilizzano termini diversi per ciò che è sostanzialmente la stessa cosa, ad esempio: `browserwidth` e `browserwidthbucketed`.

## Dimensioni supportate sia in Reporting e analisi che in Analysis Workspace

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|---|---|
| Analisi per Target | targetraw |
| ID pubblico | mescolanza |
| Browser | browser |
| Tipo di browser | browsertype |
| Categoria | categoria |
| Città | geocità |
| Profondità colore | colorimetria |
| Tipo connessione | connectiontype |
| Supporto per cookie | cookie |
| Paesi | paese |
| Fedeltà cliente | fedeltà dei clienti |
| Variabili di conversione personalizzate | evar1, evar2, ecc. |
| Varie di visualizzazione personalizzate | prop1, prop2, ecc. |
| Collegamento personalizzato | customlink |
| Giorni precedenti al primo acquisto | daysbeforePurchase |
| Giorni dall'ultimo acquisto | dayssincelastpurchase |
| Dominio | filtereddomain |
| Collegamento di download | downloadlink |
| Pagina di entrata | entrata |
| Pagina di entrata originale | entrypageOriginal |
| Collegamento di uscita | exitlink |
| Primo canale touch | firsttouchchannel |
| Primo dettaglio canale touch | firsttouchchanneldettaglio |
| Java abilitato | javaenabled |
| Lingua | language |
| Ultimo canale touch | lasttouchchannel |
| Ultimo dettaglio canale touch | lasttouchchanneldettaglio |
| Variabili elenco | listvariables |
| Canale di marketing | canale di marketing |
| Supporto audio per dispositivi mobili | mobileaudiosupporto |
| Gestore di telefonia mobile | operatore |
| Profondità colore mobile | mobilecolorprofondità |
| Supporto dei cookie per dispositivi mobili | mobilecookiesupport |
| Dispositivo mobile | mobiledevicename |
| Tipo di dispositivo mobile | mobiledevicetype |
| Lunghezza max e-mail mobile | mobileemaillength |
| Supporto per immagini mobili | mobileimagesupport |
| Produttore di dispositivi mobili | mobilemanificatore |
| Sistema operativo mobile (obsoleto) | mobileos |
| Altezza schermo mobile | mobilescreenheight |
| Dimensioni dello schermo del dispositivo mobile | mobilescreensize |
| Larghezza schermo mobile | mobilescreenwidth |
| Lunghezza massima URL browser mobile | mobileurllength |
| Supporto per video mobile | mobilevideosupport |
| Risoluzione monitor | monitorresolution |
| Sistemi operativi | sistema operativo |
| Dominio di riferimento originale | referringdomainoriginale |
| Pagina | page |
| Pagine non trovate | pagesnotfound |
| Prodotto | prodotto |
| Referrer | referrer |
| Tipo di riferimento | referrertype |
| Dominio di riferimento | referringdomain |
| Aree geografiche | georegione |
| Restituisci frequenza | frequenza di ritorno |
| SC-TnT | tntbase |
| Motore di ricerca | ricercatore |
| Cerca parola chiave | searchEnginekeyword |
| Motore di ricerca - Naturale | search enginenatural |
| Motore di ricerca - Pagato | search enginepaid |
| Parola chiave di ricerca - Naturale | search enginaturalkeyword |
| Parola chiave di ricerca - pagata | search ingegnpaidkeyword |
| Seleziona tutte le pagine di ricerca | search enginepagerank |
| Server | server |
| Visite a pagina singola | singlepfacilitisits |
| Sezione del sito | sezioni di sito |
| Tempo trascorso per visita - Granulare | sitetime |
| Codice di tracciamento | campaign |
| DMA USA | geodma |
| Stati Uniti | state |
| Tempo precedente all'evento | time before |
| Tempo trascorso per visita - A intervalli | durata |
| Profondità visita | pathlength |
| Numero visita | visitnumber |
| Codice postale | zip |

## Dimensioni supportate solo in Analysis Workspace

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| AM/PM | timpartampm |
| Altezza browser - Esteso | browserheightbuck |
| Larghezza browser - Estremità | browserwidthbuck |
| Day | daterangeday |
| Giorno del mese | time partday of month |
| Giorno della settimana | giorno della settimana |
| Giorno della settimana | time partday of week |
| Giorno dell’anno | timepartday of year |
| Giorni dall'ultima visita | dayssincelastvisit |
| Approfondimenti personalizzati | entryprops |
| Variabili elenco voci | entrylistvariables |
| Entry Server | entryserver |
| Sezione Sito di entrata | sezioni di entrata |
| Esci da approfondimenti personalizzati | exitprops |
| Variabili elenco di uscita | exitlistvariables |
| Esci da pagina | exitpage |
| Exit Server | exitserver |
| Esci dalla sezione del sito | exitsitesections |
| Profondità di hit | profondità |
| Tipo di occorrenza | tipo |
| Ora | daterangehour |
| Ora del giorno | timeparthourofday |
| Dettagli canale di marketing | marketingchanneldetail |
| Minuto | daterangeminute |
| Lunghezza massima segnalibro per dispositivi mobili | mobilebookmarklength |
| Numero dispositivo mobile | mobiledevicenumber |
| DRM mobile | mobiledrm |
| Mobile Information Services | mobileinformationservices |
| VM Java mobile | mobilejavavavm |
| Decorazione di Mobile Mail | mobilemaildecoration |
| Protocolli di Mobile Net | mobilenetprotocolli |
| Invio Per Dispositivi Mobili Per Parlare | mobilepushtotalk |
| Mese | daterangemonth |
| Mese dell’anno | timepartmonthof year |
| Tipi di sistemi operativi | operatingsystemgroup |
| Ricerca pagata | paidsearch |
| Supporto Cookie Persistente | persistentcookie |
| Trimestre | daterangequarter |
| Trimestre dell’anno | timepartquarterofyear |
| Sondaggio | topografia |
| Tempo trascorso sulla pagina - Interrotto | averagepagetime |
| Tempo trascorso sulla pagina - Granulare | pagetimeseconds |
| Motivo rifiuto tracciamento | optoutreason |
| Giorno feriale/Fine settimana | weekend |
| Settimana | daterangeweek |
| Anno | daterangeyear |

## Dimensioni in base al contenuto supportate solo in Analysis Workspace

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
|  Activity Map XY | clickmapxy |
| ID sessione multimediale | videosess ionid |
| Metodo di accesso Nielsen | nielsenacmetodo |
| ID app Nielsen | nielsenappid |
| Risorsa canale Nielsen | nielsenchannelasset |
| Nielsen Content Type | nielsencontenttype |

## Dimensioni supportate solo in Reporting e analisi

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Altezza browser | browserheight |
| Larghezza browser | browserwidth |
| Clienti univoci giornalieri | dailyunicecustomers |
| JavaScript | javascriptsupport |
| JavaScript versione | javascriptversion |
| Clienti univoci mensili | clienti unici mensili |
| Clienti univoci trimestrali | clienti di quarterlyuniveca |
| Fusi orari | timezone |
| Domini di livello principali | topleveldomain |
| Stato visitatore | legacystate |
| Clienti unici settimanali | weekend esclusivamente clienti |
| Clienti univoci annuali | yearlyunicecustomers |

## Report preconfigurati in Reporting e analisi

Reporting e analisi contiene più report preconfigurati che non vengono mappati a una dimensione specifica, oppure il report utilizza una classe di dimensioni. Questi rapporti sono elencati di seguito:

* Lunghezza URL segnalibro
* Browser
* Tipi di browser
* Funnel di conversione campagna
* Funnel di conversione del carrello
* Città
* Clic sulla pagina
* Paesi
* Vendita incrociata
* Funnel eventi personalizzati
* Supporto per Decoration Mail
* Trasmissione numero dispositivo (ON/OFF)
* Domains (Domini)
* DRM
* Pagine di entrata
* Esci da pagine
* Abbandono
* Percorsi completi
* ICities
* Servizi informativi
* Versione Java
* Lingue
* Percorsi più lunghi
* Visualizzatori simultanei
* Daypart Media
* Dettagli supporto
* Panoramica sui supporti
* Risoluzioni monitor
* Protocolli di rete
* Plug-in Netscape
* Pagina successiva
* Flusso pagina successiva
* Sistemi operativi
* Tipi di sistemi operativi
* Profondità pagina
* Riepilogo pagina
* PathFinder
* Flusso pagina precedente
* Pagina precedente
* PTT
* Funnel di conversione prodotti
* Funnel di conversione acquisti
* Domini di riferimento
* Aree geografiche
* Ricariche
* Motori di ricerca - Tutti
* Motori di ricerca - Naturale
* Motori di ricerca - Pagati
* Cerca parole chiave - Tutto
* Cerca parole chiave - Naturale
* Cerca parole chiave - A pagamento
* Dettagli attività Target
* Tempo trascorso nella pagina
* Fusi orari
* Domini di livello principali
* DMA USA
* Stati Uniti
* Numero visita
* Home page visitatori

## Dimensioni in base al contenuto supportate da Reporting e analisi e Analysis Workspace

### Video (Media Analytics)

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Contenuto | video |
| Segmento di contenuto | videosegmento |
| Tipo di contenuto | videocontenttype |
| Nome lettore annuncio | videoadplayername |
| Aggiungi in posizione contenitore | videoadinpod |
| Fotogrammi rilasciati | videoqoedroppedframecountevar |
| Errori | videoqoeerrorcountevar |
| Bitrate medio | videoqoebitrateaverageevar |
| Modifiche bitrate | videoqoebitratechangecountevar |
| Durata totale buffer | videoqoebuffertimevar |
| Eventi buffer | videoqoebuffercountevar |
| Ora di inizio | videoqetimetostartevar |
| Ad Pod | videoadpod |
| Percorso supporto | videopath |
| Annuncio | videoad |
| Nome lettore contenuti | videoplayername |
| Canale contenuto | videocanale |
| Capitolo | videocapitolo |
| Nome contenuto (variabile) | videoname |
| Lunghezza contenuto (variabile) | lunghezza video |
| Nome annuncio (variabile) | videoadname |
| Lunghezza annuncio (variabile) | videoadlength |
| Mostra le informazioni | videoshow |
| Stagione | videoconferenza |
| Episodio | videoepisodio |
| Rete | videonetwork |
| Mostra tipo | videoshowtype |
| Caricamenti annunci | videoadload |
| MVPD | videomvpd |
| Parte giorno | videodaypart |
| Inserzionista | videoinserzionista |
| ID campagna | videoadcampaign |
| Genere | videogenere |
| Tipo di flusso | videostreamtype |
| ID errore SDK lettore | videoqoeplayersderrori |
| ID errore esterni | videoqoeextneralerrori |
| Tipo di feed multimediale | videofeedtype |
| Percorso file multimediali | entryvideopath |
| Esci da percorso supporto | exitvideopath |
| Genere di ingresso | entryvideogenere |
| Tipo di uscita | exitvideogenere |
| ID errore SDK del lettore entry-level | entryvideoqoeplayersdkerror |
| Esci dagli ID errore SDK Player | exitvideoqoeplayersderrori |
| ID errore esterno voce | entryvideoqoeextneralerrori |
| Esci da ID errore esterni | exitvideoqoeextneralerrori |

### Adobe Social

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Termini | socialterm |
| Piattaforme/Proprietà social | socialcontentprovider |
| Autori | socialautore |
| Lingua | socialingua |
| Latitudine/longitudine | sociallatlong |
| Codici di tracciamento delle risorse | socialassettrackingcode |
| Proprietà Social | socialaccountandappids |
| ID post di proprietà | socialownedpostids |
| Definizioni social network di proprietà | socialinteractiontype |
| ID proprietà | socialownedproperty |
| Proprietà di proprietà e applicazione | socialownedProprietà yvsapp |
| Nome proprietà | socialownedpropertyName |
| Proprietà definizione di proprietà e post | socialownddefinition ionproperty yvspost |
| Tipo di visione della definizione di proprietà | socialowneddefinition insighype |
| Valore Insight definizione di proprietà | socialowneddefinition insightvalue |
| Metrica definizione di proprietà | socialowneddefinition |
| Risorsa | socialmediaid |

### SDK per dispositivi mobili

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Data primo avvio | mobileinstalldate |
| ID app | mobileappid |
| Numero di avvii | mobilelaunchnumber |
| Giorni dal primo utilizzo | mobiledayssincefirstuse |
| Giorni dall'ultimo utilizzo | mobiledayssincelastuse |
| Ora del giorno (SDK) | mobilehourofday |
| Giorno della settimana (SDK) | mobiledayofweek |
| Sistema operativo (SDK) | mobileosenenvironment |
| Giorni dall'ultimo aggiornamento | mobiledayssincelastupgrade |
| Avvii dall'ultimo aggiornamento | mobilelaunchessincelastupgrade |
| Nome dispositivo (SDK) | mobiledevice |
| Versione sistema operativo (SDK) | mobileosversion |
| Beacon principale | mobilebeaconmajor |
| Beacon minore | mobilebeaconminor |
| Beacon UUID | mobilebeaconuid |
| Prossimità beacon | mobilebeaconprossimità |
| Posizione (fino a 10 chilometri) | latlon1 |
| Posizione (fino a 100 m) | latlon23 |
| Posizione (fino a 1 m) | latlon45 |
| Nome del punto di interesse | puntiniere |
| Distanza dal centro del punto di interesse | puntofinterestdistanze |
| Precisione posizione | mobilesegnaposto |
| Categoria posto | mobileplacecategory |
| ID posizione | mobilesegnaposto |
| Beacon principale voce | entrymobilebeaconmajor |
| Esci dal beacon principale | exitmobilebeaconmajor |
| Beacon voce secondaria | entrymobilebeaconminor |
| Esci da beacon secondario | exitmobilebeaconminor |
| UUID beacon voce | entrymobilebeaconuid |
| Exit Beacon UUID | exitmobilebeaconuid |
| Prossimità beacon di ingresso | entrymobilebeaconprossimità |
| Esci da prossimità beacon | exitmobilebeaconprossimità |

### Adobe Advertising Cloud (AMO)

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| ID EF AMO | amo_ef_id |
| ID AMO | amo_cid |

### Activity Map

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Collegamento Activity Map Per Regione | clickmaplinkbyregion |
| Regione Activity Map | clickmapregion |
| Collegamento alla Activity Map | clickmaplink |
| Pagina della Activity Map | clickmappage |

### Integrazione Nielsen

Per ulteriori informazioni su come implementare questa integrazione, consulta [Nielsen partnership](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/nielsen-partnership.html).

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| Modello pubblicitario Nielsen | nielsenadmodel |
| Segmento Nielsen C | nielsensegmenta |
| Segmento Nielsen B | nielsensegmentb |
| Segmento Nielsen A | nielsensegmenta |
| Nielsen Content ID | nielsencontentid |
| Risorse/Programma Nielsen | nielsenasset |
| Nielsen VCID | nielsenvcid |
| Rifiuto Nielsen | nielsenoptout |
| ID client Nielsen + VCID | nielsenclientidvcid |
| ID client Nielsen | nielsenclientid |
| Rifiuto Nielsen | entrynielsenoptout |
| Esci da Nielsen Rifiuta | exitnielsenoptout |
| ID client Nielsen + VCID | entrynielsenclientidvcid |
| Esci da ID client Nielsen + VCID | exitnielsenclientidvcid |
| ID client Nielsen | entrynielsenclientid |
| Esci dall'ID client Nielsen | exitnielsenclientid |

### Adobe Experience Manager (AEM)

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| ID risorsa | aemassetid |
| Origine risorsa | aemassetsource |
| ID risorsa selezionata | aemclickedassetid |
| ID risorsa voce | entryaemassetid |
| Esci ID risorsa | exitaemassetid |

### Adobe Campaign

| Nome dimensione (visibile nell’interfaccia di Analytics) | ID dimensione (utilizzato nelle richieste API) |
|--- |--- |
| ID consegna eseguita da Adobe Campaign | ac_delivery_internal_name |
