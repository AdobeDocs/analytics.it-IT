---
description: Dati tabella che descrivono le colonne nel feed di dati.
keywords: Feed dati; colonne
seo-description: Dati tabella che descrivono le colonne nel feed di dati.
seo-title: Riferimento colonna dati
solution: Analytics
subtopic: feed dati
title: Riferimento colonna dati
topic: Reports & Analytics
uuid: 9042 a 274-7124-4323-8 cd 6-5 c 84 ab 3 eef 6 d
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Riferimento colonna dati

Utilizzare questa pagina per sapere quali dati sono contenuti in ciascuna colonna. La maggior parte delle implementazioni non utilizzano ogni colonna, pertanto è possibile fare riferimento a questa pagina per determinare quali colonne includere in un'esportazione di feed di dati.

> [!IMPORTANT] Per qualsiasi colonna specificata (ad esempio, una con 255 caratteri), un feed di dati può inviare caratteri aggiuntivi a causa dell'aggiunta di caratteri di escape di valori in una stringa. Tenete presente questo argomento se l'implementazione invia regolarmente valori che superano i limiti dei caratteri.

## Colonne, descrizioni e tipi di dati

> [!NOTE] La maggior parte delle colonne contiene una colonna simile con un prefisso di `post_`. Le colonne dei post contengono valori dopo logica lato server, regole di elaborazione e regole VISTA. Nella maggior parte dei casi, Adobe consiglia di utilizzare le colonne post.

