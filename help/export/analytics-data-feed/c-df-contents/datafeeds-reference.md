---
description: Dati di tabella che descrivono le colonne nel feed di dati.
keywords: Data Feed;columns
seo-description: Dati di tabella che descrivono le colonne nel feed di dati.
seo-title: Riferimento colonna dati
solution: Analytics
subtopic: feed di dati
title: Riferimento colonna dati
topic: Reports and Analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: 2ea071c4d4f675c74770396610219d405a07a0e1

---


# Riferimento colonna dati

Use this page to learn what data is contained in each column. Most implementations don't use every column, so this page can be referenced when determining which columns to include in a data feed export.

> [!IMPORTANT] For any given column (for instance, one that is defined as 255 characters), a data feed can send additional characters due to the addition of characters escaping values in a string. Keep this topic in mind if your implementation regularly sends values that exceed character limits.

## Columns, Descriptions, and Data Types

> [!NOTE] Most columns contain a similar column with a prefix of . `post_` Post columns contain values after server-side logic, processing rules, and VISTA rules. Adobe recommends using post columns in most cases.

| Nome colonna | Column description | Tipo di dati |
| --- | --- | --- |
| accept_language | Lists all accepted languages, as indicated in the Accept-Language HTTP header in an image request. | char(20) |
| aemassetid | A multi-value variable corresponding to Asset ID's (GUID's) of a set of Adobe Experience Manager Assets. Incrementa Gli Eventi Di Impressione. | text |
| aemassetsource | Identifica l'origine dell'evento della risorsa. Utilizzata in Adobe Experience Manager. | varchar(255) |
| aemclickedassetid | ID risorsa di una risorsa Adobe Experience Manager. Incrementi Fare Clic Su Eventi. | varchar(255) |
| browser | ID numerico del browser. Fa riferimento alla tabella di ricerca browser.tsv. | int non firmato |
| browser_height | Altezza in pixel della finestra del browser. | numero piccolo senza segno |
| browser_width | Larghezza in pixel della finestra del browser. | smallint unsigned |
| c_color | Bit depth of the color palette. Used as part of calculating the Color Depth dimension. Utilizza la funzione JavaScript screen.colorDepth(). | char(20) |
| campaign | Variabile utilizzata nella dimensione Codice tracciamento. | varchar(255) |
| vettore | Variabile di integrazione di Adobe Advertising Cloud. Specifica il vettore del dispositivo mobile. Fa riferimento alla tabella di ricerca del vettore. | varchar(100) |
| channel | Variabile utilizzata nella dimensione Sezioni del sito. | varchar(100) |
| click_action | Non più utilizzato. Address of linked clicked in the legacy Clickmap tool. | varchar(100) |
| click_action_type | Non più utilizzato. Tipo di collegamento dello strumento ClickMap precedente.<br>0: URL<br>1 HREF: ID<br>personalizzato 2: Evento<br>3 JavaScript onClick: Elemento modulo | tinyint non firmato |
| click_context | Non più utilizzato. Nome pagina in cui si è verificato il clic sul collegamento. Parte dello strumento ClickMap legacy. | varchar(255) |
| click_context_type | Non più utilizzato. Indica se click_context ha un nome di pagina o se è stato impostato automaticamente sull’URL della pagina.<br>0: URL<br>pagina 1: Nome pagina | tinyint non firmato |
| click_sourceid | Non più utilizzato. ID numerico per la posizione sulla pagina del collegamento selezionato. Parte dello strumento ClickMap legacy. | int non firmato |
| click_tag | Non più utilizzato. Tipo di elemento HTML su cui è stato fatto clic. | char(10) |
| clickmaplink | Collegamento Activity Map | varchar(255) |
| clickmaplinkbyregion | Collegamento Activity Map per regione | varchar(255) |
| clickmappage | Activity Map | varchar(255) |
| clickmapregion | Area Activity Map | varchar(255) |
| code_ver | Versione della libreria AppMeasurement utilizzata per compilare e inviare la richiesta di immagine. | char(16) |
| color | ID profondità colore in base al valore della colonna c_color. Fa riferimento alla tabella di ricerca color_deep.tsv. | numero piccolo senza segno |
| connection_type | ID numerico che rappresenta il tipo di connessione. Variabile utilizzata nella dimensione Tipo di connessione. Fa riferimento alla tabella di ricerca connection_type.tsv. | tinyint non firmato |
| cookie | Variabile utilizzata nella dimensione Cookie Support.<br>Y:<br>EnabledN:<br>DisabledU: Sconosciuto | char(1) |
| country | ID numerico che rappresenta il paese da cui proveniva l’hit. Adobe collabora con Digital Inviate per far corrispondere l'indirizzo IP al Paese. Utilizza la ricerca country.tsv. | numero piccolo senza segno |
| ct_connect_type | Relativo alla colonna connection_type. I valori più comuni sono LAN/Wifi, Mobile Carrier e Modem. | char(20) |
| curr_Factor | Determina la posizione decimale della valuta e viene utilizzata per la conversione della valuta. Ad esempio, USD utilizza due posizioni decimali, quindi il valore di questa colonna è 2. | tinyint |
| curr_rate | Il tasso di cambio al momento della transazione. Adobe collabora con XE per determinare il tasso di cambio del giorno corrente. | decimal(24,12) |
| currency | Codice valuta utilizzato durante la transazione. | char(8) |
| cust_hit_time_gmt | Solo suite di rapporti abilitate per marca temporale. Il timestamp inviato con l’hit, in base all’ora Unix. | int |
| cust_visid | Se è impostato un ID visitatore personalizzato, questo viene popolato in questa colonna. | varchar(255) |
| Daily_visitor | Flag per determinare se l’hit è un nuovo visitatore giornaliero. | tinyint non firmato |
| date_time | L'ora dell'hit in formato leggibile, in base al fuso orario della suite di rapporti. | datetime |
| domain | Variabile utilizzata nella dimensione Dominio. Basato sul provider di servizi Internet (ISP) dell'utente. | varchar(100) |
| duplicate_events | Elenca ogni evento conteggiato come duplicato. | varchar(255) |
| duplicate_purchase | Flag che indica che l'evento di acquisto per l'hit deve essere ignorato perché è un duplicato. | tinyint non firmato |
| duplicated_from | Utilizzata solo nelle suite di rapporti contenenti regole VISTA della copia hit. Indica da quale suite di rapporti è stato copiato l’hit. | varchar(40) |
| ef_id | ef_id utilizzato nelle integrazioni Adobe Advertising Cloud. | varchar(255) |
| evar1 - evar250 | Variabili personalizzate 1-250. Ogni organizzazione utilizza eVar in modo diverso. Il luogo migliore per ulteriori informazioni su come la tua organizzazione compila le rispettive eVar sarebbe un documento di progettazione della soluzione specifico per la tua organizzazione. | varchar(255) |
| event_list | Elenco separato da virgole di ID numerici che rappresentano gli eventi attivati sull’hit. Include sia gli eventi predefiniti che gli eventi personalizzati 1-1000. Utilizza la ricerca event.tsv. | text |
| exclude_hit | Flag che indica che l’hit è escluso dal reporting. La colonna visit_num non viene incrementata per gli hit esclusi.<br>1: Non utilizzato. Parte di una feature di scarto.<br>2: Non utilizzato. Parte di una feature di scarto.<br>3:Non più utilizzato. Esclusione<br>agente utente 4: Esclusione basata sull'indirizzo<br>IP 5: Informazioni hit vitali mancanti, ad esempio page_url, page_name, page_event o event_list<br>6: JavaScript non ha elaborato correttamente l'hit<br>7: Esclusione specifica dell'account, ad esempio in una regola<br>VISTA 8: Non utilizzato. Esclusione specifica per l'account alternativa.<br>9: Non utilizzato. Parte di una feature di scarto.<br>10: Codice<br>valuta 11 non valido: Hit manca una marca temporale in una suite di rapporti con solo marca temporale o un hit contiene una marca temporale in una suite<br>12 di rapporti con marca non temporale: Non utilizzato. Parte di una feature di scarto.<br>13. Non utilizzato. Parte di una feature di scarto.<br>14. Hit di destinazione che non corrisponde a un hit<br>15 di Analytics: Al momento non utilizzato.<br>16. Hit di Advertising Cloud non corrispondente a un hit di Analytics | tinyint non firmato |
| first_hit_page_url | Il primo URL del visitatore. | varchar(255) |
| first_hit_pagename | Variabile utilizzata nella dimensione Originale pagina di immissione. Il nome originale della pagina di immissione del visitatore. | varchar(100) |
| first_hit_ref_domain | Variabile utilizzata nella dimensione Dominio di riferimento originale. Basato su first_hit_referrer. Il primo dominio di riferimento del visitatore. | varchar(100) |
| first_hit_ref_type | ID numerico che rappresenta il tipo di referente del primo referente del visitatore. Utilizza la ricerca referrer_type.tsv. | tinyint non firmato |
| first_hit_referrer | Il primo URL di riferimento del visitatore. | varchar(255) |
| first_hit_time_gmt | Timestamp del primo hit del visitatore in Unix time. | int |
| geo_city | Nome della città da cui proveniva l’hit, basato su IP. Adobe collabora con Digital Enviy per adattare l'indirizzo IP alla città. | char(32) |
| geo_country | Abbreviazione del paese da cui l'hit è venuto, basato su IP. Adobe collabora con Digital Inviate per far corrispondere l'indirizzo IP al Paese. | char(4) |
| geo_dma | ID numerico dell’area demografica da cui proveniva l’hit, basato su IP. Adobe collabora con Digital Inviate per far corrispondere l'indirizzo IP all'area demografica. | int non firmato |
| geo_region | Nome dello stato o della regione da cui proveniva l’hit, in base all’IP. Adobe collabora con Digital Inviate per far corrispondere l'indirizzo IP allo stato/regione. | char(32) |
| geo_zip | Il codice zip dal quale proveniva l’hit, basato su IP. Adobe collabora con Digital Inviate per far corrispondere l'indirizzo IP al codice postale. | varchar(16) |
|  hier1 - hier5 | Utilizzata dalle variabili della gerarchia. Contiene un elenco delimitato di valori. Il carattere di delimitazione è selezionato nelle impostazioni della suite di rapporti. | varchar(255) |
| hit_source | Indica da quale origine è provenuto l’hit. <br>1: Richiesta immagine standard senza timestamp <br>2: Richiesta immagine standard con marca temporale <br>3: Caricamento origine dati live con marca temporale <br>4: Non utilizzato <br>5: Caricamento origine dati generica <br>6: Elaborazione completa del caricamento dell'origine dati <br>7: Caricamento origine dati ID transazione <br>8: Non più utilizzato; Versioni precedenti delle origini dati Adobe Advertising Cloud <br>9: Non più utilizzato; Metriche di riepilogo di Adobe Social | tinyint non firmato |
| hit_time_gmt | La marca temporale dei server di raccolta dati Adobe hit ha ricevuto l’hit, in base all’ora Unix. | int |
| hitid_high | Utilizzata in combinazione con hitid_low per identificare in modo univoco un hit. | bigint non firmato |
| hitid_low | Utilizzata in combinazione con hitid_high per identificare in modo univoco un hit. | bigint non firmato |
| homepage | Non più utilizzato. Indicato se l’URL corrente è la home page del browser. | char(1) |
| horly_visitor | Flag per determinare se l’hit è un nuovo visitatore orario. | tinyint non firmato |
| ip | Indirizzo IP, basato sull’intestazione HTTP della richiesta di immagine. | char(20) |
| ip2 |  Non utilizzato. Variabile di riferimento di back-end per le suite di rapporti contenenti regole VISTA basate sull'indirizzo IP. | char(20) |
| j_jscript | Versione di JavaScript supportata dal browser. | char(5) |
| java_enabled | Flag che indica se Java è abilitato. <br>Y: Abilitato <br>N: Disattivato <br>U: Sconosciuto | char(1) |
| javascript | ID di ricerca della versione JavaScript, basato su j_jscript. Utilizza la tabella di ricerca. | tinyint non firmato |
| language | ID numerico della lingua. Utilizza la tabella di ricerca language.tsv. | numero piccolo senza segno |
| last_hit_time_gmt | Timestamp (in tempo Unix) dell’hit precedente. Utilizzato per calcolare la dimensione Giorni dall’ultima visita. | int |
| last_purchase_num | Variabile utilizzata nella dimensione Fedeltà cliente. Indica il numero di acquisti precedenti effettuati dal visitatore. <br>0: Nessun acquisto precedente (non cliente) <br>1: 1 acquisto precedente (nuovo cliente) <br>2: 2 acquisti precedenti (cliente reso) <br>3: 3 o più acquisti precedenti (cliente leale) | int non firmato |
| last_purchase_time_gmt | Utilizzata nella dimensione Giorni dall'ultimo acquisto. Timestamp (in Unix ora) dell’ultimo acquisto effettuato. Per gli acquisti e i visitatori che non hanno effettuato un acquisto in precedenza, questo valore è 0. | int |
| latlon1 | Posizione (fino a 10 chilometri) | varchar(255) |
| latlon23 | Posizione (fino a 100 m) | varchar(255) |
| latlon45 | Posizione (fino a 1 m) | varchar(255) |
| È stata aggiunta la colonna mc_audiences | Elenco degli ID del segmento di Audience Manager a cui il visitatore appartiene. | text |
| mcvisid | ID visitatore Experience Cloud. Numero a 128 bit composto da due numeri concatenati a 64 bit aggiunti a 19 cifre. | varchar(255) |
| mobile_id | Se l'utente utilizza un dispositivo mobile, l'ID numerico del dispositivo. | int |
| mobileaction | Azione mobile. Raccolta automatica quando trackAction viene chiamato in Mobile Services. Consente il percorso automatico dell'azione nell'app. | varchar(100) |
| mobileappid | ID app mobile. Stores the application name and version in the following format:[AppName] [BundleVersion] | varchar(255) |
| mobileappperformance eappid | Utilizzato nel connettore dati Apteligent. L'ID app utilizzato in Apteligent. | varchar(255) |
| mobileappperformance ecrashid | Utilizzato nel connettore dati Apteligent. L'ID dell'arresto anomalo utilizzato in Apteligent. | varchar(255) |
| mobileappstoreobjectid | Utilizzato nel connettore dati Appfigures. ID oggetto App store | varchar(255) |
| mobilebeaconmajor | beacon principale Mobile Services | varchar(100) |
| mobilebeaconminor | beacon secondario di Mobile Services | varchar(100) |
| mobilebeaconprossimità | Prossimità beacon Mobile Services | varchar(255) |
| mobilebeaconuid | UUID beacon Mobile Services | varchar(100) |
| mobilecampaigncontent | Nome o ID del contenuto in cui è stato visualizzato il collegamento. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| mobilecampaignmedium | Canale di marketing, ad esempio banner o e-mail. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| mobilecampaignname | Nome della campagna, memorizzato anche nella variabile della campagna. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| mobilecampaignsource | Referente originale, ad esempio una newsletter o una rete social media. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| mobilecampaignterm | Keyword a pagamento o altri termini di cui si desidera tenere traccia con questa acquisizione. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| mobiledayofweek | Numero del giorno feriale in cui è stata avviata l’app. | varchar(255) |
| mobiledayssincefirstuse | Numero di giorni dalla prima esecuzione dell'app. | varchar(255) |
| mobiledayssincelastupgrade | Raccolte dalla variabile di dati contestuali a.DaysSinceLastUpgrade. Il numero di giorni trascorsi dalla sessione precedente. | varchar(255) |
| mobiledayssincelastuse | Numero di giorni dall'ultima esecuzione dell'app. | varchar(255) |
| mobiledeeplinboy | Raccolti dalla variabile dei dati contestuali a.<span>deeplink</span>.id. Utilizzato nei rapporti di acquisizione come identificatore per il collegamento di acquisizione mobile. | varchar(255) |
| mobiledevice | Nome del dispositivo mobile. Su iOS, viene memorizzato come stringa di 2 cifre separate da virgola. Il primo numero rappresenta la generazione del dispositivo e il secondo numero rappresenta la famiglia di dispositivi. | varchar(255) |
| mobilehourofday | Definisce l'ora del giorno in cui è stata avviata l'app. Segue il formato numerico a 24 ore. | varchar(255) |
| mobileinstalldate | Data di installazione per dispositivi mobili. Fornisce la data della prima volta che un utente apre l'app mobile. | varchar(255) |
| mobilelaunchessincelastupgrade | Raccolti dalla variabile di dati contestuali a.LaunchesSinceUpgrade. Segnala il numero di avvii dall'ultimo aggiornamento. | varchar(255) |
| mobilelaunchnumber | Aumenta di una volta ogni volta che l'app mobile viene avviata. | varchar(255) |
| mobileltv | Non più utilizzato. Viene compilata dai metodi trackLifetimeValue. | varchar(255) |
| mobilemessagebuttonname | Raccolte dalla variabile dei dati contestuali a.<span>message</span>.button.id. Utilizzata per i messaggi in-app per identificare il pulsante che ha chiuso il messaggio. | varchar(100) |
| mobilemessageid | ID messaggio in-app | varchar(255) |
| mobilemessageonline | Messaggio in-app online | varchar(255) |
| mobilemessagepushoptin | Raccolte dalla variabile di dati contestuali a.push.optin. Impostate su "true" quando l'utente sceglie di abilitare i messaggi push; altrimenti il valore è "false". | varchar(255) |
| mobilemessagepushpayloadid | Raccolti dalla variabile di dati contestuali a.push.payloadid. Utilizzato nei messaggi push come identificatore di payload. | varchar(255) |
| mobileosenenvironment | Raccolto dalla variabile di dati contestuali a.OSEnenvironment. Ambiente operativo stato, ad esempio Android o iOS. | varchar(255) |
| mobileosversion | Versione del sistema operativo Mobile Services | varchar(255) |
| mobilesegnaposto | Raccolte dalla variabile di dati contestuali a.loc.acc. Indica la precisione del GPS in metri al momento della raccolta. | varchar(255) |
| mobileplacecategory | Raccolto dalla variabile di dati contestuali a.loc.category. Descrive la categoria di un luogo specifico. | varchar(255) |
| mobilesegnaposto | Raccolte dalla variabile di dati contestuali a.<span>loc</span>.id. Identificatore per un dato punto di interesse. | varchar(255) |
| mobilerelaunchcampaign content | Contenuto lancio Mobile Services | varchar(255) |
| mobilerelaunchcampaign | Media di avvio di Mobile Services | varchar(255) |
| mobilerelaunchcampaign source | Origine avvio di Mobile Services | varchar(255) |
| mobilerelaunchcampaign | Termine di avvio di Mobile Services | varchar(255) |
| mobilerelaunchcampaign trackingcode | Raccolti dalla variabile di dati contestuali a.launch.campaign.trackingcode. Utilizzato nell’acquisizione come codice di tracciamento per la campagna di lancio. | varchar(255) |
| mobileresolution | Risoluzione del dispositivo mobile. Larghezza x altezza in pixel. | varchar(255) |
| month_visitor | Flag che indica che il visitatore è univoco per il mese corrente. | tinyint non firmato |
| mvvar1 - mvvar3 | Elenca i valori delle variabili. Contiene un elenco delimitato di valori personalizzati a seconda dell'implementazione. | text |
| namespace |  Non utilizzato. Parte di una feature di scarto molti anni fa. | varchar(50) |
| new_visit | Flag che determina se l’hit corrente è una nuova visita. Impostato dai server Adobe dopo 30 minuti di inattività della visita. | tinyint non firmato |
| os | ID numerico che rappresenta il sistema operativo del visitatore. Basato sulla colonna user_agent. Utilizza la ricerca os. | int non firmato |
| p_plugins | Non più utilizzato. Elenco di plug-in disponibili per il browser. Utilizzata la funzione JavaScript navigator.plugins(). | text |
| page_event | Tipo di hit inviato nella richiesta di immagine (hit standard, collegamento per il download, collegamento personalizzato, collegamento di uscita). See [Page event lookup](datafeeds-page-event.md). | tinyint non firmato |
| page_event_var1 | Utilizzata solo nelle richieste di tracciamento collegamenti delle immagini. È stato fatto clic sull’URL del collegamento di download, del collegamento di uscita o del collegamento personalizzato. | text |
| page_event_var2 | Utilizzata solo nelle richieste di tracciamento collegamenti delle immagini. Nome personalizzato (se specificato) del collegamento. | varchar(100) |
| page_event_var3 | Non più utilizzato. Dati del modulo Survey e Media contenuti. Vengono compilati rapporti video precedenti nelle versioni precedenti di Adobe Analytics. | text |
| page_type | Viene utilizzata per compilare la dimensione Pagine non trovate, utilizzata esclusivamente per 404 pagine. Questa variabile deve essere vuota o contenere "ErrorPage". | char(20) |
| page_url | URL dell’hit. Non utilizzato nelle richieste di immagini per il tracciamento dei collegamenti. | varchar(255) |
| nomepagina | Utilizzato per compilare la dimensione Pagine. Se la variabile nome pagina è vuota, Analytics utilizza invece page_url. | varchar(100) |
| paid_search | Flag impostato se l’hit corrisponde al rilevamento della ricerca a pagamento. | tinyint non firmato |
| partner_plugins |  Non utilizzato. Parte di una feature di scarto molti anni fa. | varchar(255) |
| persistente_cookie | Utilizzata dalla dimensione Supporto cookie persistente. Indica se il visitatore supporta i cookie che non vengono scartati dopo ogni hit. | char(1) |
| plugins | Non più utilizzato. Elenco di ID numerici che corrispondono ai plug-in disponibili nel browser. Utilizza la ricerca plugins.tsv. | varchar(180) |
| puntiniere | Nome del punto di interesse di Mobile Services | varchar(255) |
| puntofinterestdistanze | Distanza da Mobile Services a punto di interesse | varchar(255) |
| post_Columns | Contiene il valore utilizzato in ultima analisi nei report. Ogni colonna di post viene compilata dopo logica lato server, regole di elaborazione e regole VISTA. Nella maggior parte dei casi, Adobe consiglia di utilizzare le colonne di post. | Vedere le rispettive colonne non post |
| prev_page |  Non utilizzato. Identificatore proprietario Adobe della pagina precedente. | int non firmato |
| product_list | Elenco prodotti come passato attraverso la variabile products. I prodotti sono delimitati da virgole, mentre le singole proprietà del prodotto sono delimitate da punto e virgola. | text |
| product_merchandising |  Non utilizzato. Utilizzare product_list. | text |
| prop1 - prop75 | Variabili di traffico personalizzate 1-75. | varchar(100) |
| purchaseid | Identificatore univoco per un acquisto, impostato utilizzando la variabile s_purchaseID. Utilizzato dalla colonna duplicate_purchase. | char(20) |
| trimestrali_visitor | Flag per determinare se l’hit è un nuovo visitatore trimestrale. | tinyint non firmato |
| ref_domain | Basato sulla colonna del referente. Il dominio di riferimento dell’hit. | varchar(100) |
| ref_type | Un ID numerico che rappresenta il tipo di riferimento per l'hit.<br>1: All'interno del sito<br>2: Altri siti Web <br>3: Motori di ricerca <br>4: Disco rigido <br>5: USENET <br>6: Tipo/Segnalibro (nessun referente) <br>7: E-mail <br>8: Nessun JavaScript <br>9: Social Network | tinyint non firmato |
| referrer | URL pagina della pagina precedente. | varchar(255) |
| resolution | ID numerico che rappresenta la risoluzione del monitor. Compila la dimensione Risoluzione monitor. Utilizza la tabella di ricerca resolution.tsv. | numero piccolo senza segno |
| s_kwcid | ID parola chiave utilizzato nelle integrazioni Adobe Advertising Cloud. | varchar(255) |
| s_resolution | Valore di risoluzione dello schermo non elaborato. Raccolte utilizzando la funzione JavaScript screen.width x screen.height. | char(20) |
| sample_hit | Non più utilizzato. In precedenza veniva utilizzato per il campionamento in Analisi ad hoc. | char(1) |
| search_Engine | ID numerico che rappresenta il motore di ricerca che ha indirizzato il visitatore al sito. Utilizza la ricerca search_Engine.tsv. | numero piccolo senza segno |
| search_page_num | Utilizzata dalla dimensione Classifica pagina di ricerca. Indica in quale pagina di risultati di ricerca il sito è stato visualizzato prima che l’utente facesse clic sul sito. | numero piccolo senza segno |
| secondaria_hit | Flag che tiene traccia degli hit secondari. Di norma l’origine viene dai tag con più suite e dalle regole VISTA che copiano gli hit. | tinyint non firmato |
| service |  Non utilizzato. Utilizzare invece page_event. | char(2) |
| socialaccountandappids | Non più utilizzato. Account social e ID app | varchar(255) |
| socialassettrackingcode | Non più utilizzato. Variabile campagna social | varchar(255) |
| socialautore | Non più utilizzato. Variabile Autori social | varchar(255) |
| socialcontentprovider | Non più utilizzato. Piattaforme/Proprietà social | varchar(255) |
| socialinteractiontype | Non più utilizzato. Tipo di interazione Social | varchar(255) |
| socialingua | Non più utilizzato. Lingua sociale | varchar(255) |
| sociallatlong | Non più utilizzato. Latitudine/longitudine social | varchar(255) |
| socialowneddefinition insighype | Non più utilizzato. Tipo di informazioni sulla definizione di proprietà sociale | varchar(255) |
| socialowneddefinition insightvalue | Non più utilizzato. Valore di approfondimento della definizione di proprietà sociale | varchar(255) |
| socialowneddefinition | Non più utilizzato. Metrica di definizione social | varchar(255) |
| socialownddefinition ionproperty yvspost | Non più utilizzato. Proprietà definizione di proprietà social network vs post | varchar(255) |
| socialownedpostids | Non più utilizzato. ID post di proprietà sociale | varchar(255) |
| socialownedproperty | Non più utilizzato. ID proprietà social | varchar(255) |
| socialownedpropertyName | Non più utilizzato. Nome proprietà di proprietà di Social | varchar(255) |
| socialownedProprietà yvsapp | Non più utilizzato. Proprietà di proprietà social vs app | varchar(255) |
| state | Variabile di stato. | varchar(50) |
| stats_server | Non è utile. Server interno Adobe che ha elaborato l’hit. | char(30) |
| t_time_info | Ora locale del visitatore. Il formato è il seguente: M/G/AAAA HH:MM:SS Mese (0-11, 0=gennaio) Offset fuso orario (in minuti) | varchar(100) |
| tenda | Utilizzata nelle integrazioni Adobe Target. | text |
| tnt_action | Utilizzata nelle integrazioni Adobe Target. | text |
| tnt_post_vista | Non più utilizzato. Utilizzare post_tnt. | text |
| transactionid | Un identificatore univoco in cui è possibile caricare vari punti dati in un secondo momento tramite origini dati. | text |
| truncated_hit | Flag che indica che la richiesta di immagine è stata troncata. Indica che è stato ricevuto un hit parziale. <br>Y: Hit è stato troncato; hit parziale ricevuto <br>N: Hit non è stato troncato; hit completo ricevuto | char(1) |
| ua_color | Non più utilizzato. Precedentemente usato come fallback per la profondità del colore. | char(20) |
| ua_os | Non più utilizzato. Precedentemente utilizzato come fallback per il sistema operativo. | char(80) |
| ua_pixel | Non più utilizzato. Precedentemente usato come fallback per l’altezza e la larghezza del browser. | char(20) |
| user_agent | Stringa agente utente inviata nell’intestazione HTTP della richiesta di immagine. | text |
| user_hash | Non è utile. Hash sull'ID suite di rapporti. Utilizzate il nome utente. | int non firmato |
| user_server | Variabile utilizzata nella dimensione Server. | varchar(100) |
| userid | Non è utile. ID numerico per l'ID suite di rapporti. Utilizzate il nome utente. | int non firmato |
| username | ID suite di rapporti per l’hit. | char(40) |
| va_closer_detail | Variabile utilizzata nella dimensione Ultimo dettaglio contatto. | varchar(255) |
| va_closer_id | ID numerico che identifica la dimensione Ultimo canale di contatto. È possibile cercare questo ID in Marketing Channel Manager. | tinyint non firmato |
| va_finder_detail | Variabile utilizzata nella dimensione Primo dettaglio touch. | varchar(255) |
| va_finder_id | ID numerico che identifica la dimensione Primo canale di contatto. È possibile cercare questo ID in Marketing Channel Manager. | tinyint non firmato |
| va_instance_event | Flag per identificare le istanze del canale di marketing. Utilizzata dalla metrica Istanze ultimo contatto canale di marketing. | tinyint non firmato |
| va_new_engagement | Contrassegno per identificare i nuovi impegni del canale di marketing. Utilizzata dalla metrica New Engagement (Nuovi impegni). | tinyint non firmato |
|  video | Contenuto video | varchar(255) |
|  videoad | Nome annuncio video | varchar(255) |
| videoadinpod | Annuncio video nella posizione del contenitore | varchar(255) |
|  videoadlength | Durata video e annuncio | varchar(255) |
| videoadload | Caricamento di annunci video | varchar(255) |
| videoadname | Nome annuncio video | varchar(255) |
|  videoadplayername | Nome del lettore di annunci video | varchar(255) |
|  videoadpod | Video e contenitore | varchar(255) |
|  videoadvertiser | Annuncio video | varchar(255) |
|  videoaudioalbum | Video audio album | varchar(255) |
|  videoaudioartista | Video audio, artista | varchar(255) |
|  videoaudioautore | Autore audio video | varchar(255) |
|  videoaudiolibro | Etichetta audio video | varchar(255) |
|  videoaudiopublisher | Editore audio video | varchar(255) |
|  videoconferenza | Video audio station | varchar(255) |
|  video | Campagna video | varchar(255) |
|  videocanale | Canale video | varchar(255) |
|  videocapitolo | Nome del capitolo video | varchar(255) |
|  videocontenttype | Tipo di contenuto video. Imposta su "Video" automaticamente per tutte le viste video | varchar(255) |
|  videodaypart | Parte giorno video | varchar(255) |
|  videoepisodio | Video | varchar(255) |
|  videofeedtype | Tipo di feed video | varchar(255) |
|  videogenere | Genere video | text |
|  lunghezza video | Lunghezza video | varchar(255) |
|  videomvpd | Video MVPD | varchar(255) |
|  videoname | Nome video | varchar(255) |
|  videonetwork | Rete video | varchar(255) |
|  videopath | Percorso video | varchar(100) |
|  videoplayername | Nome lettore video | varchar(255) |
|  videoqoebitrateaverageevar | Bitrate medio della qualità video | varchar(255) |
|  videoqoebitratechangecountevar | Conteggio modifiche qualità video | varchar(255) |
|  videoqoebuffercountevar | Conteggio buffer qualità video | varchar(255) |
|  videoqoebuffertimevar | Tempo buffer qualità video | varchar(255) |
|  videoqoedroppedframecountevar | Qualità video: numero fotogrammi saltati | varchar(255) |
|  videoqoeerrorcountevar | Conteggio errori qualità video | varchar(255) |
|  videoqoeextneralerrori | Errori esterni di qualità video | text |
|  videoqoeplayersderrori | Errori SDK qualità video | text |
|  videoqetimetostartevar | Tempo di avvio della qualità video | varchar(255) |
|  videoconferenza | Stagione video | varchar(255) |
|  videosegmento | Segmento video | varchar(255) |
|  videoshow | Video show | varchar(255) |
|  videoshowtype | Tipo di visualizzazione video | varchar(255) |
|  videostreamtype | Tipo di flusso video | varchar(255) |
| visid_high | Utilizzata in combinazione con visid_low per identificare in modo univoco una visita. | bigint non firmato |
| visid_low | Utilizzata in combinazione con visid_high per identificare in modo univoco una visita. | bigint non firmato |
| visid_new | Flag per identificare se l’hit contiene un ID visitatore appena generato. | char(1) |
| visid_timestamp | Se l’ID visitatore è stato appena generato, fornisce la marca temporale (in Unix ora) di quando è stato generato l’ID visitatore. | int |
| visid_type | ID numerico che rappresenta il metodo utilizzato per identificare il visitatore. <br>0: ID visitatore personalizzato <br>1: Fallback IP e agente utente <br>2: Intestazione <br>3 utente con sottoscrizione HTTP Mobile: Valore cookie legacy (s_vi) <br>4: Valore cookie di fallback (s_fid) <br>5: Servizio identità | tinyint non firmato |
| visit_keywords | Variabile utilizzata nella dimensione Parola chiave di ricerca. Questa colonna utilizza un limite di caratteri non standard per adattarlo alla logica di back-end utilizzata da Adobe. | varchar(244) |
| visit_num | Variabile utilizzata nella dimensione Numero visita. Inizia da 1 e incrementa ogni volta che inizia una nuova visita per visitatore. | int non firmato |
| visit_page_num | Variabile utilizzata nella dimensione Profondità hit. Aumenta di 1 per ogni hit generato dall’utente. Ripristina ogni visita. | int non firmato |
| visit_ref_domain | Basato sulla colonna visit_referrer. Il primo dominio di riferimento della visita. | varchar(100) |
| visit_ref_type | ID numerico che rappresenta il tipo di referente del primo referente della visita. Utilizza la tabella di ricerca referrer_type.tsv. | tinyint non firmato |
| visit_referrer | Il primo referente della visita. | varchar(255) |
| visit_search_Engine | ID numerico del primo motore di ricerca della visita. Utilizza la tabella di ricerca search_Engine.tsv. | numero piccolo senza segno |
| visit_start_page_url | Il primo URL della visita. | varchar(255) |
| visit_start_page | Nome pagina della visita. | varchar(100) |
| visit_start_time_gmt | Timestamp (in tempo Unix) del primo hit della visita. | int |
| week_visitor | Flag per determinare se l’hit è un nuovo visitatore settimanale. | tinyint non firmato |
| year_visitor | Flag per determinare se l’hit è un nuovo visitatore annuale. | tinyint non firmato |
| zip | Utilizzato per compilare la dimensione Codice postale. | varchar(50) |

