---
description: Dati di tabella che descrivono le colonne nel feed di dati.
keywords: Data Feed;columns
subtopic: data feeds
title: Riferimento colonna dati
topic: Reports and analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
translation-type: tm+mt
source-git-commit: f3b227e7d2f239076f7c38abd42af6e1a86b0069
workflow-type: tm+mt
source-wordcount: '3403'
ht-degree: 3%

---


# Riferimento colonna dati

Utilizzare questa pagina per apprendere quali dati sono contenuti in ciascuna colonna. La maggior parte delle implementazioni non utilizza tutte le colonne, pertanto è possibile fare riferimento a questa pagina per determinare quali colonne includere in un&#39;esportazione di feed di dati.

>[!IMPORTANT]
>
>Per qualsiasi colonna (ad esempio, una con 255 caratteri), un feed di dati può inviare caratteri aggiuntivi a causa dell&#39;aggiunta di caratteri che sfuggono ai valori di una stringa. Tieni presente questi potenziali caratteri aggiuntivi se la tua implementazione invia regolarmente valori che superano i limiti dei caratteri.

## Colonne, descrizioni e tipi di dati

>[!NOTE]
>
>La maggior parte delle colonne contiene una colonna simile con il prefisso `post_`. Le colonne post contengono valori dopo la logica lato server, le regole di elaborazione e le regole VISTA.  Adobe consiglia di utilizzare le colonne di post nella maggior parte dei casi. Per ulteriori informazioni, consulta [Domande frequenti](../df-faq.md) sui feed di dati.

