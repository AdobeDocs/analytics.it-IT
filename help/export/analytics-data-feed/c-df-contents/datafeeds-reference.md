---
description: Dati di tabella che descrivono le colonne nel feed di dati.
keywords: Feed di dati;colonne
subtopic: data feeds
title: Riferimento colonna dati
feature: Nozioni di base su Reports & Analytics e nozioni di base su Analytics
uuid: 9042a274-7124-4323-8cd6-5c84ab3eef6d
exl-id: e1492147-6e7f-4921-b509-898e7efda596
translation-type: tm+mt
source-git-commit: f9b5380cfb2cdfe1827b8ee70f60c65ff5004b48
workflow-type: tm+mt
source-wordcount: '3407'
ht-degree: 3%

---

# Riferimento colonna dati

Utilizza questa pagina per scoprire quali dati sono contenuti in ciascuna colonna. La maggior parte delle implementazioni non utilizza tutte le colonne, pertanto puoi fare riferimento a questa pagina quando determini quali colonne includere in un’esportazione di feed di dati.

>[!IMPORTANT]
>
>Per qualsiasi colonna (ad esempio, una che è definita come 255 caratteri), un feed di dati può inviare caratteri aggiuntivi a causa dell’aggiunta di caratteri che sfuggono ai valori in una stringa. Tieni presenti questi potenziali caratteri aggiuntivi se l’implementazione invia regolarmente valori che superano i limiti dei caratteri.

## Colonne, descrizioni e tipi di dati

>[!NOTE]
>
>La maggior parte delle colonne contiene una colonna simile con il prefisso `post_`. Le colonne dei post contengono valori dopo la logica lato server, le regole di elaborazione e le regole VISTA. Nella maggior parte dei casi, Adobe consiglia di utilizzare colonne di post. Per ulteriori informazioni, consulta [Domande frequenti sui feed di dati](../df-faq.md) .