## Colonne vuote

Il seguente elenco di colonne non è utilizzato e non contiene dati:

* mobileacquisizioneClick
* mobileactioninapptime
* mobileactiontotaltime
* mobileappperformance anceaffectedusers
* mobileappPerformance<span>appid.</span>app-perf-app-name
* mobileappPerformance<span>appid.</span>app-perf-platform
* mobileappperformance ecrash
* mobileappperformance ecrashid<span>.</span>app-perf-crash-name
* mobileappperformance eloads
* mobileappstoreavgrating
* mobileappstoredownload
* mobileappstoreinapprvenue
* mobileappstoreinavvicinare
* mobileappstoreobjectid<span>.</span>app-store-user
* mobileappstoreobjectid<span>.</span>application-name
* mobileappstoreobjectid<span>.</span>versione applicazione
* mobileappstoreobjectid<span>.</span>appstore-name
* mobileappstoreobjectid<span>.</span>category-name
* mobileappstoreobjectid<span>.</span>country-name
* mobileappstoreobjectid<span>.</span>produttore di dispositivi
* mobileappstoreobjectid<span>.</span>device-name
* mobileappstoreobjectid<span>.</span>in-app-name
* mobileappstoreobjectid<span>.</span>platform-name-version
* mobileappstoreobjectid<span>.</span>rank-category-type
* mobileappstoreobjectid<span>.</span>region-name
* mobileappstoreobjectid<span>.</span>review-comment
* mobileappstoreobjectid<span>.</span>review-title
* mobileappstoreoneoffRevenue
* mobileappstoreoneoffroyalty
* mobileappstorepurchases
* mobileappstorerank
* mobileappstorerankdivisor
* mobileappstorerizzazione
* mobileappstoreratingdivisor
* mobileavgpresession length
* mobilecrash
* mobilecrashrate
* mobiledailyengagedusers
* mobiledeeplinboy<span>.</span>name
* mobileinstalls
* mobilelaunches
* mobileltvtotal
* mobilemessagecick
* mobilemessageid<span>.</span>dest
* mobilemessageid<span>.</span>name
* mobilemessageid<span>.</span>type
* mobilemessageimpression
* mobilemessagepushpayloadid<span><span>.</span></span>name
* mobilemessfacilità
* mobilemonthengagedusers
* mobileplacedwelltime
* mobilesegnaposto
* mobilesegnaposto exit
* mobilepresession length
* mobilerelaunchcampaign trackingcode<span><span>.</span></span>name
* mobileupgrade
* socialaveragesentiment
* socialaveragesentiment (obsoleto)
* socialfonstorie
* socialfbstorytellers
* socialinteractioncount
* sociallikeadd
* sociallink
* sociallink (obsoleto)
* socialmenità
* socialpageviews
* socialpostviews
* socialproperty
* socialproperty (obsoleto)
* socialpubcommenti
* socialpubpost
* socialpubres raccomanda
* socialpubsubscriber
* socialterm
* socialtermslist
* socialtermslist (obsoleto)
* sentimento socialtotalitario
* sourceid
*  videoautorizzato
* videoaverageminuteaudience
*  videochaptercomplete
* videochapterstart
* videoclip
*  videopause
*  videopausecount
* videopausetime
*  videogioco
* videoprogress10
* videoprogress25
* videoprogress50
* videoprogress75
* videoprogress96
*  videoqoebitrateaverage
*  videoqoebitratechange
*  videoqoebuffer
*  videoqoedropbeforestart
*  videoqoedroppedframe
* videoqoeerror
* videoresume
* videototaltime
* videouniquetimeplay