| Nome colonna | Descrizione colonna | Tipo di dati |
| --- | --- | --- |
| `accept_language` | Elenca tutte le lingue accettate, come indicato nell’intestazione HTTP Accept-Language in una richiesta di immagine. | char(20) |
| `aemassetid` | Variabile multivalore corrispondente ai GUID di un set di risorse Adobe Experience Manager. Incrementa Gli Eventi Di Impressione. | text |
| `aemassetsource` | Identifica l&#39;origine dell&#39;evento della risorsa. Utilizzata in Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | ID risorsa di una risorsa Adobe Experience Manager. Incrementi Fare Clic Su Eventi. | varchar(255) |
| `browser` | ID numerico del browser. Fa riferimento alla tabella di `browser.tsv` ricerca. | int senza segno |
| `browser_height` | Altezza in pixel della finestra del browser. | numero piccolo senza segno |
| `browser_width` | Larghezza in pixel della finestra del browser. | numero piccolo senza segno |
| `c_color` | Profondità in bit della tavolozza dei colori. Utilizzato come parte del calcolo della dimensione di profondità [del](/help/components/dimensions/color-depth.md) colore. AppMeasurement utilizza la funzione JavaScript `screen.colorDepth()`. | char(20) |
| `campaign` | Variabile utilizzata nella dimensione Codice [](/help/components/dimensions/tracking-code.md) tracciamento. | varchar(255) |
| `carrier` | Variabile di integrazione Adobe Advertising Cloud. Specifica il vettore del dispositivo mobile. Fa riferimento alla tabella di `carrier` ricerca. | varchar(100) |
| `channel` | Variabile utilizzata nella dimensione delle sezioni [](/help/components/dimensions/site-section.md) Sito. | varchar(100) |
| `click_action` | Non più utilizzato. Indirizzo del collegamento su cui è stato fatto clic nello strumento ClickMap legacy. | varchar(100) |
| `click_action_type` | Non più utilizzato. Tipo di collegamento dello strumento ClickMap precedente.<br>0: URL<br>1 HREF: ID<br>personalizzato 2: Evento<br>3 JavaScript onClick: Elemento modulo | tinyint non firmato |
| `click_context` | Non più utilizzato. Nome pagina in cui si è verificato il clic sul collegamento. Parte dello strumento ClickMap legacy. | varchar(255) |
| `click_context_type` | Non più utilizzato. Indica se click_context ha un nome di pagina o se è stato impostato automaticamente sull’URL della pagina.<br>0: URL<br>pagina 1: Nome pagina | tinyint non firmato |
| `click_sourceid` | Non più utilizzato. ID numerico per la posizione sulla pagina del collegamento selezionato. Parte dello strumento ClickMap legacy. | int senza segno |
| `click_tag` | Non più utilizzato. Tipo di elemento HTML su cui è stato fatto clic. | char(10) |
| `clickmaplink` | Collegamento Activity Map  | varchar(255) |
| `clickmaplinkbyregion` | Collegamento Activity Map  per regione | varchar(255) |
| `clickmappage` | Pagina Activity Map  | varchar(255) |
| `clickmapregion` |  Activity Map | varchar(255) |
| `code_ver` | Versione della libreria AppMeasurement utilizzata per compilare e inviare la richiesta di immagine. | char(16) |
| `color` | ID profondità colore in base al valore della `c_color` colonna. Fa riferimento alla tabella di `color_depth.tsv` ricerca. | numero piccolo senza segno |
| `connection_type` | ID numerico che rappresenta il tipo di connessione. Variabile utilizzata nella dimensione del tipo [di](/help/components/dimensions/connection-type.md) connessione. Fa riferimento alla tabella di `connection_type.tsv` ricerca. | tinyint non firmato |
| `cookies` | Variabile utilizzata nella dimensione [Cookie support](/help/components/dimensions/cookie-support.md) .<br>Y:<br>EnabledN:<br>DisabledU: Sconosciuto | char(1) |
| `country` | ID numerico che rappresenta il paese da cui proveniva l’hit. Utilizzata nella dimensione [Paesi](/help/components/dimensions/countries.md) . Utilizza `country.tsv` la ricerca. | numero piccolo senza segno |
| `ct_connect_type` | Relativo alla `connection_type` colonna. I valori più comuni sono LAN/Wifi, Mobile Carrier e Modem. | char(20) |
| `curr_factor` | Determina la posizione decimale della valuta e viene utilizzata per la conversione della valuta. Ad esempio, USD utilizza due posizioni decimali, quindi il valore di questa colonna è 2. | tinyint |
| `curr_rate` | Il tasso di cambio al momento della transazione.  Adobe partner di XE per determinare il tasso di cambio del giorno corrente. | decimal(24,12) |
| `currency` | Codice valuta utilizzato durante la transazione. | char(8) |
| `cust_hit_time_gmt` | Solo suite di rapporti abilitate per marca temporale. Il timestamp inviato con l’hit, in base all’ora Unix. | int |
| `cust_visid` | Se è impostato un ID visitatore personalizzato, questo viene popolato in questa colonna. | varchar(255) |
| `daily_visitor` | Flag per determinare se l’hit è un nuovo visitatore giornaliero. | tinyint non firmato |
| `date_time` | L&#39;ora dell&#39;hit in formato leggibile, in base al fuso orario della suite di rapporti. | datetime |
| `domain` | Variabile utilizzata nella dimensione [Dominio](/help/components/dimensions/domain.md) . In base al punto di accesso Internet del visitatore. | varchar(100) |
| `duplicate_events` | Elenca ogni evento conteggiato come duplicato. | varchar(255) |
| `duplicate_purchase` | Flag che indica che l&#39;evento di acquisto per l&#39;hit deve essere ignorato perché è un duplicato. | tinyint non firmato |
| `duplicated_from` | Utilizzata solo nelle suite di rapporti contenenti regole VISTA della copia hit. Indica da quale suite di rapporti è stato copiato l’hit. | varchar(40) |
| `ef_id` | Viene `ef_id` utilizzato nelle integrazioni Adobe Advertising Cloud. | varchar(255) |
| `evar1 - evar250` | Variabili personalizzate 1-250. Utilizzata nelle dimensioni [eVar](/help/components/dimensions/evar.md) . Ogni organizzazione utilizza eVar in modo diverso. Il luogo migliore per ulteriori informazioni su come la tua organizzazione compila le rispettive eVar sarebbe un documento di progettazione della soluzione specifico per la tua organizzazione. | varchar(255) |
| `event_list` | Elenco separato da virgole di ID numerici che rappresentano gli eventi attivati sull’hit. Include sia gli eventi predefiniti che gli eventi personalizzati 1-1000. Utilizza `event.tsv` la ricerca. | text |
| `exclude_hit` | Flag che indica che l’hit è escluso dal reporting. La `visit_num` colonna non viene incrementata per gli hit esclusi.<br>1: Non utilizzato. Parte di una feature di scarto.<br>2: Non utilizzato. Parte di una feature di scarto.<br>3: Non più utilizzato. Esclusione<br>agente utente 4: Esclusione basata sull&#39;indirizzo<br>IP 5: Informazioni hit vitali mancanti, ad esempio `page_url`, `pagename`, `page_event`o `event_list`<br>6: JavaScript non ha elaborato correttamente l&#39;hit<br>7: Esclusione specifica dell&#39;account, ad esempio in una regola<br>VISTA 8: Non utilizzato. Esclusione specifica per l&#39;account alternativa.<br>9: Non utilizzato. Parte di una feature di scarto.<br>10: Codice<br>valuta 11 non valido: Hit manca una marca temporale in una suite di rapporti con solo marca temporale o un hit contiene una marca temporale in una suite<br>12 di rapporti con marca non temporale: Non utilizzato. Parte di una feature di scarto.<br>13. Non utilizzato. Parte di una feature di scarto.<br>14. Hit di destinazione che non corrisponde a un hit<br>15 di Analytics: Al momento non utilizzato.<br>16.  hit Advertising Cloud che non corrisponde a un hit Analytics | tinyint non firmato |
| `first_hit_page_url` | Il primo URL del visitatore. | varchar(255) |
| `first_hit_pagename` | Variabile utilizzata nella dimensione originale [della pagina](/help/components/dimensions/entry-dimensions.md) Entry. Il nome originale della pagina di immissione del visitatore. | varchar(100) |
| `first_hit_ref_domain` | Variabile utilizzata nella dimensione dominio [di riferimento](/help/components/dimensions/original-referring-domain.md) originale. Basato su `first_hit_referrer`. Il primo dominio di riferimento del visitatore. | varchar(100) |
| `first_hit_ref_type` | ID numerico che rappresenta il tipo di referente del primo referente del visitatore. Utilizza `referrer_type.tsv` la ricerca. | tinyint non firmato |
| `first_hit_referrer` | Il primo URL di riferimento del visitatore. | varchar(255) |
| `first_hit_time_gmt` | Timestamp del primo hit del visitatore in Unix time. | int |
| `geo_city` | Nome della città da cui proveniva l’hit, basato su IP. Utilizzata nella dimensione [Città](/help/components/dimensions/cities.md) . | char(32) |
| `geo_country` | Abbreviazione del paese da cui l&#39;hit è venuto, basato su IP. | char(4) |
| `geo_dma` | ID numerico dell’area demografica da cui proveniva l’hit, basato su IP. Utilizzata nella dimensione DMA [](/help/components/dimensions/us-dma.md) USA. | int senza segno |
| `geo_region` | Nome dello stato o della regione da cui proveniva l’hit, in base all’IP. Utilizzata nella dimensione [Regioni](/help/components/dimensions/regions.md) . | char(32) |
| `geo_zip` | Il codice zip dal quale proveniva l’hit, basato su IP. Consente di compilare la dimensione del codice [](/help/components/dimensions/zip-code.md) ZIP. Vedi anche `zip`. | varchar(16) |
| `hier1 - hier5` | Utilizzata dalle variabili della gerarchia. Contiene un elenco delimitato di valori. Il carattere di delimitazione è selezionato nelle impostazioni della suite di rapporti. | varchar(255) |
| `hit_source` | Indica da quale origine è provenuto l’hit. Le fonti di hit 1, 2 e 6 sono fatturate. <br>1: Richiesta immagine standard senza timestamp <br>2: Richiesta immagine standard con marca temporale <br>3: Caricamento origine dati live con marca temporale <br>4: Non utilizzato <br>5: Caricamento origine dati generica <br>6: Elaborazione completa del caricamento dell&#39;origine dati <br>7: Caricamento origine dati ID transazione <br>8: Non più utilizzato; Versioni precedenti di origini dati Adobe Advertising Cloud <br>9: Non più utilizzato;  metriche di riepilogo Adobe Social <br>10:  Audience Manager di inoltro lato server utilizzato | tinyint non firmato |
| `hit_time_gmt` | La marca temporale dei server di raccolta dati del Adobe di hit  ha ricevuto l’hit, in base all’ora Unix. | int |
| `hitid_high` | Utilizzato in combinazione con `hitid_low` per identificare in modo univoco un hit. | bigint non firmato |
| `hitid_low` | Utilizzato in combinazione con `hitid_high` per identificare in modo univoco un hit. | bigint non firmato |
| `homepage` | Non più utilizzato. Indicato se l’URL corrente è la home page del browser. | char(1) |
| `hourly_visitor` | Flag per determinare se l’hit è un nuovo visitatore orario. | tinyint non firmato |
| `ip` | Indirizzo IP, basato sull’intestazione HTTP della richiesta di immagine. | char(20) |
| `ip2` | Non utilizzato. Variabile di riferimento di back-end per le suite di rapporti contenenti regole VISTA basate sull&#39;indirizzo IP. | char(20) |
| `j_jscript` | Versione di JavaScript supportata dal browser. | char(5) |
| `java_enabled` | Flag che indica se Java è abilitato. <br>Y: Abilitato <br>N: Disattivato <br>U: Sconosciuto | char(1) |
| `javascript` | ID di ricerca della versione JavaScript, in base a `j_jscript`. Utilizza la tabella di ricerca. | tinyint non firmato |
| `language` | ID numerico della lingua. Utilizza la tabella `languages.tsv` di ricerca. | numero piccolo senza segno |
| `last_hit_time_gmt` | Timestamp (in tempo Unix) dell’hit precedente. Utilizzato per calcolare la dimensione [Giorni dall&#39;ultima visita](/help/components/dimensions/days-since-last-visit.md) . | int |
| `last_purchase_num` | Variabile utilizzata nella dimensione fedeltà [](/help/components/dimensions/customer-loyalty.md) del cliente. Numero di acquisti precedenti effettuati dal visitatore. <br>0: Nessun acquisto precedente (non cliente) <br>1: 1 acquisto precedente (nuovo cliente) <br>2: 2 acquisti precedenti (cliente reso) <br>3: 3 o più acquisti precedenti (cliente leale) | int senza segno |
| `last_purchase_time_gmt` | Utilizzata nella dimensione [Giorni dall&#39;ultimo acquisto](/help/components/dimensions/days-since-last-purchase.md) . Timestamp (in Unix ora) dell’ultimo acquisto effettuato. Per gli acquisti e i visitatori che non hanno effettuato un acquisto in precedenza, questo valore è `0`. | int |
| `latlon1` | Posizione (fino a 10 chilometri) | varchar(255) |
| `latlon23` | Posizione (fino a 100 m) | varchar(255) |
| `latlon45` | Posizione (fino a 1 m) | varchar(255) |
| `mc_audiences` | Elenco degli ID  segmento di Audience Manager a cui il visitatore appartiene. | text |
| `mcvisid` | ID visitatore di Experience Cloud. Numero a 128 bit composto da due numeri concatenati a 64 bit aggiunti a 19 cifre. | varchar(255) |
| `mobile_id` | Se l&#39;utente utilizza un dispositivo mobile, l&#39;ID numerico del dispositivo. | int |
| `mobileaction` | Azione mobile. Raccolta automatica quando `trackAction` viene chiamata in Mobile Services. Consente il percorso automatico dell&#39;azione nell&#39;app. | varchar(100) |
| `mobileappid` | ID app mobile. Memorizza il nome e la versione dell&#39;applicazione nel seguente formato: `[AppName] [BundleVersion]` | varchar(255) |
| `mobileappperformanceappid` | Utilizzato nel connettore dati Apteligent. L&#39;ID app utilizzato in Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Utilizzato nel connettore dati Apteligent. L&#39;ID dell&#39;arresto anomalo utilizzato in Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Utilizzato nel connettore dati Appfigures. ID oggetto app store. | varchar(255) |
| `mobilebeaconmajor` | beacon principale Mobile Services | varchar(100) |
| `mobilebeaconminor` | beacon secondario di Mobile Services | varchar(100) |
| `mobilebeaconproximity` | Prossimità beacon Mobile Services | varchar(255) |
| `mobilebeaconuuid` | UUID beacon Mobile Services | varchar(100) |
| `mobilecampaigncontent` | Nome o ID del contenuto in cui è stato visualizzato il collegamento. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobilecampaignmedium` | Canale di marketing, ad esempio banner o e-mail. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobilecampaignname` | Nome della campagna, memorizzato anche nella variabile della campagna. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobilecampaignsource` | Referente originale, ad esempio una newsletter o una rete social media. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobilecampaignterm` | Keyword a pagamento o altri termini di cui si desidera tenere traccia con questa acquisizione. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobiledayofweek` | Numero del giorno feriale in cui è stata avviata l’app. | varchar(255) |
| `mobiledayssincefirstuse` | Numero di giorni dalla prima esecuzione dell&#39;app. | varchar(255) |
| `mobiledayssincelastupgrade` | Raccolte dalla variabile di dati contestuali a.DaysSinceLastUpgrade. Il numero di giorni trascorsi dalla sessione precedente. | varchar(255) |
| `mobiledayssincelastuse` | Numero di giorni dall&#39;ultima esecuzione dell&#39;app. | varchar(255) |
| `mobiledeeplinkid` | Raccolti dalla variabile di dati contestuali `a.deeplink.id`. Utilizzato nei rapporti di acquisizione come identificatore per il collegamento di acquisizione mobile. | varchar(255) |
| `mobiledevice` | Nome del dispositivo mobile. Su iOS, viene memorizzato come stringa di 2 cifre separate da virgola. Il primo numero rappresenta la generazione del dispositivo e il secondo numero rappresenta la famiglia di dispositivi. | varchar(255) |
| `mobilehourofday` | Definisce l&#39;ora del giorno in cui è stata avviata l&#39;app. Segue il formato numerico a 24 ore. | varchar(255) |
| `mobileinstalldate` | Data di installazione per dispositivi mobili. Fornisce la data della prima volta che un utente apre l&#39;app mobile. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Raccolti dalla variabile di dati contestuali a.LaunchesSinceUpgrade. Segnala il numero di avvii dall&#39;ultimo aggiornamento. | varchar(255) |
| `mobilelaunchnumber` | Aumenta di una volta ogni volta che l&#39;app mobile viene avviata. | varchar(255) |
| `mobileltv` | Non più utilizzato. Viene compilata dai metodi trackLifetimeValue. | varchar(255) |
| `mobilemessagebuttonname` | Raccolti dalla variabile di dati contestuali `a.message.button.id`. Utilizzata per i messaggi in-app per identificare il pulsante che ha chiuso il messaggio. | varchar(100) |
| `mobilemessageid` | ID messaggio in-app | varchar(255) |
| `mobilemessageonline` | Messaggio in-app online | varchar(255) |
| `mobilemessagepushoptin` | Raccolti dalla variabile di dati contestuali `a.push.optin`. Impostate su &quot;true&quot; quando l&#39;utente sceglie di abilitare i messaggi push; altrimenti il valore è &quot;false&quot;. | varchar(255) |
| `mobilemessagepushpayloadid` | Raccolti dalla variabile di dati contestuali `a.push.payloadid`. Utilizzato nei messaggi push come identificatore di payload. | varchar(255) |
| `mobileosenvironment` | Raccolti dalla variabile di dati contestuali `a.OSEnvironment`. Ambiente operativo stato, ad esempio Android o iOS. | varchar(255) |
| `mobileosversion` | Versione del sistema operativo Mobile Services | varchar(255) |
| `mobileplaceaccuracy` | Raccolti dalla variabile di dati contestuali `a.loc.acc`. Indica la precisione del GPS in metri al momento della raccolta. | varchar(255) |
| `mobileplacecategory` | Raccolti dalla variabile di dati contestuali `a.loc.category`. Descrive la categoria di un luogo specifico. | varchar(255) |
| `mobileplaceid` | Raccolti dalla variabile di dati contestuali `a.loc.id`. Identificatore per un dato punto di interesse. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Contenuto lancio di Mobile Services | varchar(255) |
| `mobilerelaunchcampaignmedium` | Media di avvio di Mobile Services | varchar(255) |
| `mobilerelaunchcampaignsource` | Origine avvio di Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Termine di avvio di Mobile Services | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Raccolti dalla variabile di dati contestuali `a.launch.campaign.trackingcode`. Utilizzato nell’acquisizione come codice di tracciamento per la campagna di lancio. | varchar(255) |
| `mobileresolution` | Risoluzione del dispositivo mobile. `[Width] x [Height]` in pixel. | varchar(255) |
| `monthly_visitor` | Flag che indica che il visitatore è univoco per il mese corrente. | tinyint non firmato |
| `mvvar1` - `mvvar3` | Elenca i valori delle variabili. Contiene un elenco delimitato di valori personalizzati a seconda dell&#39;implementazione. | text |
| `namespace` | Non utilizzato. Parte di una feature di scarto. | varchar(50) |
| `new_visit` | Flag che determina se l’hit corrente è una nuova visita. Impostato da  server di Adobe dopo 30 minuti di inattività della visita. | tinyint non firmato |
| `os` | ID numerico che rappresenta il sistema operativo del visitatore. Basato sulla `user_agent` colonna. Utilizza `os` la ricerca. | int senza segno |
| `p_plugins` | Non più utilizzato. Elenco di plug-in disponibili per il browser. Utilizzata la funzione JavaScript `navigator.plugins()`. | text |
| `page_event` | Tipo di hit inviato nella richiesta di immagine (hit standard, collegamento per il download, collegamento personalizzato, collegamento di uscita). See [Page event lookup](datafeeds-page-event.md). | tinyint non firmato |
| `page_event_var1` | Utilizzata solo nelle richieste di tracciamento dei collegamenti per le immagini. È stato fatto clic sull’URL del collegamento di download, del collegamento di uscita o del collegamento personalizzato. | text |
| `page_event_var2` | Utilizzata solo nelle richieste di tracciamento dei collegamenti per le immagini. Nome personalizzato (se specificato) del collegamento. | varchar(100) |
| `page_event_var3` | Non più utilizzato. Dati del modulo Survey e Media contenuti. Vengono compilati rapporti video precedenti nelle versioni precedenti di  Adobe Analytics. | text |
| `page_type` | Utilizzato per compilare la dimensione [Pagine non trovata](/help/components/dimensions/pages-not-found.md) . Utilizzata esclusivamente per 404 pagine. Questa variabile deve essere vuota o contenere il valore `ErrorPage`. | char(20) |
| `page_url` | URL dell’hit. Sono state eliminate dalle richieste di tracciamento dei collegamenti per le immagini. | varchar(255) |
| `pagename` | Utilizzato per compilare la dimensione [Pagina](/help/components/dimensions/page.md) . Se la [`pagename`](/help/implement/vars/page-vars/pagename.md) variabile è vuota, Analytics utilizza `page_url` invece. | varchar(100) |
| `paid_search` | Flag impostato se l’hit corrisponde al rilevamento della ricerca a pagamento. | tinyint non firmato |
| `partner_plugins` | Non utilizzato. Parte di una feature di scarto. | varchar(255) |
| `persistent_cookie` | Utilizzata nella dimensione [Supporto](/help/components/dimensions/persistent-cookie-support.md) cookie persistente. Indica se il visitatore supporta i cookie che non vengono scartati dopo ogni hit. | char(1) |
| `plugins` | Non più utilizzato. Elenco di ID numerici che corrispondono ai plug-in disponibili nel browser. Utilizza `plugins.tsv` la ricerca. | varchar(180) |
| `pointofinterest` | Nome del punto di interesse di Mobile Services | varchar(255) |
| `pointofinterestdistance` | Distanza da Mobile Services a punto di interesse | varchar(255) |
| `post_` column | Contiene il valore utilizzato in ultima analisi nei report. Ogni colonna di post viene compilata dopo logica lato server, regole di elaborazione e regole VISTA.  Adobe consiglia di utilizzare le colonne di post nella maggior parte dei casi. | Vedere le rispettive colonne non post |
| `prev_page` | Non utilizzato.  identificatore proprietario del Adobe della pagina precedente. | int senza segno |
| `product_list` | Elenco prodotti trasmesso attraverso la [`products`](/help/implement/vars/page-vars/products.md) variabile. I prodotti sono delimitati da virgole, mentre le singole proprietà del prodotto sono delimitate da punto e virgola. | text |
| `product_merchandising` | Non utilizzato. Usa `product_list` invece. | text |
| `prop1` - `prop75` | Variabili di traffico personalizzate 1-75. Utilizzata nelle dimensioni [Prop](/help/components/dimensions/prop.md) . | varchar(100) |
| `purchaseid` | Identificatore univoco per un acquisto, impostato utilizzando la [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md) variabile. Utilizzata dalla `duplicate_purchase` colonna. | char(20) |
| `quarterly_visitor` | Flag per determinare se l’hit è un nuovo visitatore trimestrale. | tinyint non firmato |
| `ref_domain` | Basato sulla colonna del referente. Il dominio di riferimento dell’hit. Utilizzata nella dimensione Dominio [](/help/components/dimensions/referring-domain.md) di riferimento. | varchar(100) |
| `ref_type` | Un ID numerico che rappresenta il tipo di riferimento per l&#39;hit. Utilizzata nella dimensione Tipo [](/help/components/dimensions/referrer-type.md) referente. <br>1: All&#39;interno del sito<br>2: Altri siti Web <br>3: Motori di ricerca <br>4: Disco rigido <br>5: USENET <br>6: Tipo/Segnalibro (nessun referente) <br>7: E-mail <br>8: Nessun JavaScript <br>9: Social Network | tinyint non firmato |
| `referrer` | URL pagina della pagina precedente. Utilizzata nella dimensione [Referente](/help/components/dimensions/referrer.md) . Si noti che mentre `referrer` utilizza un tipo di dati varchar(255), `post_referrer` utilizza un tipo di dati varchar(244). | varchar(255) |
| `resolution` | ID numerico che rappresenta la risoluzione del monitor. Utilizzata nella dimensione di risoluzione [del](/help/components/dimensions/monitor-resolution.md) monitor. Utilizza la tabella `resolution.tsv` di ricerca. | numero piccolo senza segno |
| `s_kwcid` | ID parola chiave utilizzato nelle integrazioni Adobe Advertising Cloud. | varchar(255) |
| `s_resolution` | Valore di risoluzione dello schermo non elaborato. Raccolte utilizzando la funzione JavaScript `screen.width x screen.height`. | char(20) |
| `sampled_hit` | Non più utilizzato. In precedenza veniva utilizzato per il campionamento in  Ad Hoc Analysis. | char(1) |
| `search_engine` | ID numerico che rappresenta il motore di ricerca che ha indirizzato il visitatore al sito. Utilizza `search_engines.tsv` la ricerca. | numero piccolo senza segno |
| `search_page_num` | Utilizzata dalla dimensione [All Search Page Rank](/help/components/dimensions/all-search-page-rank.md) . Indica in quale pagina di risultati di ricerca il sito è stato visualizzato prima che l’utente facesse clic sul sito. | numero piccolo senza segno |
| `secondary_hit` | Flag che tiene traccia degli hit secondari. Generalmente ha origine dai tag con più suite e dalle regole VISTA che copiano gli hit. | tinyint non firmato |
| `service` | Non utilizzato. Usa `page_event` invece. | char(2) |
| `socialaccountandappids` | Non più utilizzato. Account social e ID app | varchar(255) |
| `socialassettrackingcode` | Non più utilizzato. Variabile campagna social | varchar(255) |
| `socialauthor` | Non più utilizzato. Variabile Autori social | varchar(255) |
| `socialcontentprovider` | Non più utilizzato. Piattaforme/Proprietà social | varchar(255) |
| `socialinteractiontype` | Non più utilizzato. Tipo di interazione Social | varchar(255) |
| `sociallanguage` | Non più utilizzato. Lingua sociale | varchar(255) |
| `sociallatlong` | Non più utilizzato. Latitudine/longitudine social | varchar(255) |
| `socialowneddefinitioninsighttype` | Non più utilizzato. Tipo di informazioni sulla definizione di proprietà sociale | varchar(255) |
| `socialowneddefinitioninsightvalue` | Non più utilizzato. Valore di approfondimento della definizione di proprietà sociale | varchar(255) |
| `socialowneddefinitionmetric` | Non più utilizzato. Metrica di definizione social | varchar(255) |
| `socialowneddefinitionpropertyvspost` | Non più utilizzato. Proprietà definizione di proprietà social network vs post | varchar(255) |
| `socialownedpostids` | Non più utilizzato. ID post di proprietà sociale | varchar(255) |
| `socialownedpropertyid` | Non più utilizzato. ID proprietà social | varchar(255) |
| `socialownedpropertyname` | Non più utilizzato. Nome proprietà di proprietà di Social | varchar(255) |
| `socialownedpropertypropertyvsapp` | Non più utilizzato. Proprietà di proprietà social vs app | varchar(255) |
| `state` | Variabile di stato. | varchar(50) |
| `stats_server` | Non è utile.  server interno del Adobe che ha elaborato l’hit. | char(30) |
| `t_time_info` | Ora locale per il visitatore. Il formato è: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| `tnt` | Utilizzata  integrazioni Adobe Target. | text |
| `tnt_action` | Utilizzata  integrazioni Adobe Target. | text |
| `tnt_post_vista` | Non più utilizzato. Usa `post_tnt` invece. | text |
| `transactionid` | Un identificatore univoco in cui è possibile caricare vari punti dati in un secondo momento tramite origini dati. Raccolte utilizzando la [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variabile. | text |
| `truncated_hit` | Flag che indica che la richiesta di immagine è stata troncata. Indica che è stato ricevuto un hit parziale. <br>Y: Hit è stato troncato; hit parziale ricevuto <br>N: Hit non è stato troncato; hit completo ricevuto | char(1) |
| `ua_color` | Non più utilizzato. Precedentemente usato come fallback per la profondità del colore. | char(20) |
| `ua_os` | Non più utilizzato. Precedentemente utilizzato come fallback per il sistema operativo. | char(80) |
| `ua_pixels` | Non più utilizzato. Precedentemente usato come fallback per l’altezza e la larghezza del browser. | char(20) |
| `user_agent` | Stringa agente utente inviata nell’intestazione HTTP della richiesta di immagine. | text |
| `user_hash` | Non è utile. Hash sull&#39;ID della suite di rapporti. Usa `username` invece. | int senza segno |
| `user_server` | Utilizzata nella dimensione [Server](/help/components/dimensions/server.md) . | varchar(100) |
| `userid` | Non è utile. ID numerico per l&#39;ID suite di rapporti. Usa `username` invece. | int senza segno |
| `username` | ID suite di rapporti per l’hit. | char(40) |
| `va_closer_detail` | Variabile utilizzata nella dimensione [Ultimo dettaglio](/help/components/dimensions/last-touch-detail.md) tocco. | varchar(255) |
| `va_closer_id` | ID numerico che identifica la dimensione [Ultimo canale](/help/components/dimensions/last-touch-channel.md) di tocco. È possibile cercare questo ID in Marketing Channel Manager. | tinyint non firmato |
| `va_finder_detail` | Variabile utilizzata nella dimensione [Primo dettaglio](/help/components/dimensions/first-touch-detail.md) tocco. | varchar(255) |
| `va_finder_id` | ID numerico che identifica la dimensione del [primo canale](/help/components/dimensions/first-touch-channel.md) touch. È possibile cercare questo ID in Marketing Channel Manager. | tinyint non firmato |
| `va_instance_event` | Flag per identificare [le istanze](/help/components/metrics/instances.md)del canale di marketing. | tinyint non firmato |
| `va_new_engagement` | Contrassegno per identificare i [nuovi impegni](/help/components/metrics/new-engagements.md)del canale di marketing. | tinyint non firmato |
| `video` | Contenuto video | varchar(255) |
| `videoad` | Nome annuncio video | varchar(255) |
| `videoadinpod` | Annuncio video nella posizione del contenitore | varchar(255) |
| `videoadlength` | Durata video e annuncio | varchar(255) |
| `videoadload` | Caricamento di annunci video | varchar(255) |
| `videoadname` | Nome annuncio video | varchar(255) |
| `videoadplayername` | Nome del lettore di annunci video | varchar(255) |
| `videoadpod` | Video e contenitore | varchar(255) |
| `videoadvertiser` | Annuncio video | varchar(255) |
| `videoaudioalbum` | Video audio album | varchar(255) |
| `videoaudioartist` | Video audio, artista | varchar(255) |
| `videoaudioauthor` | Autore audio video | varchar(255) |
| `videoaudiolabel` | Etichetta audio video | varchar(255) |
| `videoaudiopublisher` | Editore audio video | varchar(255) |
| `videoaudiostation` | Video audio station | varchar(255) |
| `videocampaign` | Campagna video | varchar(255) |
| `videochannel` | Canale video | varchar(255) |
| `videochapter` | Nome del capitolo video | varchar(255) |
| `videocontenttype` | Tipo di contenuto video. Imposta su &quot;Video&quot; automaticamente per tutte le viste video | varchar(255) |
| `videodaypart` | Parte giorno video | varchar(255) |
| `videoepisode` | episodio video | varchar(255) |
| `videofeedtype` | Tipo di feed video | varchar(255) |
| `videogenre` | Genere video | text |
| `videolength` | Lunghezza video | varchar(255) |
| `videomvpd` | Video MVPD | varchar(255) |
| `videoname` | Nome video | varchar(255) |
| `videonetwork` | Rete video | varchar(255) |
| `videopath` | Percorso video | varchar(100) |
| `videoplayername` | Nome lettore video | varchar(255) |
| `videoqoebitrateaverageevar` | Bitrate medio della qualità video | varchar(255) |
| `videoqoebitratechangecountevar` | Conteggio modifiche qualità video | varchar(255) |
| `videoqoebuffercountevar` | Conteggio buffer qualità video | varchar(255) |
| `videoqoebuffertimeevar` | Tempo buffer qualità video | varchar(255) |
| `videoqoedroppedframecountevar` | Qualità video: numero fotogrammi saltati | varchar(255) |
| `videoqoeerrorcountevar` | Conteggio errori qualità video | varchar(255) |
| `videoqoeextneralerrors` | Errori esterni di qualità video | text |
| `videoqoeplayersdkerrors` | Errori SDK qualità video | text |
| `videoqoetimetostartevar` | Tempo di avvio della qualità video | varchar(255) |
| `videoseason` | Stagione video | varchar(255) |
| `videosegment` | Segmento video | varchar(255) |
| `videoshow` | Video show | varchar(255) |
| `videoshowtype` | Tipo di visualizzazione video | varchar(255) |
| `videostreamtype` | Tipo di flusso video | varchar(255) |
| `visid_high` | Utilizzato in combinazione con `visid_low` per identificare in modo univoco un visitatore. | bigint non firmato |
| `visid_low` | Utilizzato in combinazione con `visid_high` per identificare in modo univoco un visitatore. | bigint non firmato |
| `visid_new` | Flag per identificare se l’hit contiene un ID visitatore appena generato. | char(1) |
| `visid_timestamp` | Se l’ID visitatore è stato appena generato, fornisce la marca temporale (in Unix ora) di quando è stato generato l’ID visitatore. | int |
| `visid_type` | Non per uso esterno; utilizzato internamente dal Adobe  per l&#39;elaborazione delle ottimizzazioni. ID numerico che rappresenta il metodo utilizzato per identificare il visitatore.<br>0: ID visitatore personalizzato o Sconosciuto/non applicabile<br>1: Fallback IP e agente utente <br>2: Intestazione <br>3 utente con sottoscrizione HTTP Mobile: Valore cookie legacy (`s_vi`) <br>4: Valore cookie di fallback (`s_fid`) <br>5: Servizio identità | tinyint non firmato |
| `visit_keywords` | Variabile utilizzata nella dimensione [Cerca parola chiave](/help/components/dimensions/search-keyword.md) . Questa colonna utilizza un limite di caratteri non standard di varchar(244) per adattarlo alla logica di back-end utilizzata dal Adobe . | varchar(244) |
| `visit_num` | Variabile utilizzata nella dimensione Numero [](/help/components/dimensions/visit-number.md) visita. Inizia da 1 e incrementa ogni volta che inizia una nuova visita per visitatore. | int senza segno |
| `visit_page_num` | Variabile utilizzata nella dimensione profondità [](/help/components/dimensions/hit-depth.md) Hit. Aumenta di 1 per ogni hit generato dall’utente. Ripristina ogni visita. | int senza segno |
| `visit_ref_domain` | Basato sulla `visit_referrer` colonna. Il primo dominio di riferimento della visita. | varchar(100) |
| `visit_ref_type` | ID numerico che rappresenta il tipo di referente del primo referente della visita. Utilizza la tabella di `referrer_type.tsv` ricerca. | tinyint non firmato |
| `visit_referrer` | Il primo referente della visita. | varchar(255) |
| `visit_search_engine` | ID numerico del primo motore di ricerca della visita. Utilizza `search_engines.tsv` la ricerca. | numero piccolo senza segno |
| `visit_start_page_url` | Il primo URL della visita. | varchar(255) |
| `visit_start_pagename` | Il nome della prima pagina della visita. | varchar(100) |
| `visit_start_time_gmt` | Timestamp (in tempo Unix) del primo hit della visita. | int |
| `weekly_visitor` | Flag per determinare se l’hit è un nuovo visitatore settimanale. | tinyint non firmato |
| `yearly_visitor` | Flag per determinare se l’hit è un nuovo visitatore annuale. | tinyint non firmato |
| `zip` | Consente di compilare la dimensione del codice [](/help/components/dimensions/zip-code.md) ZIP. Vedi anche `geo_zip`. | varchar(50) |

## Colonne vuote

Il seguente elenco di colonne non è utilizzato e non contiene dati:

* `mobileacquisitionclicks`
* `mobileactioninapptime`
* `mobileactiontotaltime`
* `mobileappperformanceaffectedusers`
* `mobileappperformanceappid.app-perf-app-name`
* `mobileappperformanceappid.app-perf-platform`
* `mobileappperformancecrashes`
* `mobileappperformancecrashid.app-perf-crash-name`
* `mobileappperformanceloads`
* `mobileappstoreavgrating`
* `mobileappstoredownloads`
* `mobileappstoreinapprevenue`
* `mobileappstoreinapproyalties`
* `mobileappstoreobjectid.app-store-user`
* `mobileappstoreobjectid.application-name`
* `mobileappstoreobjectid.application-version`
* `mobileappstoreobjectid.appstore-name`
* `mobileappstoreobjectid.category-name`
* `mobileappstoreobjectid.country-name`
* `mobileappstoreobjectid.device-manufacturer`
* `mobileappstoreobjectid.device-name`
* `mobileappstoreobjectid.in-app-name`
* `mobileappstoreobjectid.platform-name-version`
* `mobileappstoreobjectid.rank-category-type`
* `mobileappstoreobjectid.region-name`
* `mobileappstoreobjectid.review-comment`
* `mobileappstoreobjectid.review-title`
* `mobileappstoreoneoffrevenue`
* `mobileappstoreoneoffroyalties`
* `mobileappstorepurchases`
* `mobileappstorerank`
* `mobileappstorerankdivisor`
* `mobileappstorerating`
* `mobileappstoreratingdivisor`
* `mobileavgprevsessionlength`
* `mobilecrashes`
* `mobilecrashrate`
* `mobiledailyengagedusers`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialpageviews`
* `socialpostviews`
* `socialproperty`
* `socialproperty (deprecated)`
* `socialpubcomments`
* `socialpubposts`
* `socialpubrecommends`
* `socialpubsubscribers`
* `socialterm`
* `socialtermslist`
* `socialtermslist (deprecated)`
* `socialtotalsentiment`
* `sourceid`
* `videoauthorized`
* `videoaverageminuteaudience`
* `videochaptercomplete`
* `videochapterstart`
* `videochaptertime`
* `videopause`
* `videopausecount`
* `videopausetime`
* `videoplay`
* `videoprogress10`
* `videoprogress25`
* `videoprogress50`
* `videoprogress75`
* `videoprogress96`
* `videoqoebitrateaverage`
* `videoqoebitratechange`
* `videoqoebuffer`
* `videoqoedropbeforestart`
* `videoqoedroppedframes`
* `videoqoeerror`
* `videoresume`
* `videototaltime`
* `videouniquetimeplayed`