| Nome colonna | Descrizione colonna | Tipo di dati |
| --- | --- | --- |
| `accept_language` | Elenca tutte le lingue accettate, come indicato nell&#39;intestazione HTTP Accept-Language in una richiesta di immagine. | char(20) |
| `aemassetid` | Variabile multivalore corrispondente ai GUID (Asset ID) di un set di Adobe Experience Manager Assets. Incrementa gli eventi di impression. | text |
| `aemassetsource` | Identifica l’origine dell’evento risorsa. Utilizzato in Adobe Experience Manager. | varchar(255) |
| `aemclickedassetid` | ID risorsa di una risorsa Adobe Experience Manager. Incrementa gli eventi di clic. | varchar(255) |
| `browser` | ID numerico del browser. Fa riferimento alla tabella di ricerca `browser.tsv` . | int senza segno |
| `browser_height` | Altezza in pixel della finestra del browser. | piccolo senza segno |
| `browser_width` | Larghezza in pixel della finestra del browser. | piccolo senza segno |
| `c_color` | Profondità in bit della palette di colori. Utilizzato come parte del calcolo della dimensione [Profondità colore](/help/components/dimensions/color-depth.md). AppMeasurement utilizza la funzione JavaScript `screen.colorDepth()`. | char(20) |
| `campaign` | Variabile utilizzata nella dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md). | varchar(255) |
| `carrier` | Variabile di integrazione Adobe Advertising Cloud. Specifica il gestore di telefonia mobile. Fa riferimento alla tabella di ricerca `carrier` . | varchar(100) |
| `channel` | Variabile utilizzata nella dimensione [Sezioni del sito](/help/components/dimensions/site-section.md). | varchar(100) |
| `click_action` | Non più utilizzato. Indirizzo di clic collegato nello strumento ClickMap legacy. | varchar(100) |
| `click_action_type` | Non più utilizzato. Tipo di collegamento dello strumento ClickMap legacy.<br>0: URL HREF<br>1: ID personalizzato<br>2: Evento onClick JavaScript<br>3: Elemento modulo | tinyint senza segno |
| `click_context` | Non più utilizzato. Nome della pagina in cui si è verificato il clic sul collegamento. Parte dello strumento ClickMap legacy. | varchar(255) |
| `click_context_type` | Non più utilizzato. Indica se click_context ha un nome di pagina o se è stato impostato in modo predefinito sull&#39;URL della pagina.<br>0: URL pagina<br>1: Nome pagina | tinyint senza segno |
| `click_sourceid` | Non più utilizzato. ID numerico della posizione sulla pagina del collegamento selezionato. Parte dello strumento ClickMap legacy. | int senza segno |
| `click_tag` | Non più utilizzato. Tipo di elemento HTML su cui è stato fatto clic. | char(10) |
| `clickmaplink` | Collegamento Activity Map | varchar(255) |
| `clickmaplinkbyregion` | Collegamento Activity Map per regione | varchar(255) |
| `clickmappage` | Pagina Activity Map | varchar(255) |
| `clickmapregion` | Area geografica di Activity Map | varchar(255) |
| `code_ver` | Versione della libreria AppMeasurement utilizzata per compilare e inviare la richiesta di immagine. | char(16) |
| `color` | ID di profondità colore in base al valore della colonna `c_color`. Fa riferimento alla tabella di ricerca `color_depth.tsv` . | piccolo senza segno |
| `connection_type` | ID numerico che rappresenta il tipo di connessione. Variabile utilizzata nella dimensione [Tipo di connessione](/help/components/dimensions/connection-type.md). Fa riferimento alla tabella di ricerca `connection_type.tsv` . | tinyint senza segno |
| `cookies` | Variabile utilizzata nella dimensione [Supporto cookie](/help/components/dimensions/cookie-support.md).<br>Y: <br>AbilitatoN: <br>DisabledU: Sconosciuto | char(1) |
| `country` | ID numerico che rappresenta il paese da cui proviene l&#39;hit. Utilizzato nella dimensione [Nazioni](/help/components/dimensions/countries.md). Utilizza la ricerca `country.tsv`. | piccolo senza segno |
| `ct_connect_type` | Correlato alla colonna `connection_type`. I valori più comuni sono LAN/Wifi, Mobile Carrier e Modem. | char(20) |
| `curr_factor` | Determina la posizione decimale della valuta e viene utilizzata per la conversione della valuta. Ad esempio, USD utilizza due posizioni decimali, quindi questo valore di colonna è 2. | tinyint |
| `curr_rate` | Il tasso di cambio al momento della transazione. Partner di Adobe con XE per determinare il tasso di cambio del giorno corrente. | decimale(24,12) |
| `currency` | Codice valuta utilizzato durante la transazione. | char(8) |
| `cust_hit_time_gmt` | Solo suite di rapporti abilitate per le marche temporali. La marca temporale inviata con l’hit, in base al tempo Unix. | int |
| `cust_visid` | Se è impostato un ID visitatore personalizzato, questo viene popolato in questa colonna. | varchar(255) |
| `daily_visitor` | Flag per determinare se l’hit è un nuovo visitatore giornaliero. | tinyint senza segno |
| `date_time` | L&#39;ora dell&#39;hit in formato leggibile, in base al fuso orario della suite di rapporti. | datetime |
| `domain` | Variabile utilizzata nella dimensione [Dominio](/help/components/dimensions/domain.md). In base al punto di accesso a Internet del visitatore. | varchar(100) |
| `duplicate_events` | Elenca ogni evento conteggiato come duplicato. | varchar(255) |
| `duplicate_purchase` | Flag che indica che l&#39;evento di acquisto per questo hit deve essere ignorato perché è un duplicato. | tinyint senza segno |
| `duplicated_from` | Utilizzato solo nelle suite di rapporti contenenti regole VISTA della copia hit. Indica la suite di rapporti da cui è stato copiato l&#39;hit. | varchar(40) |
| `ef_id` | Il `ef_id` utilizzato nelle integrazioni Adobe Advertising Cloud. | varchar(255) |
| `evar1 - evar250` | Variabili personalizzate 1-250. Utilizzato nelle dimensioni [eVar](/help/components/dimensions/evar.md). Ogni organizzazione utilizza eVar in modo diverso. Il luogo migliore per ulteriori informazioni su come la tua organizzazione compila i rispettivi eVar sarebbe un documento di progettazione della soluzione specifico per la tua organizzazione. | varchar(255) |
| `event_list` | Elenco degli ID numerici separati da virgole che rappresentano gli eventi attivati sull&#39;hit. Include eventi predefiniti ed eventi personalizzati da 1 a 1000. Utilizza la ricerca `event.tsv`. | text |
| `exclude_hit` | Flag che indica che l’hit è escluso dal rapporto. La colonna `visit_num` non viene incrementata per gli hit esclusi.<br>1: Non utilizzato. Parte di una feature di scarto.<br>2: Non utilizzato. Parte di una feature di scarto.<br>3: Non più utilizzato. Esclusione dell&#39;agente utente<br>4: Esclusione basata sull&#39;indirizzo IP<br>5: Informazioni hit vitali mancanti, ad esempio `page_url`, `pagename`, `page_event` o `event_list`<br>6: JavaScript non elabora correttamente l&#39;hit<br>7: Esclusione specifica dell’account, ad esempio in una regola VISTA<br>8: Non utilizzato. Esclusione alternativa specifica per l’account.<br>9: Non utilizzato. Parte di una feature di scarto.<br>10. Codice valuta<br>11 non valido: Hit mancante di una marca temporale in una suite di rapporti solo di marca temporale o un hit contenente una marca temporale in una suite di rapporti non di marca temporale<br>12: Non utilizzato. Parte di una feature di scarto.<br>13. Non utilizzato. Parte di una feature di scarto.<br>14. Hit di Target che non corrisponde a un hit di Analytics<br>15: Non attualmente utilizzato.<br>16. Hit Advertising Cloud che non corrisponde a un hit di Analytics | tinyint senza segno |
| `first_hit_page_url` | Il primo URL del visitatore. | varchar(255) |
| `first_hit_pagename` | Variabile utilizzata nella dimensione [Pagina di ingresso originale](/help/components/dimensions/entry-dimensions.md). Il nome originale della pagina di ingresso del visitatore. | varchar(100) |
| `first_hit_ref_domain` | Variabile utilizzata nella dimensione [Dominio di riferimento originale](/help/components/dimensions/original-referring-domain.md). Basato su `first_hit_referrer`. Il primo dominio di riferimento del visitatore. | varchar(100) |
| `first_hit_ref_type` | ID numerico che rappresenta il tipo di referente del primo referente del visitatore. Utilizza la ricerca `referrer_type.tsv`. | tinyint senza segno |
| `first_hit_referrer` | Il primo URL di riferimento del visitatore. | varchar(255) |
| `first_hit_time_gmt` | Timestamp del primo hit del visitatore in tempo Unix. | int |
| `geo_city` | Nome della città da cui proviene l’hit, in base all’IP. Utilizzato nella dimensione [Città](/help/components/dimensions/cities.md). | char(32) |
| `geo_country` | Abbreviazione del paese da cui proviene l&#39;hit, basata su IP. | char(4) |
| `geo_dma` | ID numerico dell’area demografica da cui proviene l’hit, basato su IP. Utilizzato nella dimensione [US DMA](/help/components/dimensions/us-dma.md). | int senza segno |
| `geo_region` | Nome dello stato o della regione da cui proviene l’hit, in base all’IP. Utilizzato nella dimensione [Regioni](/help/components/dimensions/regions.md). | char(32) |
| `geo_zip` | Il codice postale da cui proviene l&#39;hit, basato su IP. Consente di popolare la dimensione [Codice postale](/help/components/dimensions/zip-code.md). Vedi anche `zip`. | varchar(16) |
| `hier1 - hier5` | Utilizzato da variabili gerarchiche. Contiene un elenco delimitato di valori. Il delimitatore viene selezionato nelle impostazioni della suite di rapporti. | varchar(255) |
| `hit_source` | Indica da quale origine proviene l&#39;hit. Le fonti di hit 1, 2 e 6 vengono fatturate. <br>1: Richiesta immagine standard senza timestamp  <br>2: Richiesta immagine standard con timestamp  <br>3: Caricamento origine dati in tempo reale con timestamp  <br>4: Non utilizzato  <br>5: Caricamento origine dati generica  <br>6: Caricamento origine dati elaborazione completa  <br>7: Caricamento origine dati TransactionID  <br>8: Non più utilizzato; Versioni precedenti di origini dati Adobe Advertising Cloud  <br>9: Non più utilizzato; Metriche di riepilogo di Adobe Social  <br>10: Audience Manager inoltro lato server utilizzato | tinyint senza segno |
| `hit_time_gmt` | La marca temporale dei server di raccolta dati di Adobe di hit ha ricevuto l&#39;hit, in base all&#39;ora Unix. | int |
| `hitid_high` | Utilizzato in combinazione con `hitid_low` per identificare in modo univoco un hit. | bigotto senza segno |
| `hitid_low` | Utilizzato in combinazione con `hitid_high` per identificare in modo univoco un hit. | bigotto senza segno |
| `homepage` | Non più utilizzato. Indica se l’URL corrente è la home page del browser. | char(1) |
| `hourly_visitor` | Flag per determinare se l’hit è un nuovo visitatore orario. | tinyint senza segno |
| `ip` | Indirizzo IP, basato sull’intestazione HTTP della richiesta di immagine. | char(20) |
| `ip2` | Non utilizzato. Variabile di riferimento di back-end per suite di rapporti che contiene regole VISTA basate sull’indirizzo IP. | char(20) |
| `j_jscript` | Versione di JavaScript supportata dal browser. | char(5) |
| `java_enabled` | Flag che indica se Java è abilitato. <br>Y: Abilitato  <br>N: Disabilitato  <br>U: Sconosciuto | char(1) |
| `javascript` | ID ricerca della versione JavaScript, in base a `j_jscript`. Utilizza la tabella di ricerca. | tinyint senza segno |
| `language` | ID numerico della lingua. Utilizza la tabella di ricerca `languages.tsv`. | piccolo senza segno |
| `last_hit_time_gmt` | Timestamp (in tempo Unix) dell’hit precedente. Utilizzato per calcolare la dimensione [Giorni dall’ultima visita](/help/components/dimensions/days-since-last-visit.md) . | int |
| `last_purchase_num` | Variabile utilizzata nella dimensione [Fedeltà cliente](/help/components/dimensions/customer-loyalty.md). Il numero di acquisti precedenti effettuati dal visitatore. <br>0: Nessun acquisto precedente (non cliente)  <br>1: 1 acquisto precedente (nuovo cliente)  <br>2: 2 acquisti precedenti (cliente reso)  <br>3: 3 o più acquisti precedenti (cliente leale) | int senza segno |
| `last_purchase_time_gmt` | Utilizzato nella dimensione [Giorni dall&#39;ultimo acquisto](/help/components/dimensions/days-since-last-purchase.md). Timestamp (in tempo Unix) dell’ultimo acquisto effettuato. Per gli acquisti e i visitatori che non hanno effettuato un acquisto in precedenza, questo valore è `0`. | int |
| `latlon1` | Posizione (fino a 10 chilometri) | varchar(255) |
| `latlon23` | Posizione (fino a 100 m) | varchar(255) |
| `latlon45` | Posizione (fino a 1 m) | varchar(255) |
| `mc_audiences` | Elenco degli ID del segmento di Audience Manager a cui appartiene il visitatore. | text |
| `mcvisid` | ID visitatore di Experience Cloud. Numero a 128 bit costituito da due numeri concatenati a 64 bit aggiunti a 19 cifre. | varchar(255) |
| `mobile_id` | Se l’utente utilizza un dispositivo mobile, l’ID numerico del dispositivo. | int |
| `mobileaction` | Azione mobile. Raccolta automatica quando `trackAction` viene chiamato in Mobile Services. Consente il percorso automatico delle azioni nell’app. | varchar(100) |
| `mobileappid` | ID app mobile. Memorizza il nome e la versione dell&#39;applicazione nel seguente formato: `[AppName] [BundleVersion]` | varchar(255) |
| `mobileappperformanceappid` | Utilizzato nel connettore dati Apteligent. L&#39;ID app utilizzato in Apteligent. | varchar(255) |
| `mobileappperformancecrashid` | Utilizzato nel connettore dati Apteligent. ID dell&#39;arresto anomalo utilizzato in Apteligent. | varchar(255) |
| `mobileappstoreobjectid` | Utilizzato nel connettore dati Appfigures. ID dell&#39;oggetto dell&#39;app store. | varchar(255) |
| `mobilebeaconmajor` | Principale beacon di Mobile Services | varchar(100) |
| `mobilebeaconminor` | secondario beacon di Mobile Services | varchar(100) |
| `mobilebeaconproximity` | Prossimità beacon di Mobile Services | varchar(255) |
| `mobilebeaconuuid` | UUID beacon di Mobile Services | varchar(100) |
| `mobilecampaigncontent` | Nome o ID del contenuto che ha visualizzato il collegamento. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobilecampaignmedium` | Canale di marketing, ad esempio banner o e-mail. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobilecampaignname` | Nome della campagna, memorizzato anche nella variabile della campagna. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobilecampaignsource` | Referente originale, ad esempio newsletter o Social media network. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobilecampaignterm` | Parole chiave a pagamento o altri termini di cui tenere traccia con questa acquisizione. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| `mobiledayofweek` | Numero del giorno feriale in cui è stata avviata l’app. | varchar(255) |
| `mobiledayssincefirstuse` | Numero di giorni dalla prima esecuzione dell’app. | varchar(255) |
| `mobiledayssincelastupgrade` | Raccolto dalla variabile di dati di contesto a.DaysSinceLastUpgrade. Il numero di giorni trascorsi dalla sessione precedente. | varchar(255) |
| `mobiledayssincelastuse` | Numero di giorni dall’ultima esecuzione dell’app. | varchar(255) |
| `mobiledeeplinkid` | Raccolte dalla variabile di dati di contesto `a.deeplink.id`. Utilizzato nei rapporti di acquisizione come identificatore per il collegamento di acquisizione mobile. | varchar(255) |
| `mobiledevice` | Nome del dispositivo mobile. Su iOS, viene memorizzato come stringa di 2 cifre separate da virgola. Il primo numero rappresenta la generazione del dispositivo e il secondo numero rappresenta la famiglia di dispositivi. | varchar(255) |
| `mobilehourofday` | Definisce l&#39;ora del giorno in cui l&#39;app è stata avviata. Segue il formato numerico a 24 ore. | varchar(255) |
| `mobileinstalldate` | Data di installazione per dispositivi mobili. Fornisce la data della prima apertura dell’app mobile da parte di un utente. | varchar(255) |
| `mobilelaunchessincelastupgrade` | Raccolto dalla variabile di dati di contesto a.LaunchesSinceUpgrade. Segnala il numero di avvii dall’ultimo aggiornamento. | varchar(255) |
| `mobilelaunchnumber` | Aumenta di una volta ogni volta che l’app mobile viene avviata. | varchar(255) |
| `mobileltv` | Non più utilizzato. Viene compilata dai metodi trackLifetimeValue. | varchar(255) |
| `mobilemessagebuttonname` | Raccolte dalla variabile di dati di contesto `a.message.button.id`. Utilizzato per la messaggistica in-app per identificare il pulsante che ha chiuso il messaggio. | varchar(100) |
| `mobilemessageid` | ID messaggio in-app | varchar(255) |
| `mobilemessageonline` | Messaggi in-app online | varchar(255) |
| `mobilemessagepushoptin` | Raccolte dalla variabile di dati di contesto `a.push.optin`. Imposta su &quot;true&quot; quando l&#39;utente acconsente ai messaggi push; altrimenti il valore è &quot;false&quot;. | varchar(255) |
| `mobilemessagepushpayloadid` | Raccolte dalla variabile di dati di contesto `a.push.payloadid`. Utilizzato nei messaggi push come identificatore del payload. | varchar(255) |
| `mobileosenvironment` | Raccolte dalla variabile di dati di contesto `a.OSEnvironment`. Ambiente operativo avanzato, ad esempio Android o iOS. | varchar(255) |
| `mobileosversion` | Versione del sistema operativo Mobile Services | varchar(255) |
| `mobileplaceaccuracy` | Raccolte dalla variabile di dati di contesto `a.loc.acc`. Indica la precisione del GPS in metri al momento della raccolta. | varchar(255) |
| `mobileplacecategory` | Raccolte dalla variabile di dati di contesto `a.loc.category`. Descrive la categoria di un luogo specifico. | varchar(255) |
| `mobileplaceid` | Raccolte dalla variabile di dati di contesto `a.loc.id`. Identificatore per un dato punto di interesse. | varchar(255) |
| `mobilerelaunchcampaigncontent` | Contenuto lancio di Mobile Services | varchar(255) |
| `mobilerelaunchcampaignmedium` | Media di lancio di Mobile Services | varchar(255) |
| `mobilerelaunchcampaignsource` | Origine lancio Mobile Services | varchar(255) |
| `mobilerelaunchcampaignterm` | Termine di avvio di Mobile Services | varchar(255) |
| `mobilerelaunchcampaigntrackingcode` | Raccolte dalla variabile di dati di contesto `a.launch.campaign.trackingcode`. Utilizzato nell&#39;acquisizione come codice di tracciamento per la campagna di lancio. | varchar(255) |
| `mobileresolution` | Risoluzione del dispositivo mobile. `[Width] x [Height]` in pixel. | varchar(255) |
| `monthly_visitor` | Flag che indica che il visitatore è univoco per il mese corrente. | tinyint senza segno |
| `mvvar1` - `mvvar3` | Elencare i valori delle variabili. Contiene un elenco delimitato di valori personalizzati a seconda dell’implementazione. | text |
| `namespace` | Non utilizzato. Parte di una feature di scarto. | varchar(50) |
| `new_visit` | Flag che determina se l’hit corrente è una nuova visita. Impostato dai server di Adobe dopo 30 minuti di inattività della visita. | tinyint senza segno |
| `os` | ID numerico che rappresenta il sistema operativo del visitatore. In base alla colonna `user_agent`. Utilizza la ricerca `os`. | int senza segno |
| `p_plugins` | Non più utilizzato. Elenco dei plug-in disponibili per il browser. Uso della funzione JavaScript `navigator.plugins()`. | text |
| `page_event` | Tipo di hit inviato nella richiesta di immagine (hit standard, collegamento per il download, collegamento personalizzato, collegamento di uscita). Consulta [Ricerca eventi pagina](datafeeds-page-event.md). | tinyint senza segno |
| `page_event_var1` | Utilizzato solo nelle richieste di tracciamento delle immagini di tracciamento dei collegamenti. L&#39;URL del collegamento di download, del collegamento di uscita o del collegamento personalizzato selezionato. | text |
| `page_event_var2` | Utilizzato solo nelle richieste di tracciamento delle immagini di tracciamento dei collegamenti. Nome personalizzato (se specificato) del collegamento. | varchar(100) |
| `page_event_var3` | Non più utilizzato. Dati del modulo Survey e Media contenuti. Report video legacy compilati nelle versioni precedenti di Adobe Analytics. | text |
| `page_type` | Utilizzato per compilare la dimensione [Pagine non trovate](/help/components/dimensions/pages-not-found.md). Utilizzato esclusivamente per 404 pagine. Questa variabile deve essere vuota o contenere il valore `ErrorPage`. | char(20) |
| `page_url` | URL dell&#39;hit. Nella sua variante post (post_page_url), il valore viene rimosso per le richieste di tracciamento dei collegamenti alle immagini. | varchar(255) |
| `pagename` | Utilizzato per compilare la dimensione [Pagina](/help/components/dimensions/page.md). Se la variabile [`pagename`](/help/implement/vars/page-vars/pagename.md) è vuota, Analytics utilizza invece `page_url` . | varchar(100) |
| `paid_search` | Flag impostato se l&#39;hit corrisponde al rilevamento di ricerca a pagamento. | tinyint senza segno |
| `partner_plugins` | Non utilizzato. Parte di una feature di scarto. | varchar(255) |
| `persistent_cookie` | Utilizzato nella dimensione [Supporto cookie persistente](/help/components/dimensions/persistent-cookie-support.md) . Indica se il visitatore supporta i cookie che non vengono scartati dopo ogni hit. | char(1) |
| `plugins` | Non più utilizzato. Elenco di ID numerici corrispondenti ai plug-in disponibili nel browser. Utilizza la ricerca `plugins.tsv`. | varchar(180) |
| `pointofinterest` | Nome del punto di interesse di Mobile Services | varchar(255) |
| `pointofinterestdistance` | Distanza da Mobile Services al centro di interesse | varchar(255) |
| `post_` colonne | Contiene il valore utilizzato in ultima analisi nei rapporti. Ogni colonna post viene compilata dopo la logica lato server, le regole di elaborazione e le regole VISTA. Nella maggior parte dei casi, Adobe consiglia di utilizzare colonne di post. | Vedi la rispettiva colonna non post |
| `prev_page` | Non utilizzato. Identificatore proprietario Adobe della pagina precedente. | int senza segno |
| `product_list` | Elenco prodotti trasmesso attraverso la variabile [`products`](/help/implement/vars/page-vars/products.md). I prodotti sono delimitati da virgole, mentre le singole proprietà dei prodotti sono delimitate da punti e virgola. | text |
| `product_merchandising` | Non utilizzato. Utilizza invece `product_list` . | text |
| `prop1` -  `prop75` | Variabili di traffico personalizzate da 1 a 75. Utilizzato nelle dimensioni [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| `purchaseid` | Identificatore univoco per un acquisto, come impostato utilizzando la variabile [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Utilizzato dalla colonna `duplicate_purchase`. | char(20) |
| `quarterly_visitor` | Flag per determinare se l’hit è un nuovo visitatore trimestrale. | tinyint senza segno |
| `ref_domain` | In base alla colonna referrer. Dominio di riferimento dell&#39;hit. Utilizzato nella dimensione [Dominio di riferimento](/help/components/dimensions/referring-domain.md). | varchar(100) |
| `ref_type` | Un ID numerico che rappresenta il tipo di riferimento per l&#39;hit. Utilizzato nella dimensione [Tipo referente](/help/components/dimensions/referrer-type.md). <br>1: All&#39;interno del tuo sito<br>2: Altri siti web  <br>3: Motori di ricerca  <br>4: Disco rigido  <br>5: USENET  <br>6: Digitato/Segnalibro (senza referrer)  <br>7: E-mail  <br>8: JavaScript  <br>9 non disponibile: Social network | tinyint senza segno |
| `referrer` | URL della pagina precedente. Utilizzato nella dimensione [Referrer](/help/components/dimensions/referrer.md). Nota che mentre `referrer` utilizza un tipo di dati varchar(255), `post_referrer` utilizza un tipo di dati varchar(244). | varchar(255) |
| `resolution` | ID numerico che rappresenta la risoluzione del monitoraggio. Utilizzato nella dimensione [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md). Utilizza la tabella di ricerca `resolution.tsv`. | piccolo senza segno |
| `s_kwcid` | ID parola chiave utilizzato nelle integrazioni Adobe Advertising Cloud. | varchar(255) |
| `s_resolution` | Valore di risoluzione dello schermo non elaborato. Raccolto utilizzando la funzione JavaScript `screen.width x screen.height`. | char(20) |
| `search_engine` | ID numerico che rappresenta il motore di ricerca che ha indirizzato il visitatore al sito. Utilizza la ricerca `search_engines.tsv`. | piccolo senza segno |
| `search_page_num` | Utilizzato dalla dimensione [All Search Page Rank](/help/components/dimensions/all-search-page-rank.md). Indica in quale pagina dei risultati di ricerca il sito è stato visualizzato prima che l’utente avesse fatto clic sul sito. | piccolo senza segno |
| `secondary_hit` | Flag che tiene traccia degli hit secondari. In genere proviene dall’assegnazione di tag a più suite e dalle regole VISTA che consentono di copiare gli hit. | tinyint senza segno |
| `service` | Non utilizzato. Utilizza invece `page_event` . | char(2) |
| `socialaccountandappids` | Non più utilizzato. Account social e ID app | varchar(255) |
| `socialassettrackingcode` | Non più utilizzato. Variabile della campagna social | varchar(255) |
| `socialauthor` | Non più utilizzato. Variabile Autori social | varchar(255) |
| `socialcontentprovider` | Non più utilizzato. Piattaforme/proprietà social | varchar(255) |
| `socialinteractiontype` | Non più utilizzato. Tipo di interazione social | varchar(255) |
| `sociallanguage` | Non più utilizzato. Lingua sociale | varchar(255) |
| `sociallatlong` | Non più utilizzato. Latitudine/longitudine social | varchar(255) |
| `socialowneddefinitioninsighttype` | Non più utilizzato. Tipo di informazioni sulla definizione di proprietà social | varchar(255) |
| `socialowneddefinitioninsightvalue` | Non più utilizzato. Valore insight della definizione di proprietà social | varchar(255) |
| `socialowneddefinitionmetric` | Non più utilizzato. Metrica di definizione di proprietà social | varchar(255) |
| `socialowneddefinitionpropertyvspost` | Non più utilizzato. Proprietà di proprietà social di definizione vs. post | varchar(255) |
| `socialownedpostids` | Non più utilizzato. ID post di proprietà sociale | varchar(255) |
| `socialownedpropertyid` | Non più utilizzato. ID proprietà social | varchar(255) |
| `socialownedpropertyname` | Non più utilizzato. Nome proprietà di proprietà social | varchar(255) |
| `socialownedpropertypropertyvsapp` | Non più utilizzato. Proprietà di proprietà social vs. app | varchar(255) |
| `state` | Variabile di stato. | varchar(50) |
| `stats_server` | Non è utile. Adobe di server interno che ha elaborato l&#39;hit. | char(30) |
| `t_time_info` | Ora locale del visitatore. Il formato è: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| `tnt` | Utilizzato nelle integrazioni Adobe Target. | text |
| `tnt_action` | Utilizzato nelle integrazioni Adobe Target. | text |
| `tnt_post_vista` | Non più utilizzato. Utilizza invece `post_tnt` . | text |
| `transactionid` | Identificatore univoco in cui è possibile caricare diversi punti dati in un secondo momento tramite origini dati. Raccolte utilizzando la variabile [`transactionID`](/help/implement/vars/page-vars/transactionid.md) . | text |
| `truncated_hit` | Flag che indica che la richiesta di immagine è stata troncata. Indica che è stato ricevuto un hit parziale. <br>Y: Hit troncato; hit parziale ricevuto  <br>N: Hit non troncato; hit completo ricevuto | char(1) |
| `ua_color` | Non più utilizzato. Precedentemente utilizzato come fallback per la profondità del colore. | char(20) |
| `ua_os` | Non più utilizzato. Precedentemente utilizzato come fallback per il sistema operativo. | char(80) |
| `ua_pixels` | Non più utilizzato. Precedentemente utilizzato come fallback per l’altezza e la larghezza del browser. | char(20) |
| `user_agent` | Stringa dell&#39;agente utente inviata nell&#39;intestazione HTTP della richiesta di immagine. | text |
| `user_hash` | Non è utile. Hash sull&#39;ID suite di rapporti. Utilizza invece `username` . | int senza segno |
| `user_server` | Utilizzato nella dimensione [Server](/help/components/dimensions/server.md). | varchar(100) |
| `userid` | Non è utile. ID numerico dell&#39;ID suite di rapporti. Utilizza invece `username` . | int senza segno |
| `username` | ID suite di rapporti per l&#39;hit. | char(40) |
| `va_closer_detail` | Variabile utilizzata nella dimensione [Dettaglio ultimo contatto](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| `va_closer_id` | ID numerico che identifica la dimensione [Canale ultimo contatto](/help/components/dimensions/last-touch-channel.md) . La ricerca per questo ID si trova in Marketing Channel Manager. | tinyint senza segno |
| `va_finder_detail` | Variabile utilizzata nella dimensione [Dettaglio primo contatto](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| `va_finder_id` | ID numerico che identifica la dimensione [Primo canale di contatto](/help/components/dimensions/first-touch-channel.md) . La ricerca per questo ID si trova in Marketing Channel Manager. | tinyint senza segno |
| `va_instance_event` | Flag per identificare le istanze del canale di marketing [Istanze](/help/components/metrics/instances.md). | tinyint senza segno |
| `va_new_engagement` | Flag per identificare il canale di marketing [Nuovi impegni](/help/components/metrics/new-engagements.md). | tinyint senza segno |
| `video` | Contenuto video | varchar(255) |
| `videoad` | Nome annuncio video | varchar(255) |
| `videoadinpod` | Video annuncio in posizione pozzo | varchar(255) |
| `videoadlength` | Lunghezza annuncio video | varchar(255) |
| `videoadload` | Caricamenti di annunci video | varchar(255) |
| `videoadname` | Nome annuncio video | varchar(255) |
| `videoadplayername` | Nome del lettore di annunci video | varchar(255) |
| `videoadpod` | Video annuncio pod | varchar(255) |
| `videoadvertiser` | Inserzionista video | varchar(255) |
| `videoaudioalbum` | Album audio video | varchar(255) |
| `videoaudioartist` | Video audio | varchar(255) |
| `videoaudioauthor` | Autore audio video | varchar(255) |
| `videoaudiolabel` | Etichetta audio video | varchar(255) |
| `videoaudiopublisher` | Pubblicazione audio video | varchar(255) |
| `videoaudiostation` | Video audio | varchar(255) |
| `videocampaign` | Campagna video | varchar(255) |
| `videochannel` | Canale video | varchar(255) |
| `videochapter` | Nome del capitolo video | varchar(255) |
| `videocontenttype` | Tipo di contenuto video. Imposta automaticamente su &quot;Video&quot; per tutte le visualizzazioni video | varchar(255) |
| `videodaypart` | Parte giorno video | varchar(255) |
| `videoepisode` | episodio video | varchar(255) |
| `videofeedtype` | Tipo di feed video | varchar(255) |
| `videogenre` | Genere video | text |
| `videolength` | Lunghezza del video | varchar(255) |
| `videomvpd` | MVPD video | varchar(255) |
| `videoname` | Nome video | varchar(255) |
| `videonetwork` | Rete video | varchar(255) |
| `videopath` | Percorso video | varchar(100) |
| `videoplayername` | Nome del lettore video | varchar(255) |
| `videoqoebitrateaverageevar` | Bit rate medio della qualità video | varchar(255) |
| `videoqoebitratechangecountevar` | Conteggio dei cambiamenti nella qualità video | varchar(255) |
| `videoqoebuffercountevar` | Conteggio buffer qualità video | varchar(255) |
| `videoqoebuffertimeevar` | Tempo buffer qualità video | varchar(255) |
| `videoqoedroppedframecountevar` | Numero di fotogrammi saltati della qualità video | varchar(255) |
| `videoqoeerrorcountevar` | Numero di errori nella qualità video | varchar(255) |
| `videoqoeextneralerrors` | Errori esterni nella qualità video | text |
| `videoqoeplayersdkerrors` | Errori SDK di qualità video | text |
| `videoqoetimetostartevar` | Tempo di avvio della qualità video | varchar(255) |
| `videoseason` | Stagione video | varchar(255) |
| `videosegment` | Segmento video | varchar(255) |
| `videoshow` | Video show | varchar(255) |
| `videoshowtype` | Tipo di presentazione video | varchar(255) |
| `videostreamtype` | Tipo di flusso video | varchar(255) |
| `visid_high` | Utilizzato in combinazione con `visid_low` per identificare in modo univoco un visitatore. | bigotto senza segno |
| `visid_low` | Utilizzato in combinazione con `visid_high` per identificare in modo univoco un visitatore. | bigotto senza segno |
| `visid_new` | Flag per identificare se l&#39;hit contiene un ID visitatore appena generato. | char(1) |
| `visid_timestamp` | Se l&#39;ID visitatore è stato generato di recente, fornisce la marca temporale (in tempo Unix) di quando è stato generato l&#39;ID visitatore. | int |
| `visid_type` | Non per uso esterno; Utilizzato internamente da Adobe per l’elaborazione delle ottimizzazioni. ID numerico che rappresenta il metodo utilizzato per identificare il visitatore.<br>0: ID visitatore personalizzato o sconosciuto/non applicabile<br>1: Fallback  <br>2 dell’agente IP e dell’agente utente: Intestazione  <br>3 del sottoscrittore mobile HTTP: Valore cookie legacy (`s_vi`)  <br>4: Valore cookie di fallback (`s_fid`)  <br>5: Servizio identità | tinyint senza segno |
| `visit_keywords` | Variabile utilizzata nella dimensione [Cerca parola chiave](/help/components/dimensions/search-keyword.md). Questa colonna utilizza un limite di caratteri non standard di varchar(244) per adattarsi alla logica back-end utilizzata da Adobe. | varchar(244) |
| `visit_num` | Variabile utilizzata nella dimensione [Numero visita](/help/components/dimensions/visit-number.md). Inizia a 1 e viene incrementato ogni volta che inizia una nuova visita per visitatore. | int senza segno |
| `visit_page_num` | Variabile utilizzata nella dimensione [Profondità hit](/help/components/dimensions/hit-depth.md). Aumenta di 1 per ogni hit generato dall’utente. Ripristina ogni visita. | int senza segno |
| `visit_ref_domain` | In base alla colonna `visit_referrer`. Il primo dominio di riferimento della visita. | varchar(100) |
| `visit_ref_type` | ID numerico che rappresenta il tipo di referente del primo referente della visita. Utilizza la tabella di ricerca `referrer_type.tsv`. | tinyint senza segno |
| `visit_referrer` | Il primo referente della visita. | varchar(255) |
| `visit_search_engine` | ID numerico del primo motore di ricerca della visita. Utilizza la ricerca `search_engines.tsv`. | piccolo senza segno |
| `visit_start_page_url` | Il primo URL della visita. | varchar(255) |
| `visit_start_pagename` | Nome pagina della visita. | varchar(100) |
| `visit_start_time_gmt` | Timestamp (in tempo Unix) del primo hit della visita. | int |
| `weekly_visitor` | Flag per determinare se l’hit è un nuovo visitatore settimanale. | tinyint senza segno |
| `yearly_visitor` | Flag per determinare se l’hit è un nuovo visitatore annuale. | tinyint senza segno |
| `zip` | Consente di popolare la dimensione [Codice postale](/help/components/dimensions/zip-code.md). Vedi anche `geo_zip`. | varchar(50) |

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
