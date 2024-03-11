---
description: Dati di tabella che descrivono le colonne nel feed di dati.
keywords: Feed di dati; colonne
subtopic: data feeds
title: Riferimento colonna dati
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 6fbfaf295899b77fc22f79ee58b70a19c7e5563c
workflow-type: tm+mt
source-wordcount: '3928'
ht-degree: 98%

---

# Riferimento colonna dati

Utilizza questa pagina per scoprire quali dati sono contenuti in ciascuna colonna. La maggior parte delle implementazioni non utilizza tutte le colonne, pertanto puoi fare riferimento a questa pagina quando determini quali colonne includere in un’esportazione di feed di dati.

>[!IMPORTANT]
>
>Per una determinata colonna (ad esempio, quella definita come 255 caratteri), un feed di dati può inviare caratteri aggiuntivi a causa dell’aggiunta di caratteri che sfuggono ai valori in una stringa. Tieni presente questi potenziali caratteri aggiuntivi se l’implementazione invia regolarmente valori che superano i limiti dei caratteri.

## Colonne, descrizioni e tipi di dati

>[!NOTE]
>
>La maggior parte delle colonne contiene una colonna simile con il prefisso `post_`. Le colonne post contengono valori dopo la logica lato server, le regole di elaborazione e le regole VISTA. Nella maggior parte dei casi, Adobe consiglia di utilizzare colonne post. Per ulteriori informazioni, consulta [Domande frequenti sui feed di dati](../df-faq.md).