| Nome colonna | Descrizione colonna | Tipo dati |
| --- | --- | --- |
| accept_ language | Elenca tutte le lingue accettate, come indicato nell'intestazione HTTP Accettazione-lingua in una richiesta di immagine. | char (20) |
| aemassetid | Una variabile con più valori corrispondente a (GUID) di un set di risorse Adobe Experience Manager. Incrementi Eventi impression. | text |
| aemassetsource | Identifica l'origine dell'evento di risorsa. Utilizzato in Adobe Experience Manager. | varchar (255) |
| aemclickedassetid | ID risorsa di una risorsa Adobe Experience Manager. Incrementa eventi. | varchar (255) |
| browser | ID numerico del browser. Fa riferimento alla tabella di ricerca browser. tsv. | int unsigned |
| browser_ height | Altezza in pixel della finestra del browser. | smallint unsigned |
| browser_ width | Larghezza in pixel della finestra del browser. | smallint unsigned |
| c_ color | Profondità di bit della palette colori. Utilizzato come parte del calcolo della dimensione Profondità colore. Utilizza la funzione javascript. colordepth (). | char (20) |
| campaign | Variabile utilizzata nella dimensione Codice di tracciamento. | varchar (255) |
| operatore | Variabile di integrazione Adobe Advertising Cloud. Specifica il gestore di dispositivi mobili. Fa riferimento alla tabella di ricerca del vettore. | varchar (100) |
| channel | Variabile utilizzata nella dimensione Sezioni del sito. | varchar (100) |
| click_ action | Non più utilizzato. Indirizzo di collegamento collegato nello strumento Clickmap precedente. | varchar (100) |
| click_ action_ type | Non più utilizzato. Tipo di collegamento dello strumento Clickmap precedente.<br>0: URL HREF<br>1: ID personalizzato<br>2: Evento javascript onclick<br>3: Elemento modulo | tinyint unsigned |
| click_ context | Non più utilizzato. Nome pagina in cui si è verificato il collegamento. Parte dello strumento Clickmap precedente. | varchar (255) |
| click_ context_ type | Non più utilizzato. Indica se click_ context aveva un nome di pagina o un nome predefinito all'URL della pagina.<br>0: URL pagina<br>1: Nome pagina | tinyint unsigned |
| click_ sourceid | Non più utilizzato. ID numerico per la posizione nella pagina del collegamento selezionato. Parte dello strumento Clickmap precedente. | int unsigned |
| click_ tag | Non più utilizzato. Tipo di elemento HTML su cui è stato fatto clic. | char (10) |
| clickmaplink | Collegamento Activity Map | varchar (255) |
| clickmaplinkbyarea | Collegamento Mappa dell'attività per regione | varchar (255) |
| clickmappage | Pagina Activity Map | varchar (255) |
| clickmapregion | Area Activity Map | varchar (255) |
| code_ ver | Versione libreria appmeasurement utilizzata per compilare e inviare la richiesta di immagine. | char (16) |
| color | ID profondità colore in base al valore della colonna c_ color. Fa riferimento alla tabella di ricerca color_ depth. tsv. | smallint unsigned |
| connection_ type | ID numerico che rappresenta il tipo di connessione. Variabile utilizzata nella dimensione Tipo di connessione. Fa riferimento alla tabella di ricerca connection_ type. tsv. | tinyint unsigned |
| cookie | Variabile utilizzata nella dimensione Supporto cookie.<br>Y: Enabledn<br>: Disabledu<br>: Sconosciuto | char (1) |
| paese | ID numerico da cui proveniva l'hit. Partner Adobe con Digital Dispaty per far corrispondere l'indirizzo IP al paese. Utilizza la ricerca country. tsv. | smallint unsigned |
| ct_ connect_ type | Correlata alla colonna connection_ type. I valori più comuni sono LAN/Wifi, Mobile Carrier e Modem. | char (20) |
| curr_ factor | Determina la posizione decimale della valuta e viene utilizzata per la conversione valuta. Ad esempio, USD utilizza due posizioni decimali, quindi il valore di colonna sarà 2. | tinyint |
| curr_ rate | Il tasso di scambio al verificarsi della transazione. I partner Adobe con XE consentono di determinare il tasso di cambio del giorno corrente. | decimal (24,12) |
| currency | Codice valuta utilizzato durante la transazione. | char (8) |
| cust_ hit_ time_ gmt | Solo suite per report abilitate per marca temporale. Marca temporale inviata con l'hit, basata in ora Unix. | int |
| cust_ visid | Se un ID visitatore personalizzato è impostato, viene popolato in questa colonna. | varchar (255) |
| daily_ visitor | Flag per determinare se l'hit è un nuovo visitatore giornaliero. | tinyint unsigned |
| date_ time | L'ora dell'hit in formato leggibile, in base al fuso orario della suite di rapporti. | datetime |
| domain | Variabile utilizzata nella dimensione Dominio. Basato sul provider di servizi Internet (ISP) dell'utente. | varchar (100) |
| duplicate_ events | Elenca ogni evento che è stato conteggiato come duplicato. | varchar (255) |
| duplicate_ purchase | Flag indica che l'evento di acquisto per questo hit deve essere ignorato perché è un duplicato. | tinyint unsigned |
| duplicato_ from | Utilizzato solo nelle suite di rapporti contenenti regole di copia vista. Indica la suite di rapporti dalla quale è stata copiata l'hit. | varchar (40) |
| ef_ id | ef_ id utilizzato nelle integrazioni Adobe Advertising Cloud. | varchar (255) |
| evar 1 - evar 250 | Variabili personalizzate 1-250. Ciascuna organizzazione utilizza evar in modo diverso. La posizione migliore per ottenere informazioni su come l'azienda popola le rispettive evar sarebbe un documento di progettazione della soluzione specifico per l'organizzazione. | varchar (255) |
| event_ list | Elenco separato da virgole degli ID numerici che rappresentano gli eventi attivati. Include eventi predefiniti e eventi personalizzati 1-1000. Utilizza la ricerca event. tsv. | text |
| exclude_ hit | Flag che indica che l'hit è escluso dai rapporti. La colonna visit_ num non viene incrementata per gli hit esclusi.<br>1: Non utilizzato. Parte di una funzione scaricata.<br>2: Non utilizzato. Parte di una funzione scaricata.<br>3: Non più utilizzato. User agent exclusion<br>4: Exclusion based on IP address<br>5: Vital hit info missing, such as page_url, pagename, page_event, or event_list<br>6: JavaScript did not correctly process hit<br>7: Account-specific exclusion, such as in a VISTA rules<br>8: Not used. Esclusione specifica dell'account.<br>9: Non utilizzato. Parte di una funzione scaricata.<br>10: Codice valuta non valido<br>11: Hit mancante una marca temporale su una suite di rapporti solo marca temporale, o su un hit contenuto in una marca temporale su una suite di rapporti non marca temporale<br>12: Non utilizzato. Parte di una funzione scaricata.<br>13: Non utilizzato. Parte di una funzione scaricata.<br>14: Hit di destinazione che non corrisponde a un hit Analytics<br>15: Attualmente non utilizzato.<br>16: Hit di Advertising Cloud che non corrisponde a un hit Analytics | tinyint unsigned |
| first_ hit_ page_ url | Il primo URL del visitatore. | varchar (255) |
| first_ hit_ pagename | Variabile utilizzata nella dimensione Pagina di immissione. Il nome della pagina di immissione originale del visitatore. | varchar (100) |
| first_ hit_ ref_ domain | Variabile utilizzata nella dimensione Dominio di riferimento originale. Basato su first_ hit_ referrer. Il primo dominio di riferimento del visitatore. | varchar (100) |
| first_ hit_ ref_ type | ID numerico che rappresenta il tipo di referente del primo referente del visitatore. Utilizza la ricerca referrer_ type. tsv. | tinyint unsigned |
| first_ hit_ referrer | Il primo URL di riferimento del visitatore. | varchar (255) |
| first_ hit_ time_ gmt | Marca temporale del primo hit del visitatore in ora Unix. | int |
| geo_ city | Nome della città da cui proveniva l'hit, in base all'IP. Partner Adobe con l'Edk digitale per far corrispondere l'indirizzo IP a città. | char (32) |
| geo_ country | Abbreviazione del paese da cui proveniva l'hit, basato su IP. Partner Adobe con Digital Dispaty per far corrispondere l'indirizzo IP al paese. | char (4) |
| geo_ dma | ID numerico dell'area demografica da cui proveniva l'hit, in base all'IP. Partner Adobe con Digital Dispaty per far corrispondere l'indirizzo IP all'area demografica. | int unsigned |
| geo_ region | Nome dello stato o della regione da cui proviene l'hit, basato su IP. Partner Adobe con Digital Dispaty per far corrispondere l'indirizzo IP allo stato/regione. | char (32) |
| geo_zip | Il codice zip da cui proviene l'hit, basato su IP. Partner Adobe con l'Edk digitale per far corrispondere l'indirizzo IP al codice postale. | varchar (16) |
| hier 1 - hier 5 | Utilizzato dalle variabili gerarchiche. Contiene un elenco delimitato di valori. Il delimitatore viene scelto nelle impostazioni della suite di rapporti. | varchar (255) |
| hit_ source | Indica da quale sorgente proveniva l'hit. <br>1: Richiesta di immagine standard senza marca temporale <br>2: Richiesta immagine standard con marca temporale <br>3: Caricamento live source source with timestamp <br>4: Not used <br>5: Caricamento origine dati generico <br>6: Caricamento completo sorgente dati <br>7: Transactionid data source upload <br>8: Non più utilizzato; Versioni precedenti delle origini dati Adobe Advertising Cloud <br>9: Non più utilizzato; Metriche di riepilogo di Adobe Social | tinyint unsigned |
| hit_ time_ gmt | L'indicatore temporale dei server di raccolta dati Adobe ha ricevuto l'hit, basato su ora Unix. | int |
| hitid_ high | Utilizzato insieme a hitid_ low per identificare in modo univoco un hit. | bigint unsigned |
| hitid_ low | Utilizzato insieme a hitid_ high per identificare in modo univoco un hit. | bigint unsigned |
| homepage | Non più utilizzato. Indicato se l'URL corrente è la pagina iniziale del browser. | char (1) |
| hourful_ visitor | Flag per determinare se l'hit è un nuovo visitatore oraria. | tinyint unsigned |
| ip | Indirizzo IP, in base all'intestazione HTTP della richiesta di immagine. | char (20) |
| ip2 | Non utilizzato. Variabile di riferimento retroend per le suite di rapporti contenenti regole VISTA basate sull'indirizzo IP. | char (20) |
| j_ jscript | Versione di javascript supportata dal browser. | char (5) |
| java_ enabled | Flag che indica se Java è abilitato. <br>Y: Attivato <br>N: Disattivato <br>U: Sconosciuto | char (1) |
| javascript | ID di ricerca della versione javascript, basato su j_ jscript. Utilizza la tabella di ricerca. | tinyint unsigned |
| language | ID numerico di lingua. Utilizza la tabella di ricerca languages. tsv. | smallint unsigned |
| last_ hit_ time_ gmt | Marca temporale (in tempo Unix) dell'hit precedente. Utilizzato per calcolare la dimensione Giorni dall'ultima visita. | int |
| last_ purchase_ num | Variabile utilizzata nella dimensione Fedeltà cliente. Indica il numero di acquisti precedenti effettuati dal visitatore. <br>0: Nessun acquisto precedente (non cliente) <br>1: acquisto prima del 1 (nuovo cliente) <br>2: 2 acquisti precedenti (ritorno cliente) <br>3: 3 o più acquisti precedenti (clienti fedeli) | int unsigned |
| last_ purchase_ time_ gmt | Utilizzato nella dimensione Giorni dall'ultimo acquisto. Marca temporale (in tempo Unix) dell'ultimo acquisto eseguito. Per gli acquisti per la prima volta e i visitatori che non hanno effettuato un acquisto prima, questo valore è 0. | int |
| latlon1 | Posizione (fino a 10 chilometri) | varchar (255) |
| latlon23 | Posizione (fino a 100 m) | varchar (255) |
| latlon45 | Posizione (fino a 1 m) | varchar (255) |
| È stata aggiunta la colonna mc_audiences | Elenco degli ID del segmento Audience Manager a cui appartiene il visitatore. | text |
| mcvisid | ID visitatore Experience Cloud. Numero a 128 bit composto da due numeri di 64 bit concatenati a 19 cifre. | varchar (255) |
| mobile_ id | Se l'utente utilizza un dispositivo mobile, l'ID numerico del dispositivo. | int |
| mobileaction | Azione mobile. Raccolta automatica quando trackaction viene invocato in Mobile Services. Consente il percorso automatico dell'azione nell'app. | varchar (100) |
| mobileappid | ID app mobile. Stores the application name and version in the following format:[AppName] [BundleVersion] | varchar (255) |
| mobileappperformanceappid | Utilizzato nel connettore dati Apteligent. L'ID app utilizzato in Apteligent. | varchar (255) |
| mobileappperformancecrashid | Utilizzato nel connettore dati Apteligent. L'ID anomalo utilizzato in Apteligent. | varchar (255) |
| mobileappstoreobjectid | Utilizzato nel connettore dati Appfigures. ID oggetto app store | varchar (255) |
| mobilebeaconmajor | Beacon di Mobile Services | varchar (100) |
| mobilebeacon | Beacon di Mobile Services | varchar (100) |
| mobilebeaconproximity | Prossimità di Mobile Services | varchar (255) |
| mobilebeaconuuid | UUCON di Mobile Services Beacon | varchar (100) |
| mobilecampaigncontent | Nome o ID del contenuto in cui è stato visualizzato il collegamento. Viene compilata dalla funzione Acquisizione da app mobile. | varchar (255) |
| mobilecampaignmedium | Canale di marketing, ad esempio banner o e-mail. Viene compilata dalla funzione Acquisizione da app mobile. | varchar (255) |
| mobilecampaignname | Nome della campagna, memorizzato anche nella variabile della campagna. Viene compilata dalla funzione Acquisizione da app mobile. | varchar (255) |
| mobilecampaignsource | Referente originale, ad esempio una newsletter o una rete social media. Viene compilata dalla funzione Acquisizione da app mobile. | varchar (255) |
| mobilecampaignterm | Keyword a pagamento o altri termini di cui si desidera tenere traccia con questa acquisizione. Viene compilata dalla funzione Acquisizione da app mobile. | varchar (255) |
| mobiledayofweek | Numero della settimana in cui è stata avviata l'app. | varchar (255) |
| mobiledayssincefirstuse | Numero di giorni dall'esecuzione dell'app per la prima volta. | varchar (255) |
| mobiledayssincelastupgrade | Raccolto dalla variabile di dati di contesto a. dayssincelastupgrade. Il numero di giorni passati dalla sessione precedente. | varchar (255) |
| mobiledayssincelastuse | Numero di giorni dall'ultima esecuzione dell'app. | varchar (255) |
| mobiledeeplinkid | Collected from the context data variable a.<span>deeplink</span>.id. Utilizzato nei rapporti di acquisizione come identificatore per il collegamento di acquisizione mobile. | varchar (255) |
| mobiledevice | Nome del dispositivo mobile. Su iOS, viene memorizzato come stringa di 2 cifre separate da virgola. Il primo numero rappresenta la generazione del dispositivo, mentre il secondo numero rappresenta la famiglia di dispositivi. | varchar (255) |
| mobilehourofday | Definisce l'ora del giorno in cui è stata avviata l'app. Segue il formato numerico a 24 ore. | varchar (255) |
| mobileinstall data | Data di installazione per dispositivi mobili. Fornisce la data della prima volta che un utente apre l'app mobile. | varchar (255) |
| mobilelaunchessincelastupgrade | Raccolto dalla variabile di dati di contesto a. launchessinceupgrade. Segnala il numero di avvii dall'ultimo aggiornamento. | varchar (255) |
| mobilelaunchnumber | Incrementa di una volta l'avvio dell'app mobile. | varchar (255) |
| mobileltv | Non più utilizzato. Viene compilata dai metodi trackLifetimeValue. | varchar (255) |
| mobilemessagebuttonname | Collected from the context data variable a.<span>message</span>.button.id. Utilizzato per i messaggi in-app per identificare il pulsante che ha chiuso il messaggio. | varchar (100) |
| mobilemessageid | ID messaggio in-app | varchar (255) |
| mobilemessageonline | Messaggio in-app online | varchar (255) |
| mobilemessagepushoptin | Raccolto dalla variabile di dati contestuali a. push. optin. Impostato su "true" quando l'utente accede a messaggi push; altrimenti il valore è "false". | varchar (255) |
| mobilemessagepushpayloadid | Raccolto dalla variabile di dati di contesto a. push. payloadid. Utilizzato nei messaggi push come identificatore payload. | varchar (255) |
| mobileosenvironment | Raccolto dalla variabile di dati di contesto a. osenvironment. Ambiente OS, ad esempio Android o iOS. | varchar (255) |
| mobileosversion | Versione del sistema operativo Mobile Services | varchar (255) |
| precisione mobileplace | Raccolto dalla variabile di dati di contesto a. loc. acc. Indica la precisione del GPS in metri al momento della raccolta. | varchar (255) |
| mobileplacecategory | Raccolto dalla variabile di dati di contesto a. loc. category. Descrive la categoria di una posizione specifica. | varchar (255) |
| mobileplaceid | Collected from the context data variable a.<span>loc</span>.id. Identificatore per un determinato punto di interesse. | varchar (255) |
| contenuto mobilerelaunchcampaign | Contenuto di Mobile Services avviata | varchar (255) |
| mobilerelaunchcampaignmedium | Media Services launch medium | varchar (255) |
| mobilerelaunchcampaignsource | Sorgente di avvio di Mobile Services | varchar (255) |
| mobilerelaunchcampaign | Termine di avvio di Mobile Services | varchar (255) |
| mobilerelaunchcampaigntrackingcode | Raccolto dalla variabile di dati di contesto a. launch. campaign. trackingcode. Utilizzato nell'acquisizione come codice di tracciamento per la campagna di lancio. | varchar (255) |
| mobileresoluzione | Risoluzione del dispositivo mobile. Altezza x altezza, in pixel. | varchar (255) |
| monthly_ visitor | Flag che indica che il visitatore è univoco per il mese corrente. | tinyint unsigned |
| mvvar 1 - mvvar 3 | Elenca i valori delle variabili. Contiene un elenco delimitato di valori personalizzati a seconda dell'implementazione. | text |
| namespace | Non utilizzato. Parte di una funzione bloccata, molti anni fa. | varchar (50) |
| new_ visit | Flag che determina se l'hit corrente è una nuova visita. Impostato dai server Adobe dopo 30 minuti di inattività delle visite. | tinyint unsigned |
| os | ID numerico che rappresenta il sistema operativo del visitatore. Basato sulla colonna user_ agent. Utilizza la ricerca OS. | int unsigned |
| p_ plugins | Non più utilizzato. Elenco dei plug-in disponibili per il browser. Utilizzato la funzione javascript navigator. plugins (). | text |
| page_ event | Il tipo di hit inviato nella richiesta immagine (hit standard, collegamento di download, collegamento personalizzato, collegamento uscita). | tinyint unsigned |
| page_ event_ var 1 | Utilizzato solo nelle richieste di tracciamento delle immagini. L'URL del collegamento di download, del collegamento di uscita o del collegamento personalizzato. | text |
| page_ event_ var 2 | Utilizzato solo nelle richieste di tracciamento delle immagini. Il nome personalizzato (se specificato) del collegamento. | varchar (100) |
| page_ event_ var 3 | Non più utilizzato. Dati del modulo Sondaggio e Contenuti multimediali. Sono stati inseriti rapporti video legacy nelle versioni precedenti di Adobe Analytics. | text |
| page_ type | Utilizzato per compilare la dimensione Pagine non trovata, utilizzata esclusivamente per 404 pagine. Questa variabile deve essere vuota o contenere "errorpage". | char (20) |
| page_ url | L'URL dell'hit. Non utilizzato nel collegamento per il tracciamento delle immagini. | varchar (255) |
| pagename | Utilizzato per compilare la dimensione Pagine. Se la variabile pagename è vuota, Analytics utilizza invece page_ url. | varchar (100) |
| paid_ search | Flag impostato se l'hit corrisponde al rilevamento della ricerca a pagamento. | tinyint unsigned |
| partner_ plugins | Non utilizzato. Parte di una funzione bloccata, molti anni fa. | varchar (255) |
| persistent_ cookie | Utilizzato dalla dimensione Supporto cookie persistente. Indica se il visitatore supporta i cookie che non vengono eliminati dopo ogni hit. | char (1) |
| plugins | Non più utilizzato. Elenco di ID numerici che corrispondono ai plug-in disponibili nel browser. Utilizza la ricerca plugins. tsv. | varchar (180) |
| pointofinterest | Nome del punto di interesse di Mobile Services | varchar (255) |
| pointofinterestdistance | Distanza di Mobile Services dal centro dei punti di interesse | varchar (255) |
| post_ columns | Contiene il valore utilizzato in genere nei report. Ogni colonna del post viene compilata dopo logica lato server, regole di elaborazione e regole VISTA. Nella maggior parte dei casi, Adobe consiglia di utilizzare le colonne post. | Vedere la rispettiva colonna non post |
| prev_ page | Non utilizzato. Identificatore proprietario Adobe della pagina precedente. | int unsigned |
| product_ list | Elenco prodotti trasmesso tramite la variabile products. I prodotti sono delimitati da virgole mentre le singole proprietà del prodotto sono delimitate da punto e virgola. | text |
| product_ merchandising | Non utilizzato. Utilizzare invece product_ list. | text |
| prop 1 - prop 75 | Variabili di traffico personalizzate 1-75. | varchar (100) |
| purchaseid | Identificatore univoco per un acquisto, come impostato tramite la variabile s_ purchaseid. Utilizzato dalla colonna duplicate_ purchase. | char (20) |
| trimestrale | Flag per determinare se l'hit è un nuovo visitatore trimestrale. | tinyint unsigned |
| ref_ domain | In base alla colonna referrer. Il dominio di riferimento dell'hit. | varchar (100) |
| ref_ type | Un ID numerico che rappresenta il tipo di riferimento per l'hit.<br>1: All'interno del sito<br>2: Altri siti Web <br>3: Motori di ricerca <br>4: Disco rigido <br>5: USENET <br>6: Typed/Bookmarked (no referrer) <br>7: Email <br>8: Nessun javascript <br>9: Social Network | tinyint unsigned |
| referrer | URL pagina della pagina precedente. | varchar (255) |
| resolution | ID numerico che rappresenta la risoluzione del monitor. Compila la dimensione della risoluzione monitor. Utilizza la tabella di ricerca risoluzione. tsv. | smallint unsigned |
| s_ kwcid | ID parola chiave utilizzato nelle integrazioni Adobe Advertising Cloud. | varchar (255) |
| s_ resolution | Valore di risoluzione dello schermo grezzo. Raccolto utilizzando la funzione javascript dello schermo. width x. height. | char (20) |
| sample_ hit | Non più utilizzato. Precedentemente utilizzato per il campionamento in Analisi ad hoc. | char (1) |
| search_ engine | ID numerico che rappresenta il motore di ricerca che ha indirizzato il visitatore al sito. Utilizza la ricerca search_ engine. tsv. | smallint unsigned |
| search_ page_ num | Utilizzato dalla dimensione di classificazione Tutte le pagine. Indica la pagina dei risultati della ricerca su cui il sito è apparso prima che l'utente faccia clic sul sito. | smallint unsigned |
| secondary_ hit | Flag che tiene traccia degli hit secondari. Generalmente viene originata da tag con più suite e regole VISTA che copia gli hit. | tinyint unsigned |
| service | Non utilizzato. Utilizzare invece page_ event. | char (2) |
| socialaccountandappids | Non più utilizzato. Account social e ID app | varchar (255) |
| socialassettrackingcode | Non più utilizzato. Variabile della campagna social | varchar (255) |
| socialauthor | Non più utilizzato. Variabile Autori social | varchar (255) |
| socialcontentprovider | Non più utilizzato. Piattaforme/proprietà social | varchar (255) |
| socialinteractiontype | Non più utilizzato. Tipo interazione social | varchar (255) |
| sociallanguage | Non più utilizzato. Lingua social | varchar (255) |
| sociallatlong | Non più utilizzato. Latitudine social/longitudine | varchar (255) |
| socialowneddefinitioninsighttype | Non più utilizzato. Tipo di descrizione definizione per social network | varchar (255) |
| socialowneddefinitioninsightvalue | Non più utilizzato. Valore di insight definito per social network | varchar (255) |
| socialowneddefinitionmetric | Non più utilizzato. Metrica di definizione di social network | varchar (255) |
| socialowneddefinitionpropertyvspost | Non più utilizzato. Proprietà di definizione di proprietà social rispetto a post | varchar (255) |
| socialownedpostids | Non più utilizzato. L'ID del post di proprietà social | varchar (255) |
| socialownedpropertyid | Non più utilizzato. ID proprietà di Social | varchar (255) |
| socialownedpropertyname | Non più utilizzato. Nome proprietà di social | varchar (255) |
| socialownedpropertypropertyvsapp | Non più utilizzato. Proprietà di proprietà social rispetto all'app | varchar (255) |
| state | Variabile stato. | varchar (50) |
| stats_ server | Non d'uso. Server interno Adobe che ha elaborato l'hit. | char (30) |
| t_ time_ info | Ora locale per il visitatore. Formato: M/G/AAAA HH: MM: Mese SS (0-11, 0 = gennaio) Offset fuso orario (in minuti) | varchar (100) |
| tnt | Utilizzato nelle integrazioni di Adobe Target. | text |
| tnt_ action | Utilizzato nelle integrazioni di Adobe Target. | text |
| tnt_ post_ vista | Non più utilizzato. Utilizzate invece post_ tnt. | text |
| transactionid | Un identificatore univoco in cui vari punti dati possono essere caricati successivamente tramite origini dati. | text |
| truncated_ hit | Un flag che indica che la richiesta di immagine è stata troncata. Indica che è stato ricevuto un hit parziale. <br>Y: Hit was truncated; hit parziale ricevuto <br>N: Hit was not truncated; hit completo ricevuto | char (1) |
| ua_ color | Non più utilizzato. Precedentemente utilizzato come fallback per la profondità del colore. | char (20) |
| ua_ os | Non più utilizzato. Precedentemente utilizzato come fallback per il sistema operativo. | char (80) |
| ua_ pixel | Non più utilizzato. Precedentemente utilizzato come fallback per l'altezza e la larghezza del browser. | char (20) |
| user_ agent | Stringa agente utente inviata nell'intestazione HTTP della richiesta di immagine. | text |
| user_ hash | Non d'uso. Hash sull'ID della suite di rapporti. Utilizzate invece il nome utente. | int unsigned |
| user_ server | Variabile utilizzata nella dimensione Server. | varchar (100) |
| userid | Non d'uso. L'ID numerico dell'ID della suite di rapporti. Utilizzate invece il nome utente. | int unsigned |
| username | L'ID suite di rapporti per l'hit. | char (40) |
| va_closer_detail | Variabile utilizzata nella dimensione Ultimo tocco. | varchar (255) |
| va_ closer_ id | ID numerico che identifica la dimensione Ultimo canale touch. La ricerca di questo ID si trova in Marketing Channel Manager. | tinyint unsigned |
| va_finder_detail | Variabile utilizzata nella dimensione Primo tocco. | varchar (255) |
| va_ finder_ id | ID numerico che identifica la dimensione Primo contatto. La ricerca di questo ID si trova in Marketing Channel Manager. | tinyint unsigned |
| va_ instance_ event | Flag per identificare le istanze di Marketing Channel. Utilizzato dalla metrica Last Touch Instances dell'ultimo canale di marketing. | tinyint unsigned |
| va_ new_ engagement | Flag per identificare i nuovi engagement di Marketing. Utilizzato dalla metrica New Engagement (Nuovi engagement). | tinyint unsigned |
| video | Contenuto video | varchar (255) |
| videoad | Nome annuncio video | varchar (255) |
| videoadinpod | Annuncio video nella posizione del contenitore | varchar (255) |
| videoadlength | Lunghezza annuncio video | varchar (255) |
| videoadload | Caricamenti di annunci video | varchar (255) |
| videoadname | Nome annuncio video | varchar (255) |
| videoadplayername | Nome del lettore video | varchar (255) |
| videoadpod | Contenitore annunci video | varchar (255) |
| videoadvertiser | Inserzionista video | varchar (255) |
| videoaudioalbum | Album audio video | varchar (255) |
| videoaudioartist | Artista audio | varchar (255) |
| videoaudioauthor | Autore audio | varchar (255) |
| videoaudiolabel | Etichetta audio video | varchar (255) |
| videoaudiopublisher | Editore audio video | varchar (255) |
| videoaudiostation | Stazione audio video | varchar (255) |
| webampaign | Campagna video | varchar (255) |
| videochannel | Canale video | varchar (255) |
| videocapitolo | Nome capitolo video | varchar (255) |
| videocontenttype | Tipo di contenuto video. Impostare automaticamente il video per tutte le visualizzazioni video | varchar (255) |
| videodaypart | Parte del video | varchar (255) |
| videoepisodio | Episodio video | varchar (255) |
| videofeedtype | Tipo di feed video | varchar (255) |
| videogenre | Genere video | text |
| videolength | Lunghezza video | varchar (255) |
| videomvpd | Video MVPD | varchar (255) |
| videoname | Nome video | varchar (255) |
| videonetwork | Rete video | varchar (255) |
| videopath | Percorso video | varchar (100) |
| videoplayername | Nome lettore video | varchar (255) |
| videoqoebitrateaverageevar | Bitrate medio qualità video | varchar (255) |
| videoqoebitratechangecountevar | Conteggio delle modifiche alla qualità video | varchar (255) |
| videoqoebuffercountevar | Numero di buffer di qualità video | varchar (255) |
| videoqoebuffertimeevar | Tempo di bufferizzazione video | varchar (255) |
| videoqoedroppedframecountevar | Conteggio fotogrammi con qualità video | varchar (255) |
| videoqoeerrorcountevar | Conteggio errori qualità video | varchar (255) |
| videoqoeextneralerrors | Errori esterni di qualità video | text |
| videoqoeplayersdkerrors | Errori SDK di qualità video | text |
| videoqoetimetostartevar | Tempo di inizio del video | varchar (255) |
| videoseason | Stagione video | varchar (255) |
| videosegmento | Segmento video | varchar (255) |
| videoshow | Video mostra | varchar (255) |
| videoshowtype | Tipo di visualizzazione video | varchar (255) |
| videostreamtype | Tipo di flusso video | varchar (255) |
| visid_ high | Utilizzata in combinazione con visid_ low per identificare in modo univoco una visita. | bigint unsigned |
| visid_ low | Utilizzato insieme a visid_ high per identificare in modo univoco una visita. | bigint unsigned |
| visid_ new | Flag per identificare se l'hit contiene un ID visitatore appena generato. | char (1) |
| visid_ timestamp | Se l'ID visitatore è stato appena generato, fornisce l'indicatore temporale (in ora Unix) di quando è stato generato l'ID visitatore. | int |
| visid_ type | ID numerico che rappresenta il metodo utilizzato per identificare il visitatore. <br>0: Personalizzato visitorid <br>1: IP e fallback agente utente <br>2: Intestazione utente HTTP Mobile <br>3: Valore cookie legacy (s_ vi) <br>4: Valore cookie di fallback (s_ fid) <br>5: Servizio identità | tinyint unsigned |
| visit_ keywords | Variabile utilizzata nella dimensione Parola chiave Cerca. Questa colonna utilizza un limite di caratteri non standard per contenere la logica di back-end utilizzata da Adobe. | varchar (244) |
| visit_ num | Variabile utilizzata nella dimensione Numero visita. Inizia da 1 e incrementa ogni volta che inizia una nuova visita per visitatore. | int unsigned |
| visit_page_num | Variabile utilizzata nella dimensione Profondità hit. Aumenta di 1 per ogni hit generato dall'utente. Reimposta ogni visita. | int unsigned |
| visit_ ref_ domain | In base alla colonna visit_ referrer. Il primo dominio di riferimento della visita. | varchar (100) |
| visit_ ref_ type | ID numerico che rappresenta il tipo di referente del primo referente della visita. Utilizza la tabella di ricerca referrer_ type. tsv. | tinyint unsigned |
| visit_ referrer | Il primo referente della visita. | varchar (255) |
| visit_ search_ engine | ID numerico del primo motore di ricerca della visita. Utilizza la tabella di ricerca search_ engine. tsv. | smallint unsigned |
| visit_ start_ page_ url | Il primo URL della visita. | varchar (255) |
| visit_ start_ pagename | Il primo Nome pagina della visita. | varchar (100) |
| visit_start_time_gmt | Marca temporale (in tempo Unix) del primo hit della visita. | int |
| weekly_ visitor | Flag per determinare se l'hit è un nuovo visitatore settimanale. | tinyint unsigned |
| annual_ visitor | Flag per determinare se l'hit è un nuovo visitatore annuale. | tinyint unsigned |
| zip | Utilizzato per compilare la dimensione Codice postale. | varchar (50) |