Gli aggiornamenti precedenti a questa tabella si trovano nella [cronologia dei commit su GitHub](https://github.com/AdobeDocs/analytics.en/commits/main/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md) di questa pagina.

| Nome colonna | Descrizione colonna | Tipo di dati |
| --- | --- | --- |
| **`accept_language`** | Elenca tutte le lingue accettate, come indicato nell’intestazione HTTP Accetta-Lingua in una richiesta di immagine. | char(20) |
| **`adload`** | Caricamenti di annunci multimediali | varchar(255) |
| **`aemassetid`** | Variabile multivalore corrispondente ai GUID (ID risorsa) di un set di Adobe Experience Manager Assets. Incrementa gli eventi di impression. | testo |
| **`aemassetsource`** | Identifica l’origine dell’evento risorsa. Utilizzato in Adobe Experience Manager. | varchar(255) |
| **`aemclickedassetid`** | ID risorsa di una risorsa di Adobe Experience Manager. Incrementa gli eventi di clic. | varchar(255) |
| **`browser`** | ID numerico del browser. Fa riferimento alla tabella di ricerca `browser.tsv`. | int senza segno |
| **`browser_height`** | Altezza in pixel della finestra del browser. | smallint senza segno |
| **`browser_width`** | Larghezza in pixel della finestra del browser. | smallint senza segno |
| **`c_color`** | Profondità in bit della palette di colori. Utilizzato come parte del calcolo della dimensione [Profondità colore](/help/components/dimensions/color-depth.md). AppMeasurement utilizza la funzione `screen.colorDepth()` di JavaScript. | char(20) |
| **`campaign`** | Variabile utilizzata nella dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md). | varchar(255) |
| **`carrier`** | Variabile di integrazione di Adobe Advertising. Specifica il gestore di telefonia mobile. Valore chiave per [Ricerca dinamica](dynamic-lookups.md) `carrier.tsv`. | varchar(100) |
| **`ch_hdr`** | Hint client raccolti tramite l’intestazione della richiesta HTTP. | testo |
| **`ch_js`** | Hint client raccolti tramite l’API JavaScript per gli hint client dall’agente utente | testo |
| **`channel`** | Variabile utilizzata nella dimensione [Sezioni del sito](/help/components/dimensions/site-section.md). | varchar(100) |
| **`click_action`** | Non più utilizzato. Indirizzo del collegamento su cui è stato fatto clic nello strumento legacy ClickMap. | varchar(100) |
| **`click_action_type`** | Non più utilizzato. Tipo di collegamento dello strumento legacy ClickMap.<br>0: URL HREF<br>1: ID personalizzato<br>2: Evento onClick JavaScript<br>3: Elemento modulo | tinyint unsigned |
| **`click_context`** | Non più utilizzato. Nome della pagina in cui si è verificato il clic sul collegamento. Parte dello strumento legacy ClickMap. | varchar(255) |
| **`click_context_type`** | Non più utilizzato. Indica se `click_context` aveva un nome di pagina o è stato impostato come URL predefinito per la pagina.<br>0: URL della pagina<br>1: Nome pagina | tinyint unsigned |
| **`click_sourceid`** | Non più utilizzato. ID numerico della posizione sulla pagina del collegamento in cui è stato fatto clic. Parte dello strumento legacy ClickMap. | int senza segno |
| **`click_tag`** | Non più utilizzato. Tipo di elemento HTML su cui è stato fatto clic. | char(10) |
| **`clickmaplink`** | Collegamento ad Activity Map | varchar(255) |
| **`clickmaplinkbyregion`** | Collegamento ad Activity Map per area geografica | varchar(255) |
| **`clickmappage`** | Pagina di Activity Map | varchar(255) |
| **`clickmapregion`** | Area geografica di Activity Map | varchar(255) |
| **`code_ver`** | Versione API o client SDK utilizzata per compilare e inviare la richiesta di immagine. | char(16) |
| **`color`** | ID di profondità colore in base al valore della colonna `c_color`. Fa riferimento alla tabella di ricerca `color_depth.tsv`. | smallint senza segno |
| **`connection_type`** | ID numerico che rappresenta il tipo di connessione. Variabile utilizzata nella dimensione [Tipo di connessione](/help/components/dimensions/connection-type.md). Fa riferimento alla tabella di ricerca `connection_type.tsv`. | tinyint unsigned |
| **`cookies`** | Variabile utilizzata nella dimensione [Supporto cookie](/help/components/dimensions/cookie-support.md).<br>Y: abilitato<br>N: disabilitato<br>U: sconosciuto | char(1) |
| **`country`** | ID numerico che rappresenta i valori presenti nella ricerca nel file `country.tsv`. | smallint senza segno |
| **`ct_connect_type`** | Correlato alla colonna `connection_type`. I valori più comuni sono LAN/Wi-Fi, Gestore di telefonia mobile e Modem. | char(20) |
| **`curr_factor`** | Determina la posizione dei decimali della valuta e viene utilizzato per la conversione della valuta. Ad esempio, USD utilizza due posizioni decimali, quindi questo valore di colonna è 2. | Tinyint |
| **`curr_rate`** | Il tasso di cambio al momento della transazione. Adobe si appoggia a XE per determinare il tasso di cambio del giorno corrente. | decimal(24,12) |
| **`currency`** | Codice valuta utilizzato durante la transazione. | char(8) |
| **`cust_hit_time_gmt`** | Solo suite di rapporti abilitate per la marca temporale. La marca temporale inviata con l’hit, in base al tempo UNIX®. | Intero |
| **`cust_visid`** | Se è impostato un ID visitatore personalizzato, questo viene popolato in questa colonna. | varchar(255) |
| **`daily_visitor`** | Flag per determinare se l’hit è un nuovo visitatore giornaliero. | tinyint unsigned |
| **`dataprivacyconsentoptin`** | Variabile utilizzata nella dimensione [Consenso alla gestione del consenso](/help/components/dimensions/cm-opt-in.md). È possibile che siano presenti più valori per hit, separati da una barra verticale (`\|`). I valori validi includono `DMP` e `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | Variabile utilizzata nella dimensione [Rinuncia alla gestione del consenso](/help/components/dimensions/cm-opt-out.md). È possibile che siano presenti più valori per hit, separati da una barra verticale (`\|`). I valori validi includono `SSF`, `DMP` e `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | Valore che identifica se il consenso è acquisito per l’invio di dati da Adobe Analytics tramite Adobi Advertising a provider pubblicitari di terze parti (come Google). Consulta [Consenso annuncio](/help/components/dimensions/ad-consent.md) per ulteriori informazioni. | varchar(100) |
| **`date_time`** | L’ora dell’hit in formato leggibile, in base al fuso orario della suite di rapporti. | Datetime |
| **`domain`** | Variabile utilizzata nella dimensione [Dominio](/help/components/dimensions/domain.md). In base al punto di accesso a Internet del visitatore. | varchar(100) |
| **`duplicate_events`** | Elenca ogni evento conteggiato come duplicato. | varchar(255) |
| **`duplicate_purchase`** | Flag che indica che l’evento di acquisto per questo hit viene ignorato perché è un duplicato. | tinyint unsigned |
| **`duplicated_from`** | Utilizzato solo nelle suite di rapporti contenenti regole VISTA della copia hit. Indica la suite di rapporti da cui è stato copiato l’hit. | varchar(40) |
| **`ef_id`** | Valore `ef_id` utilizzato nelle integrazioni di Adobe Advertising.  | varchar(255) |
| **`evar1 - evar250`** | Variabili personalizzate 1-250. Utilizzato nelle dimensioni [eVar](/help/components/dimensions/evar.md). Ogni organizzazione utilizza le eVar in modo diverso. Il luogo migliore per ulteriori informazioni su come la tua organizzazione compila le rispettive eVar sarebbe un documento di progettazione della soluzione specifico per la tua organizzazione. | varchar(255) |
| **`event_list`** | Elenco di ID numerici separati da virgole che rappresentano gli eventi attivati sull’hit. Include eventi predefiniti ed eventi personalizzati da 1 a 1.000. Usa la ricerca `event.tsv`. | testo |
| **`exclude_hit`** | Flag che indica che l’hit è escluso dal reporting. La colonna `visit_num` non viene incrementata per gli hit esclusi.<br>1: non utilizzato. Parte di una funzione scartata.<br>2: non utilizzato. Parte di una funzione scartata.<br>3: non più utilizzato. Esclusione dell’agente utente<br>4: esclusione basata sull’indirizzo IP<br>5: informazioni hit vitali mancanti, ad esempio `page_url`, `pagename`, `page_event` oppure `event_list`<br>6: JavaScript non ha elaborato correttamente gli hit<br>7: esclusione specifica dell’account, ad esempio in una regola VISTA<br>8: non utilizzato. Esclusione alternativa specifica per l’account.<br>9: non utilizzato. Parte di una funzione scartata.<br>10: codice valuta non valido<br>11: hit mancante di una marca temporale in una suite di rapporti solo di marca temporale o un hit contenente una marca temporale in una suite di rapporti non di marca temporale<br>12: non utilizzato. Parte di una funzione scartata.<br>13: non utilizzato. Parte di una funzione scartata.<br>14: hit di destinazione che non corrisponde a un hit di Analytics<br>15: non attualmente utilizzato.<br>16: hit di Advertising Cloud che non corrisponde a un hit di Analytics | tinyint unsigned |
| **`first_hit_page_url`** | Il primo URL del visitatore. | varchar(255) |
| **`first_hit_pagename`** | Variabile utilizzata nella dimensione [Pagina di ingresso originale](/help/components/dimensions/entry-dimensions.md). Il nome della pagina di ingresso originale del visitatore. | varchar(100) |
| **`first_hit_ref_domain`** | Variabile utilizzata nella dimensione [Dominio di riferimento originale](/help/components/dimensions/original-referring-domain.md). In base a `first_hit_referrer`. Il primo dominio di provenienza del visitatore. | varchar(100) |
| **`first_hit_ref_type`** | ID numerico che rappresenta il tipo di referrer del primo referrer del visitatore. Usa la ricerca `referrer_type.tsv`. | tinyint unsigned |
| **`first_hit_referrer`** | Il primo URL di provenienza del visitatore. | varchar(255) |
| **`first_hit_time_gmt`** | Marca temporale del primo hit del visitatore in tempo UNIX®. | Intero |
| **`geo_city`** | Nome della città da cui proviene l’hit, in base all’IP. Utilizzato nella dimensione [Città](/help/components/dimensions/cities.md). | char(32) |
| **`geo_country`** | Abbreviazione del Paese da cui proviene l’hit, basata su IP. Utilizzato nella dimensione [Paesi](/help/components/dimensions/countries.md). | char(4) |
| **`geo_dma`** | ID numerico dell’area demografica di origine dell’hit, basato su IP. Utilizzato nella dimensione [DMA USA](/help/components/dimensions/us-dma.md). | int senza segno |
| **`geo_region`** | Nome dello stato o dell’area geografica da cui proviene l’hit, in base all’IP. Utilizzato nella dimensione [Aree geografiche](/help/components/dimensions/regions.md). | char(32) |
| **`geo_zip`** | Il codice postale di origine dell’hit, basato su IP. Consente di popolare la dimensione [Codice postale](/help/components/dimensions/zip-code.md). Consulta anche `zip`. | varchar(16) |
| **`hier1 - hier5`** | Utilizzato da variabili gerarchiche. Contiene un elenco delimitato di valori. Il delimitatore viene selezionato nelle impostazioni della suite di rapporti. | varchar(255) |
| **`hit_source`** | Indica l’origine dalla quale proviene l’hit. Le origini di hit 1, 2 e 6 vengono fatturate. <br>1: richiesta immagine standard senza marca temporale <br>2: richiesta immagine standard con marca temporale <br>3: caricamento origine dati live con marca temporale <br>4: non utilizzato <br>5: caricamento origine dati generica <br>6: caricamento origine dati a elaborazione completa <br>7: caricamento origine dati TransactionID <br>8: non più utilizzato; versioni precedenti di origini dati di Adobe Advertising Cloud <br>9: non più utilizzato; metriche di riepilogo di Adobe Social <br>10: inoltro lato server Audience Manager utilizzato | tinyint unsigned |
| **`hit_time_gmt`** | La marca temporale dei server Adobe di raccolta dati degli hit ha ricevuto l’hit, in base all’ora UNIX®. | Intero |
| **`hitid_high`** | Utilizzato con `hitid_low` per identificare un hit. | Bigint senza segno |
| **`hitid_low`** | Utilizzato con `hitid_high` per identificare un hit. | Bigint senza segno |
| **`homepage`** | Non più utilizzato. Indica se l’URL corrente è la home page del browser. | char(1) |
| **`hourly_visitor`** | Flag per determinare se l’hit è un nuovo visitatore orario. | tinyint unsigned |
| **`ip`** | L’indirizzo IPv4, in base all’intestazione HTTP della richiesta di immagine. Reciprocamente esclusivo per `ipv6`; se questa colonna contiene un indirizzo IP non offuscato, `ipv6` è vuoto. | char(20) |
| **`ip2`** | Non utilizzato. Variabile di riferimento di back-end per suite di rapporti contenenti regole VISTA basate sull’indirizzo IP. | char(20) |
| **`ipv6`** | Indirizzo IPv6 compresso, se disponibile. Reciprocamente esclusivo per `ip`; se questa colonna contiene un indirizzo IP non offuscato, `ip` è vuoto. | varchar(40) |
| **`j_jscript`** | Versione di JavaScript supportata dal browser. | char(5) |
| **`java_enabled`** | Flag che indica se Java è abilitato. <br>Y: abilitato <br>N: disabilitato <br>U: sconosciuto | char(1) |
| **`javascript`** | ID di ricerca della versione JavaScript, in base a `j_jscript`. Fa riferimento alla tabella di ricerca `javascript_version`. | tinyint unsigned |
| **`language`** | ID numerico della lingua. Usa la tabella di ricerca `languages.tsv`. | smallint senza segno |
| **`last_hit_time_gmt`** | Marca temporale (in ora UNIX®) dell’hit precedente. Utilizzato per calcolare la dimensione [Giorni dall’ultima visita](/help/components/dimensions/days-since-last-visit.md). | Intero |
| **`last_purchase_num`** | Variabile utilizzata nella dimensione [Fedeltà del cliente](/help/components/dimensions/customer-loyalty.md). Il numero di acquisti precedenti effettuati dal visitatore. <br>0: nessun acquisto precedente (non è un cliente) <br>1: 1 acquisto precedente (nuovo cliente) <br>2: 2 acquisti precedenti (cliente di ritorno) <br>3: 3 o più acquisti precedenti (cliente abituale) | int senza segno |
| **`last_purchase_time_gmt`** | Utilizzato nella dimensione [Giorni dall’ultimo acquisto](/help/components/dimensions/days-since-last-purchase.md). Marca temporale (in ora UNIX®) dell’ultimo acquisto effettuato. Per i nuovi acquisti e i visitatori che non hanno effettuato un acquisto in precedenza, questo valore è `0`. | Intero |
| **`latlon1`** | Posizione (fino a 10 chilometri) | varchar(255) |
| **`latlon23`** | Posizione (fino a 100 m) | varchar(255) |
| **`latlon45`** | Posizione (fino a 1 m) | varchar(255) |
| **`mc_audiences`** | Elenco degli ID del segmento di Audience Manager a cui appartiene il visitatore. Nella colonna `post_mc_audiences` il delimitatore diventa `--**--`. | testo |
| **`mcvisid`** | ID visitatore di Experience Cloud. Numero a 128 bit costituito da due numeri concatenati a 64 bit aggiunti a 19 cifre. | varchar(255) |
| **`mobile_id`** | Se l’utente utilizza un dispositivo mobile, l’ID numerico del dispositivo. Il valore chiave per `mobile_attributes.tsv` [Ricerca dinamica](dynamic-lookups.md). | Intero |
| **`mobileaction`** | Azione da dispositivo mobile. Raccolta automatica quando `trackAction` viene chiamato in Mobile Services. Consente il percorso automatico delle azioni nell’app. | varchar(100) |
| **`mobileappid`** | ID dell’app mobile. Memorizza il nome e la versione dell&#39;applicazione nel seguente formato: `[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | Utilizzato nel connettore dati Apteligent. L’ID app utilizzato in Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Utilizzato nel connettore dati Apteligent. ID di arresto anomalo utilizzato in Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Utilizzato nel connettore dati Appfigures. ID dell’oggetto nell’app store. | varchar(255) |
| **`mobilebeaconmajor`** | Beacon principale di Mobile Services | varchar(100) |
| **`mobilebeaconminor`** | Beacon secondario di Mobile Services | varchar(100) |
| **`mobilebeaconproximity`** | Prossimità beacon di Mobile Services | varchar(255) |
| **`mobilebeaconuuid`** | UUID del beacon di Mobile Services | varchar(100) |
| **`mobilecampaigncontent`** | Nome o ID del contenuto che ha visualizzato il collegamento. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobilecampaignmedium`** | Canale di marketing, ad esempio banner o e-mail. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobilecampaignname`** | Nome della campagna, memorizzato anche nella variabile della campagna. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobilecampaignsource`** | Referente originale, ad esempio newsletter o Social media network. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobilecampaignterm`** | Parole chiave a pagamento o altri termini di cui tenere traccia con questa acquisizione. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobiledayofweek`** | Numero del giorno della settimana in cui è stata avviata l’app. | varchar(255) |
| **`mobiledayssincefirstuse`** | Numero di giorni dalla prima esecuzione dell’app. | varchar(255) |
| **`mobiledayssincelastupgrade`** | Ritirato - Raccolto dalla variabile di dati di contesto a.DaysSinceLastUpgrade. Il numero di giorni trascorsi dalla sessione precedente. | varchar(255) |
| **`mobiledayssincelastuse`** | Numero di giorni dall’ultima esecuzione dell’app. | varchar(255) |
| **`mobiledeeplinkid`** | Raccolto dalla variabile di dati di contesto `a.deeplink.id`. Utilizzato nei rapporti di acquisizione come identificatore per il collegamento di acquisizione mobile. | varchar(255) |
| **`mobiledevice`** | Nome del dispositivo mobile. In iOS, viene memorizzato come stringa di 2 cifre separate da virgola. Il primo numero rappresenta la generazione del dispositivo e il secondo rappresenta la famiglia di dispositivi. | varchar(255) |
| **`mobilehourofday`** | Definisce l’ora del giorno in cui l’app è stata avviata. Segue il formato numerico di 24 ore. | varchar(255) |
| **`mobileinstalldate`** | Data di installazione dell’app mobile. Fornisce la data della prima apertura dell’app mobile da parte di un utente. | varchar(255) |
| **`mobilelaunchessincelastupgrade`** | Ritirato - Raccolto dalla variabile di dati di contesto a.LaunchesSinceUpgrade. Segnala il numero di avvii dall’ultimo aggiornamento. | varchar(255) |
| **`mobilelaunchnumber`** | Aumenta di uno ogni volta che l’app mobile viene avviata. | varchar(255) |
| **`mobileltv`** | Non più utilizzato. Compilato dai metodi trackLifetimeValue. | varchar(255) |
| **`mobilemessagebuttonname`** | Raccolto dalla variabile di dati di contesto `a.message.button.id`. Utilizzato per la messaggistica in-app per identificare il pulsante che ha chiuso il messaggio. | varchar(100) |
| **`mobilemessageid`** | ID messaggio in-app | varchar(255) |
| **`mobilemessageonline`** | Messaggio in-app online | varchar(255) |
| **`mobilemessagepushoptin`** | Raccolto dalla variabile di dati di contesto `a.push.optin`. Imposta su “true” quando l’utente acconsente ai messaggi push; altrimenti il valore è “false”. | varchar(255) |
| **`mobilemessagepushpayloadid`** | Raccolto dalla variabile di dati di contesto `a.push.payloadid`. Utilizzato nei messaggi push come identificatore del payload. | varchar(255) |
| **`mobileosenvironment`** | Ritirato - Raccolto dalla variabile di dati di contesto `a.OSEnvironment`. Ambiente del sistema operativo degli stati, ad esempio Android o iOS. | varchar(255) |
| **`mobileosversion`** | Versione del sistema operativo Mobile Services | varchar(255) |
| **`mobileplaceaccuracy`** | Raccolto dalla variabile di dati di contesto `a.loc.acc`. Indica la precisione del GPS in metri al momento della raccolta. | varchar(255) |
| **`mobileplacecategory`** | Raccolto dalla variabile di dati di contesto `a.loc.category`. Descrive la categoria di un luogo specifico. | varchar(255) |
| **`mobileplaceid`** | Raccolto dalla variabile di dati di contesto `a.loc.id`. Identificatore per un dato punto di interesse. | varchar(255) |
| **`mobilepushoptin`** | Consenso push Mobile Services | varchar(255) |
| **`mobilepushpayloadid`** | ID payload push Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigncontent`** | Contenuto del lancio Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignmedium`** | Media del lancio Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignsource`** | Origine del lancio Mobile Services | varchar(255) |
| **`mobilerelaunchcampaignterm`** | Termine del lancio Mobile Services | varchar(255) |
| **`mobilerelaunchcampaigntrackingcode`** | Raccolto dalla variabile di dati di contesto `a.launch.campaign.trackingcode`. Utilizzato nell’acquisizione come codice di tracciamento per la campagna di lancio. | varchar(255) |
| **`mobileresolution`** | Risoluzione del dispositivo mobile. `[Width] x [Height]` in pixel. | varchar(255) |
| **`monthly_visitor`** | Flag che indica che il visitatore è univoco per il mese corrente. | tinyint unsigned |
| **`mvvar1`** - `mvvar3` | Elenca i valori delle variabili. Contiene un elenco delimitato di valori personalizzati a seconda dell’implementazione. Nelle colonne `post_mvvar1` - `post_mvvar3` il delimitatore originale è sostituito da `--**--`. | testo |
| **`mvvar1_instances`** - `mvvar3_instances` | I valori delle variabili di elenco impostati sull’hit corrente. Sostituisce il delimitatore originale con `--**--`. Non ha una colonna `post`. | testo |
| **`namespace`** | Non utilizzato. Parte di una funzione scartata. | varchar(50) |
| **`new_visit`** | Flag che determina se l’hit corrente è una nuova visita. Impostato dai server di Adobe dopo 30 minuti di inattività della visita. | tinyint unsigned |
| **`os`** | ID numerico che rappresenta il sistema operativo del visitatore. In base alla colonna `user_agent`. Il valore chiave per `operating_system.tsv` ricerca standard e `operating_system_type.tsv` [Ricerca dinamica](dynamic-lookups.md). | int senza segno |
| **`p_plugins`** | Non più utilizzato. Elenco dei plug-in disponibili per il browser. Utilizzava la funzione JavaScript `navigator.plugins()`. | testo |
| **`page_event`** | Tipo di hit inviato nella richiesta di immagine (hit standard, collegamento per il download, collegamento personalizzato, collegamento di uscita). Consulta [Ricerca degli eventi di pagina](datafeeds-page-event.md). | tinyint unsigned |
| **`page_event_var1`** | Utilizzato solo nelle richieste di immagine per il tracciamento dei collegamenti. L’URL del collegamento di download, del collegamento di uscita o del collegamento personalizzato in cui è stato fatto clic. | testo |
| **`page_event_var2`** | Utilizzato solo nelle richieste di immagine per il tracciamento dei collegamenti. Nome personalizzato (se specificato) del collegamento. | varchar(100) |
| **`page_event_var3`** | Non più utilizzato. Conteneva dati dai moduli Survey e Media. Compilava i rapporti video legacy nelle versioni precedenti di Adobe Analytics. | testo |
| **`page_type`** | Utilizzato per popolare la dimensione [Pagine non trovate](/help/components/dimensions/pages-not-found.md). Utilizzato esclusivamente per le pagine 404. Questa variabile deve essere vuota o contenere il valore `ErrorPage`. | char(20) |
| **`page_url`** | URL dell’hit. Tieni presente che `post_page_url` viene rimosso per le richieste di immagini per il tracciamento dei collegamenti e utilizza un tipo di dati varchar(255). | testo |
| **`pagename`** | Utilizzato per popolare la dimensione [Pagina](/help/components/dimensions/page.md). Se la variabile [`pagename`](/help/implement/vars/page-vars/pagename.md) è vuota, Analytics utilizza `page_url`. | varchar(100) |
| **`pagename_no_url`** | Simile a `pagename`, tranne per il fatto che non torna a `page_url`. Solo la colonna `post` è disponibile. | varchar(100) |
| **`paid_search`** | Flag impostato se l’hit corrisponde al rilevamento di ricerca a pagamento. | tinyint unsigned |
| **`partner_plugins`** | Non utilizzato. Parte di una funzione scartata. | varchar(255) |
| **`persistent_cookie`** | Utilizzato nella dimensione [Supporto cookie persistenti](/help/components/dimensions/persistent-cookie-support.md). Indica se il visitatore supporta i cookie che non vengono eliminati dopo ogni hit. | char(1) |
| **`plugins`** | Non più utilizzato. Elenco di ID numerici corrispondenti ai plug-in disponibili nel browser. Usa la ricerca `plugins.tsv`. | varchar(180) |
| **`pointofinterest`** | Nome del punto di interesse in Mobile Services | varchar(255) |
| **`pointofinterestdistance`** | Distanza dal centro del punto di interesse in Mobile Services  | varchar(255) |
| Colonne **`post_`** | Contiene il valore utilizzato nei rapporti. Ogni colonna post viene compilata dopo la logica lato server, le regole di elaborazione e le regole VISTA. Nella maggior parte dei casi, Adobe consiglia di utilizzare colonne post. | Vedi la rispettiva colonna non post |
| **`prev_page`** | Non utilizzato. Identificatore proprietario Adobe della pagina precedente. | int senza segno |
| **`product_list`** | Elenco prodotti trasmesso attraverso la variabile [`products`](/help/implement/vars/page-vars/products.md). I prodotti sono delimitati da virgole, mentre le proprietà del singolo prodotto sono delimitate da punti e virgola. | testo |
| **`product_merchandising`** | Non utilizzato. Al suo posto, utilizza `product_list`. | testo |
| **`prop1`** - `prop75` | Variabili di traffico personalizzate da 1 a 75. Utilizzato nelle dimensioni [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`purchaseid`** | Identificatore univoco per un acquisto, impostato mediante la variabile [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Utilizzato dalla colonna `duplicate_purchase`. | char(20) |
| **`quarterly_visitor`** | Contrassegno flag per determinare se l’hit è un nuovo visitatore trimestrale. | tinyint unsigned |
| **`ref_domain`** | In base alla colonna referrer. Dominio di riferimento dell’hit. Utilizzato nella dimensione [Dominio di riferimento](/help/components/dimensions/referring-domain.md). | varchar(100) |
| **`ref_type`** | Un ID numerico che rappresenta il tipo di riferimento per l’hit. Utilizzato nella dimensione [Tipo referrer](/help/components/dimensions/referrer-type.md). <br>1: All’interno del sito<br>2: Altri siti web <br>3: Motori di ricerca <br>4. Disco rigido <br>5: USENET <br>6. Digitato/Contrassegnato con segnalibro (nessun referrer) <br>7: E-mail <br>8: Nessun JavaScript <br>9: Social network | tinyint unsigned |
| **`referrer`** | URL della pagina precedente. Utilizzato nella dimensione [Referrer](/help/components/dimensions/referrer.md). Tieni presente che `referrer` utilizza un tipo di dati varchar(255), `post_referrer` utilizza un tipo di dati varchar(244). | varchar(255) |
| **`resolution`** | ID numerico che rappresenta la risoluzione del monitoraggio. Utilizzato in dimensione [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md). Usa la tabella di ricerca `resolution.tsv`. | smallint senza segno |
| **`s_kwcid`** | ID parola chiave utilizzato nelle integrazioni Adobe Advertising.  | varchar(255) |
| **`s_resolution`** | Valore di risoluzione dello schermo non elaborato. Raccolto utilizzando la funzione JavaScript `screen.width x screen.height`. | char(20) |
| **`search_engine`** | ID numerico che rappresenta il motore di ricerca che ha indirizzato il visitatore al sito. Usa ricerca `search_engines.tsv`. | smallint senza segno |
| **`search_page_num`** | Utilizzato dalla dimensione [Classificazione di tutte le pagine di ricerca](/help/components/dimensions/all-search-page-rank.md). Indica in quale pagina dei risultati di ricerca è stato visualizzato il sito prima che l’utente facesse clic su esso. | smallint senza segno |
| **`secondary_hit`** | Contrassegno flag che tiene traccia degli hit secondari. In genere proviene dall’assegnazione di tag a più suite e dalle regole VISTA che consentono di copiare gli hit. | tinyint unsigned |
| **`service`** | Non utilizzato. Usa `page_event` invece. | char(2) |
| **`socialaccountandappids`** | Non più utilizzato. Account social e ID app | varchar(255) |
| **`socialassettrackingcode`** | Non più utilizzato. Variabile della campagna social | varchar(255) |
| **`socialauthor`** | Non più utilizzato. Variabile Autori social | varchar(255) |
| **`socialcontentprovider`** | Non più utilizzato. Piattaforme/Proprietà social | varchar(255) |
| **`socialinteractiontype`** | Non più utilizzato. Tipo di interazione social | varchar(255) |
| **`sociallanguage`** | Non più utilizzato. Lingua social | varchar(255) |
| **`sociallatlong`** | Non più utilizzato. Latitudine/Longitudine social | varchar(255) |
| **`socialowneddefinitioninsighttype`** | Non più utilizzato. Tipo di informazioni sulla definizione di proprietà social | varchar(255) |
| **`socialowneddefinitioninsightvalue`** | Non più utilizzato. Valore informazioni della definizione di proprietà social | varchar(255) |
| **`socialowneddefinitionmetric`** | Non più utilizzato. Metrica di definizione di proprietà social | varchar(255) |
| **`socialowneddefinitionpropertyvspost`** | Non più utilizzato. Proprietà di proprietà social di definizione vs. post | varchar(255) |
| **`socialownedpostids`** | Non più utilizzato. ID post di proprietà social | varchar(255) |
| **`socialownedpropertyid`** | Non più utilizzato. ID proprietà di proprietà social | varchar(255) |
| **`socialownedpropertyname`** | Non più utilizzato. Nome proprietà di proprietà social | varchar(255) |
| **`socialownedpropertypropertyvsapp`** | Non più utilizzato. Proprietà di proprietà social vs. app | varchar(255) |
| **`sourceid`** | ID sorgente | int senza segno |
| **`state`** | Variabile di stato. | varchar(50) |
| **`stats_server`** | Non è utile. Server interno di Adobe che ha elaborato l’hit. | char(30) |
| **`survey`** | Non più utilizzato. Variabile Adobe Survey. Solo la colonna `post` è disponibile. | testo |
| **`survey_instances`** | Non più utilizzato. Variabile delle istanze Adobe Survey. | testo |
| **`t_time_info`** | Ora locale del visitatore. Il formato è: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Utilizzato nelle integrazioni Adobe Target. Rappresenta tutti i test attualmente qualificati per. Il formato è: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | testo |
| **`tnt_action`** | Utilizzato nelle integrazioni Adobe Target. Rappresenta tutti i test per i quali l’hit è qualificato. | testo |
| **`tnt_instances`** | Utilizzato nelle integrazioni Adobe Target. Variabile delle istanze Target. | testo |
| **`tnt_post_vista`** | Non più utilizzato. Usa `post_tnt` invece. | testo |
| **`transactionid`** | Identificatore univoco in cui è possibile caricare diversi punti dati in un secondo momento tramite origini dati. Raccolte utilizzando la variabile [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | testo |
| **`truncated_hit`** | Contrassegno flag che indica che la richiesta di immagine è stata troncata. Indica che è stato ricevuto un hit parziale. <br>Y: hit troncato; hit parziale ricevuto <br>N: hit non troncato; hit completo ricevuto | char(1) |
| **`ua_color`** | Non più utilizzato. Precedentemente utilizzato come fallback per la profondità del colore. | char(20) |
| **`ua_os`** | Non più utilizzato. Precedentemente utilizzato come fallback per il sistema operativo. | char(80) |
| **`ua_pixels`** | Non più utilizzato. Precedentemente utilizzato come fallback per l’altezza e la larghezza del browser. | char(20) |
| **`user_agent`** | Stringa dell&#39;agente utente inviata nell&#39;intestazione HTTP della richiesta di immagine. | testo |
| **`user_hash`** | Non è utile. Hash sull&#39;ID suite di rapporti. Usa `username` invece. | int senza segno |
| **`user_server`** | Utilizzato nella dimensione [Server](/help/components/dimensions/server.md). | varchar(100) |
| **`userid`** | Non è utile. ID numerico dell&#39;ID suite di rapporti. Usa `username` invece. | int senza segno |
| **`username`** | ID suite di rapporti per l&#39;hit. | char(40) |
| **`va_closer_detail`** | Variabile utilizzata nella dimensione [Dettaglio ultimo contatto](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| **`va_closer_id`** | ID numerico che identifica la dimensione [Canale di ultimo contatto](/help/components/dimensions/last-touch-channel.md). La ricerca per questo ID si trova in Marketing Channel Manager. | tinyint unsigned |
| **`va_finder_detail`** | Variabile utilizzata nella dimensione [Dettaglio del primo contatto](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| **`va_finder_id`** | ID numerico che identifica la dimensione [Canale di primo contatto](/help/components/dimensions/first-touch-channel.md). La ricerca per questo ID si trova in Marketing Channel Manager. | tinyint unsigned |
| **`va_instance_event`** | Contrassegno flag per identificare il canale di marketing [Istanze](/help/components/metrics/instances.md). | tinyint unsigned |
| **`va_new_engagement`** | Contrassegno flag per identificare il canale di marketing [Nuovi impegni](/help/components/metrics/new-engagements.md). | tinyint unsigned |
| **`video`** | Contenuto video | varchar(255) |
| **`videoad`** | Nome annuncio video | varchar(255) |
| **`videoadinpod`** | Posizione annuncio in pod | varchar(255) |
| **`videoadlength`** | Lunghezza annuncio video | numero intero |
| **`videoadload`** | Caricamenti di annunci video | varchar(255) |
| **`videoadname`** | Nome annuncio video | varchar(255) |
| **`videoadplayername`** | Nome del lettore di annunci video | varchar(255) |
| **`videoadpod`** | Pod annuncio video | varchar(255) |
| **`videoadvertiser`** | Inserzionista video | varchar(255) |
| **`videoaudioalbum`** | Album audio video | varchar(255) |
| **`videoaudioartist`** | Artista audio video | varchar(255) |
| **`videoaudioauthor`** | Autore audio video | varchar(255) |
| **`videoaudiolabel`** | Etichetta audio video | varchar(255) |
| **`videoaudiopublisher`** | Pubblicazione audio video | varchar(255) |
| **`videoaudiostation`** | Stazione audio video | varchar(255) |
| **`videocampaign`** | Campagna video | varchar(255) |
| **`videochannel`** | Canale video | varchar(255) |
| **`videochapter`** | Nome del capitolo video | varchar(255) |
| **`videocontenttype`** | Tipo di contenuto video. Imposta automaticamente su “Video” per tutte le visualizzazioni video | varchar(255) |
| **`videodaypart`** | Parte giorno video | varchar(255) |
| **`videoepisode`** | Episodio video | varchar(255) |
| **`videofeedtype`** | Tipo di feed video | varchar(255) |
| **`videogenre`** | Genere video | testo |
| **`videolength`** | Lunghezza video | numero intero |
| **`videomvpd`** | MVPD video | varchar(255) |
| **`videoname`** | Nome del video | varchar(255) |
| **`videonetwork`** | Rete video | varchar(255) |
| **`videopath`** | Percorso video | varchar(100) |
| **`videoplayername`** | Nome del lettore video | varchar(255) |
| **`videotime`** | Tempo del video | numero intero |
| **`videoqoebitrateaverageevar`** | Bit rate medio della qualità video | varchar(255) |
| **`videoqoebitratechangecountevar`** | Conteggio dei cambiamenti nella qualità video | varchar(255) |
| **`videoqoebuffercountevar`** | Conteggio buffer qualità video | varchar(255) |
| **`videoqoebuffertimeevar`** | Tempo buffer qualità video | varchar(255) |
| **`videoqoedroppedframecountevar`** | Numero di fotogrammi non elaborati della qualità video | varchar(255) |
| **`videoqoeerrorcountevar`** | Conteggio errori nella qualità video | varchar(255) |
| **`videoqoeextneralerrors`** | Errori esterni nella qualità video | testo |
| **`videoqoeplayersdkerrors`** | Errori SDK nella qualità video | testo |
| **`videoqoetimetostartevar`** | Tempo di avvio della qualità video | varchar(255) |
| **`videoseason`** | Stagione video | varchar(255) |
| **`videosegment`** | Segmento video | varchar(255) |
| **`videoshow`** | Presentazione video | varchar(255) |
| **`videoshowtype`** | Tipo di presentazione video | varchar(255) |
| **`videostreamtype`** | Tipo di flusso video | varchar(255) |
| **`visid_high`** | Utilizzato con `visid_low` per identificare in modo univoco un visitatore. | Bigint senza segno |
| **`visid_low`** | Utilizzato con `visid_high` per identificare in modo univoco un visitatore. | Bigint senza segno |
| **`visid_new`** | Contrassegno flag per identificare se l&#39;hit contiene un ID visitatore appena generato. | char(1) |
| **`visid_timestamp`** | Se l’ID visitatore è stato generato di recente, fornisce la marca temporale (in tempo UNIX®) di quando è stato generato l’ID visitatore. | Intero |
| **`visid_type`** | Non per uso esterno; utilizzato internamente da Adobe per l’elaborazione delle ottimizzazioni. ID numerico che rappresenta il metodo utilizzato per identificare il visitatore.<br>`0`: ID visitatore personalizzato o sconosciuto/non applicabile<br>`1`: fallback dell’IP e dell’agente utente <br>`2`: intestazione dell’abbonato mobile HTTP <br>`3`: valore cookie legacy (`s_vi`) <br>`4` valore cookie di fallback (`s_fid`) <br>`5`: servizio identità | tinyint unsigned |
| **`visit_keywords`** | Variabile utilizzata nella dimensione [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md). Questa colonna utilizza un limite di caratteri non standard di varchar(244) per adattarsi alla logica back-end utilizzata da Adobe. | varchar(244) |
| **`visit_num`** | Variabile utilizzata nella dimensione [Numero di visite](/help/components/dimensions/visit-number.md). Inizia a 1 e viene incrementato ogni volta che inizia una nuova visita per visitatore. | int senza segno |
| **`visit_page_num`** | Variabile utilizzata nella dimensione [Profondità di hit](/help/components/dimensions/hit-depth.md). Aumenta di 1 per ogni hit generato dall’utente. Ripristina ogni visita. | int senza segno |
| **`visit_ref_domain`** | In base alla colonna `visit_referrer`. Il primo dominio di riferimento della visita. | varchar(100) |
| **`visit_ref_type`** | ID numerico che rappresenta il tipo di referrer del primo referrer della visita. Utilizza la tabella di ricerca `referrer_type.tsv`. | tinyint unsigned |
| **`visit_referrer`** | Il primo referrer della visita. | varchar(255) |
| **`visit_search_engine`** | ID numerico del primo motore di ricerca della visita. Usa la ricerca `search_engines.tsv`. | smallint senza segno |
| **`visit_start_page_url`** | Il primo URL della visita. | varchar(255) |
| **`visit_start_pagename`** | Il valore Nome pagina nel primo hit della visita. | varchar(100) |
| **`visit_start_time_gmt`** | Marca temporale (in tempo UNIX®) del primo hit della visita. | Intero |
| **`weekly_visitor`** | Contrassegno flag per determinare se l’hit è un nuovo visitatore settimanale. | tinyint unsigned |
| **`yearly_visitor`** | Contrassegno flag per determinare se l’hit è un nuovo visitatore annuale. | tinyint unsigned |
| **`zip`** | Consente di popolare la dimensione [Codice postale](/help/components/dimensions/zip-code.md). Consulta anche `geo_zip`. | varchar(50) |

## Colonne vuote

Il seguente elenco di colonne non è utilizzato e non contiene dati:

* `adclassificationcreative`
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
