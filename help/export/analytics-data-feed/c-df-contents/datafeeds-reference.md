---
description: Dati di tabella che descrivono le colonne nel feed di dati.
keywords: Feed di dati; colonne
subtopic: data feeds
title: Riferimento colonna dati
feature: Data Feeds
exl-id: e1492147-6e7f-4921-b509-898e7efda596
source-git-commit: 9138a6ae20b5c74a5eaf3b11fb7fcc406d9605e7
workflow-type: tm+mt
source-wordcount: '3570'
ht-degree: 67%

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
| **`aemassetid`** | Variabile multivalore corrispondente agli ID risorsa (GUID) di un set di Adobe Experience Manager Assets. Incrementa gli eventi di impression. | testo |
| **`aemassetsource`** | Identifica l’origine dell’evento risorsa. Utilizzato in Adobe Experience Manager. | varchar(255) |
| **`aemclickedassetid`** | ID risorsa di una risorsa di Adobe Experience Manager. Incrementa gli eventi di clic. | varchar(255) |
| **`browser`** | ID numerico che rappresenta il browser. Fa riferimento alla tabella di ricerca `browser.tsv`. | int senza segno |
| **`browser_height`** | La dimensione [Altezza browser](/help/components/dimensions/browser-height.md). | smallint senza segno |
| **`browser_width`** | Larghezza [Browser](/help/components/dimensions/browser-width.md) | smallint senza segno |
| **`c_color`** | Profondità in bit della palette di colori. Utilizzato come parte del calcolo della dimensione [Profondità colore](/help/components/dimensions/color-depth.md). AppMeasurement utilizza la funzione `screen.colorDepth()` di JavaScript. | char(20) |
| **`campaign`** | La [dimensione Tracking Code](/help/components/dimensions/tracking-code.md) . | varchar(255) |
| **`carrier`** | Variabile di integrazione di Adobe Advertising. Specifica il gestore di telefonia mobile. Valore chiave per [Ricerca dinamica](dynamic-lookups.md) `carrier.tsv`. | varchar(100) |
| **`ch_hdr`** | Hint client raccolti tramite l’intestazione della richiesta HTTP. | testo |
| **`ch_js`** | Hint client raccolti tramite l’API JavaScript per gli hint client dall’agente utente | testo |
| **`channel`** | La dimensione [Sezioni del sito](/help/components/dimensions/site-section.md). | varchar(100) |
| **`clickmaplink`** | Collegamento ad Activity Map | varchar(255) |
| **`clickmaplinkbyregion`** | Collegamento ad Activity Map per area geografica | varchar(255) |
| **`clickmappage`** | Pagina di Activity Map | varchar(255) |
| **`clickmapregion`** | Area geografica di Activity Map | varchar(255) |
| **`code_ver`** | Versione API o SDK client utilizzata per compilare e inviare la richiesta di immagine. | char(16) |
| **`color`** | ID di profondità colore in base al valore della colonna `c_color`. Fa riferimento alla tabella di ricerca `color_depth.tsv`. | smallint senza segno |
| **`connection_type`** | ID numerico che rappresenta il tipo di connessione. La dimensione [Tipo di connessione](/help/components/dimensions/connection-type.md). Fa riferimento alla tabella di ricerca `connection_type.tsv`. | tinyint unsigned |
| **`cookies`** | La dimensione [Supporto cookie](/help/components/dimensions/cookie-support.md).<br>Y: abilitato<br>N: disabilitato<br>U: sconosciuto | char(1) |
| **`country`** | Un ID numerico che rappresenta il paese del visitatore. Fa riferimento alla tabella di ricerca `country.tsv`. | smallint senza segno |
| **`ct_connect_type`** | Correlato alla colonna `connection_type`. I valori più comuni sono LAN/Wi-Fi, Gestore di telefonia mobile e Modem. | char(20) |
| **`curr_factor`** | Determina la posizione dei decimali della valuta e viene utilizzato per la conversione della valuta. Ad esempio, USD utilizza due posizioni decimali, quindi il valore di questa colonna sarebbe `2`. | Tinyint |
| **`curr_rate`** | Il tasso di cambio al momento della transazione. Adobe si appoggia a XE per determinare il tasso di cambio del giorno corrente. | decimal(24,12) |
| **`currency`** | Codice valuta utilizzato durante la transazione. Impostato con [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). | char(8) |
| **`cust_hit_time_gmt`** | Solo suite di rapporti abilitate per la marca temporale. La marca temporale inviata con l’hit, in base al tempo UNIX®. | Intero |
| **`cust_visid`** | ID visitatore personalizzato, se impostato con [`visitorID`](/help/implement/vars/config-vars/visitorid.md). | varchar(255) |
| **`daily_visitor`** | Flag che determina se l’hit è un nuovo visitatore giornaliero. | tinyint unsigned |
| **`dataprivacyconsentoptin`** | La dimensione [Gestione del consenso esplicito](/help/components/dimensions/cm-opt-in.md). È possibile che siano presenti più valori per hit, separati da una barra verticale (`\|`). I valori validi includono `DMP` e `SELL`. | varchar(100) |
| **`dataprivacyconsentoptout`** | La dimensione [Rinuncia alla gestione del consenso](/help/components/dimensions/cm-opt-out.md). È possibile che siano presenti più valori per hit, separati da una barra verticale (`\|`). I valori validi includono `SSF`, `DMP` e `SELL`. | varchar(100) |
| **`dataprivacydmaconsent`** | Valore che identifica se il consenso è stato acquisito per l’invio di dati da Adobe Analytics tramite Adobe Advertising a provider pubblicitari di terze parti (come Google). Per ulteriori informazioni, consulta [Consenso agli annunci](/help/components/dimensions/ad-consent.md). | varchar(100) |
| **`date_time`** | L’ora dell’hit in formato leggibile, in base al fuso orario della suite di rapporti. | Datetime |
| **`domain`** | La [dimensione Dominio](/help/components/dimensions/domain.md) . In base al punto di accesso Internet del visitatore. | varchar(100) |
| **`duplicate_events`** | Elenca ogni evento conteggiato come duplicato. | varchar(255) |
| **`duplicate_purchase`** | Flag che determina se l’evento di acquisto per questo hit viene ignorato perché è un duplicato. | tinyint unsigned |
| **`duplicated_from`** | Utilizzato solo nelle suite di rapporti contenenti regole VISTA della copia hit. Indica la suite di rapporti da cui è stato copiato l’hit. | varchar(40) |
| **`ef_id`** | Valore `ef_id` utilizzato nelle integrazioni di Adobe Advertising.  | varchar(255) |
| **`evar1 - evar250`** | Variabili personalizzate 1-250. Utilizzato nelle dimensioni [eVar](/help/components/dimensions/evar.md). Ogni organizzazione utilizza le eVar in modo diverso. Il luogo migliore per ulteriori informazioni su come la tua organizzazione compila le rispettive eVar sarebbe un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md) specifico per la tua organizzazione. | varchar(255) |
| **`event_list`** | Elenco separato da virgole degli ID numerici che rappresentano gli eventi attivati sull&#39;hit. Include sia gli eventi predefiniti che gli [eventi personalizzati 1-1000](/help/components/metrics/custom-events.md). Usa la ricerca `event.tsv`. | testo |
| **`exclude_hit`** | Un contrassegno che determina se l&#39;hit è escluso dal reporting. La colonna `visit_num` non viene incrementata per gli hit esclusi.<br>1: non utilizzato. Parte di una funzione scartata.<br>2: non utilizzato. Parte di una funzione scartata.<br>3: non più utilizzato. Esclusione dell’agente utente<br>4: esclusione basata sull’indirizzo IP<br>5: informazioni hit vitali mancanti, ad esempio `page_url`, `pagename`, `page_event` oppure `event_list`<br>6: JavaScript non ha elaborato correttamente gli hit<br>7: esclusione specifica dell’account, ad esempio in una regola VISTA<br>8: non utilizzato. Esclusione alternativa specifica per l’account.<br>9: non utilizzato. Parte di una funzione scartata.<br>10: codice valuta non valido<br>11: hit mancante di una marca temporale in una suite di rapporti solo di marca temporale o un hit contenente una marca temporale in una suite di rapporti non di marca temporale<br>12: non utilizzato. Parte di una funzione scartata.<br>13: non utilizzato. Parte di una funzione scartata.<br>14: hit di destinazione che non corrisponde a un hit di Analytics<br>15: non attualmente utilizzato.<br>16: hit di Advertising Cloud che non corrisponde a un hit di Analytics | tinyint unsigned |
| **`first_hit_page_url`** | Il primo URL del visitatore. | varchar(255) |
| **`first_hit_pagename`** | La dimensione [Pagina di ingresso originale](/help/components/dimensions/entry-dimensions.md). Il nome della pagina di ingresso originale del visitatore. | varchar(100) |
| **`first_hit_ref_domain`** | La dimensione [Dominio di riferimento originale](/help/components/dimensions/original-referring-domain.md). In base a `first_hit_referrer`. Il primo dominio di provenienza del visitatore. | varchar(100) |
| **`first_hit_ref_type`** | Un ID numerico che rappresenta il tipo di referrer del primo referrer del visitatore. Fa riferimento alla tabella di ricerca `referrer_type.tsv`. | tinyint unsigned |
| **`first_hit_referrer`** | Il primo URL di provenienza del visitatore. | varchar(255) |
| **`first_hit_time_gmt`** | Marca temporale del primo hit del visitatore in tempo UNIX®. | Intero |
| **`geo_city`** | Il nome della città da cui proviene l’hit, in base all’IP. Utilizzato nella dimensione [Città](/help/components/dimensions/cities.md). | char(32) |
| **`geo_country`** | L’abbreviazione del paese da cui proviene l’hit, basata su IP. Utilizzato nella dimensione [Paesi](/help/components/dimensions/countries.md). | char(4) |
| **`geo_dma`** | ID numerico dell’area demografica di origine dell’hit, basato su IP. Utilizzato nella dimensione [DMA USA](/help/components/dimensions/us-dma.md). | int senza segno |
| **`geo_region`** | Il nome dello stato o dell’area geografica da cui proviene l’hit, in base all’IP. Utilizzato nella dimensione [Aree geografiche](/help/components/dimensions/regions.md). | char(32) |
| **`geo_zip`** | Il codice postale di origine dell’hit, basato su IP. Consente di popolare la dimensione [Codice postale](/help/components/dimensions/zip-code.md). Consulta anche `zip`. | varchar(16) |
| **`hit_source`** | La fonte da cui proviene l’hit. Le origini di hit 1, 2 e 6 vengono fatturate. <br>1: richiesta immagine standard senza marca temporale <br>2: richiesta immagine standard con marca temporale <br>3: caricamento origine dati live con marca temporale <br>4: non utilizzato <br>5: caricamento origine dati generica <br>6: caricamento origine dati a elaborazione completa <br>7: caricamento origine dati TransactionID <br>8: non più utilizzato; versioni precedenti di origini dati di Adobe Advertising Cloud <br>9: non più utilizzato; metriche di riepilogo di Adobe Social <br>10: inoltro lato server Audience Manager utilizzato | tinyint unsigned |
| **`hit_time_gmt`** | La marca temporale dei server Adobe di raccolta dati degli hit ha ricevuto l’hit, in base all’ora UNIX®. | Intero |
| **`hitid_high`** | Utilizzato con `hitid_low` per identificare un hit. | Bigint senza segno |
| **`hitid_low`** | Utilizzato con `hitid_high` per identificare un hit. | Bigint senza segno |
| **`hourly_visitor`** | Flag che determina se l’hit è un nuovo visitatore orario. | tinyint unsigned |
| **`ip`** | L’indirizzo IPv4, in base all’intestazione HTTP della richiesta di immagine. Reciprocamente esclusivo per `ipv6`; se questa colonna contiene un indirizzo IP non offuscato, `ipv6` è vuoto. | char(20) |
| **`ipv6`** | Indirizzo IPv6 compresso, se disponibile. Reciprocamente esclusivo per `ip`; se questa colonna contiene un indirizzo IP non offuscato, `ip` è vuoto. | varchar(40) |
| **`j_jscript`** | Versione di JavaScript supportata dal browser. | char(5) |
| **`java_enabled`** | [[!UICONTROL Java enabled]](/help/components/dimensions/java-enabled.md). <br>Y: abilitato <br>N: disabilitato <br>U: sconosciuto | char(1) |
| **`javascript`** | ID di ricerca di JavaScript versione, basato su `j_jscript`. Fa riferimento alla tabella di ricerca `javascript_version`. | tinyint unsigned |
| **`language`** | ID numerico che rappresenta la lingua del visitatore. Fa riferimento alla tabella di ricerca `languages.tsv`. | smallint senza segno |
| **`last_hit_time_gmt`** | Marca temporale (in ora UNIX®) dell’hit precedente. Utilizzato per calcolare la dimensione [[!UICONTROL Days since last visit]](/help/components/dimensions/days-since-last-visit.md). | Intero |
| **`last_purchase_num`** | La dimensione [Fedeltà del cliente](/help/components/dimensions/customer-loyalty.md). Il numero di acquisti precedenti effettuati dal visitatore. <br>0: nessun acquisto precedente (non è un cliente) <br>1: 1 acquisto precedente (nuovo cliente) <br>2: 2 acquisti precedenti (cliente di ritorno) <br>3: 3 o più acquisti precedenti (cliente abituale) | int senza segno |
| **`last_purchase_time_gmt`** | Utilizzato nella dimensione [[!UICONTROL Days since last purchase]](/help/components/dimensions/days-since-last-purchase.md). Marca temporale (in ora UNIX®) dell’ultimo acquisto effettuato. Per i nuovi acquisti e i visitatori che non hanno effettuato un acquisto in precedenza, questo valore è `0`. | Intero |
| **`latlon1`** | Posizione (fino a 10 chilometri) | varchar(255) |
| **`latlon23`** | Posizione (fino a 100 m) | varchar(255) |
| **`latlon45`** | Posizione (fino a 1 m) | varchar(255) |
| **`mc_audiences`** | Elenco degli ID del segmento di Audience Manager a cui appartiene il visitatore. Nella colonna `post_mc_audiences` il delimitatore diventa `--**--`. | testo |
| **`mcvisid`** | ID visitatore di Experience Cloud. Numero a 128 bit costituito da due numeri concatenati a 64 bit aggiunti a 19 cifre. | varchar(255) |
| **`mobile_id`** | Se l’utente utilizza un dispositivo mobile, l’ID numerico del dispositivo. Il valore chiave per `mobile_attributes.tsv` [Ricerca dinamica](dynamic-lookups.md). | Intero |
| **`mobileaction`** | Azione da dispositivo mobile. Raccolta automatica quando `trackAction` viene chiamato nelle implementazioni mobili. Consente il percorso automatico delle azioni nell’app. | varchar(100) |
| **`mobileappid`** | ID dell’app mobile. Memorizza il nome e la versione dell&#39;applicazione nel seguente formato: `[AppName] [BundleVersion]` | varchar(255) |
| **`mobileappperformanceappid`** | Utilizzato nel connettore dati Apteligent. L’ID app utilizzato in Apteligent. | varchar(255) |
| **`mobileappperformancecrashid`** | Utilizzato nel connettore dati Apteligent. ID di arresto anomalo utilizzato in Apteligent. | varchar(255) |
| **`mobileappstoreobjectid`** | Utilizzato nel connettore dati [!DNL Appfigures]. ID dell’oggetto nell’app store. | varchar(255) |
| **`mobilebeaconmajor`** | Beacon principale di Mobile Services | varchar(100) |
| **`mobilebeaconminor`** | Beacon secondario di Mobile Services | varchar(100) |
| **`mobilebeaconproximity`** | Prossimità beacon di Mobile Services | varchar(255) |
| **`mobilebeaconuuid`** | UUID del beacon di Mobile Services | varchar(100) |
| **`mobilecampaigncontent`** | Nome o ID del contenuto che ha visualizzato il collegamento. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobilecampaignmedium`** | Canale di marketing, ad esempio banner o e-mail. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobilecampaignname`** | Il nome della campagna, memorizzato anche nella variabile della campagna. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobilecampaignsource`** | Referente originale, ad esempio newsletter o Social media network. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobilecampaignterm`** | Parole chiave a pagamento o altri termini di cui tenere traccia con questa acquisizione. Viene compilata dalla funzione Acquisizione da app mobile. | varchar(255) |
| **`mobiledayofweek`** | Numero del giorno della settimana in cui è stata avviata l’app. | varchar(255) |
| **`mobiledayssincefirstuse`** | Numero di giorni dalla prima esecuzione dell’app. | varchar(255) |
| **`mobiledayssincelastuse`** | Numero di giorni dall’ultima esecuzione dell’app. | varchar(255) |
| **`mobiledeeplinkid`** | Raccolto dalla variabile di dati di contesto `a.deeplink.id`. Utilizzato nei rapporti di acquisizione come identificatore per il collegamento di acquisizione mobile. | varchar(255) |
| **`mobiledevice`** | Nome del dispositivo mobile. In iOS, viene memorizzato come stringa di 2 cifre separate da virgola. Il primo numero rappresenta la generazione del dispositivo e il secondo rappresenta la famiglia di dispositivi. | varchar(255) |
| **`mobilehourofday`** | Definisce l’ora del giorno in cui l’app è stata avviata. Segue il formato numerico di 24 ore. | varchar(255) |
| **`mobileinstalldate`** | Data di installazione dell’app mobile. Fornisce la data della prima apertura dell’app mobile da parte di un utente. | varchar(255) |
| **`mobilelaunchnumber`** | Aumenta di uno ogni volta che l’app mobile viene avviata. | varchar(255) |
| **`mobilemessagebuttonname`** | Raccolto dalla variabile di dati di contesto `a.message.button.id`. Utilizzato per la messaggistica in-app per identificare il pulsante che ha chiuso il messaggio. | varchar(100) |
| **`mobilemessageid`** | ID messaggio in-app | varchar(255) |
| **`mobilemessageonline`** | Messaggio in-app online | varchar(255) |
| **`mobilemessagepushoptin`** | Raccolto dalla variabile di dati di contesto `a.push.optin`. Imposta su “true” quando l’utente acconsente ai messaggi push; altrimenti il valore è “false”. | varchar(255) |
| **`mobilemessagepushpayloadid`** | Raccolto dalla variabile di dati di contesto `a.push.payloadid`. Utilizzato nei messaggi push come identificatore del payload. | varchar(255) |
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
| **`monthly_visitor`** | Flag che determina se il visitatore è univoco per il mese corrente. | tinyint unsigned |
| **`mvvar1`** - `mvvar3` | [Elenca i valori della variabile](/help/implement/vars/page-vars/list.md). Contiene un elenco delimitato di valori personalizzati a seconda dell’implementazione. Nelle colonne `post_mvvar1` - `post_mvvar3` il delimitatore originale è sostituito da `--**--`. | testo |
| **`mvvar1_instances`** - `mvvar3_instances` | I valori delle variabili di elenco impostati sull’hit corrente. Sostituisce il delimitatore originale con `--**--`. Le colonne `post` in genere non contengono dati. | testo |
| **`new_visit`** | Flag che determina se l’hit corrente è una nuova visita. Impostato dall’Adobe dopo 30 minuti di inattività della visita. | tinyint unsigned |
| **`os`** | Un ID numerico che rappresenta il sistema operativo del visitatore. In base alla colonna `user_agent`. Il valore chiave per `operating_system.tsv` ricerca standard e `operating_system_type.tsv` [Ricerca dinamica](dynamic-lookups.md). | int senza segno |
| **`page_event`** | Tipo di hit inviato nella richiesta di immagine (hit standard, collegamento per il download, collegamento personalizzato, collegamento di uscita). Consulta [Ricerca degli eventi di pagina](datafeeds-page-event.md). | tinyint unsigned |
| **`page_event_var1`** | Utilizzato solo nelle richieste di immagine per il tracciamento dei collegamenti. L’URL del collegamento di download, del collegamento di uscita o del collegamento personalizzato in cui è stato fatto clic. | testo |
| **`page_event_var2`** | Utilizzato solo nelle richieste di immagine per il tracciamento dei collegamenti. Nome personalizzato (se specificato) del collegamento. Imposta il [collegamento personalizzato](/help/components/dimensions/custom-link.md), [collegamento di download](/help/components/dimensions/download-link.md) o [collegamento di uscita](/help/components/dimensions/exit-link.md) a seconda del valore in `page_event`. | varchar(100) |
| **`page_type`** | La [dimensione Pagine non trovate](/help/components/dimensions/pages-not-found.md) , generalmente utilizzata per 404 pagine. | char(20) |
| **`page_url`** | URL dell’hit. Nota che `post_page_url` viene rimosso per collegare le richieste di tracking delle immagini ([`tl()`](/help/implement/vars/functions/tl-method.md)) e utilizza un tipo di dati di varchar(255). | testo |
| **`pagename`** | La dimensione [Pagina](/help/components/dimensions/page.md). Se la variabile [`pagename`](/help/implement/vars/page-vars/pagename.md) è vuota, Analytics utilizza `page_url`. | varchar(100) |
| **`pagename_no_url`** | Simile a `pagename`, tranne per il fatto che non torna a `page_url`. Solo la colonna `post` è disponibile. | varchar(100) |
| **`paid_search`** | Flag che determina se l’hit corrisponde al rilevamento di ricerche a pagamento. | tinyint unsigned |
| **`persistent_cookie`** | Utilizzato nella dimensione [Supporto cookie persistenti](/help/components/dimensions/persistent-cookie-support.md). Indica se il visitatore supporta i cookie che non vengono eliminati dopo ogni hit. | char(1) |
| **`pointofinterest`** | Nome del punto di interesse in Mobile Services | varchar(255) |
| **`pointofinterestdistance`** | Distanza dal centro del punto di interesse in Mobile Services  | varchar(255) |
| Colonne **`post_`** | Contiene il valore utilizzato nei rapporti. Ogni colonna post viene compilata dopo la logica lato server, le regole di elaborazione e le regole VISTA. Nella maggior parte dei casi, Adobe consiglia di utilizzare colonne post. | Vedi la rispettiva colonna non post |
| **`product_list`** | La variabile di pagina [`products`](/help/implement/vars/page-vars/products.md). Consente di popolare diverse dimensioni e metriche, tra cui [Categoria](/help/components/dimensions/category.md), [Prodotto](/help/components/dimensions/product.md), [Unità](/help/components/metrics/units.md) e [Ricavi](/help/components/metrics/revenue.md). | testo |
| **`prop1`** - `prop75` | Variabili di traffico personalizzate da 1 a 75. Utilizzato nelle dimensioni [Prop](/help/components/dimensions/prop.md). | varchar(100) |
| **`purchaseid`** | Identificatore univoco per un acquisto, impostato mediante la variabile [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). Utilizzato dalla colonna `duplicate_purchase`. | char(20) |
| **`quarterly_visitor`** | Flag che determina se l’hit è un nuovo visitatore trimestrale. | tinyint unsigned |
| **`ref_domain`** | La dimensione [Dominio di riferimento](/help/components/dimensions/referring-domain.md). In base alla colonna `referrer`. | varchar(100) |
| **`ref_type`** | ID numerico che rappresenta il tipo di riferimento per l’hit. Utilizzato nella dimensione [Tipo referrer](/help/components/dimensions/referrer-type.md). <br>1: All’interno del sito<br>2: Altri siti web <br>3: Motori di ricerca <br>4. Disco rigido <br>5: USENET <br>6. Digitato/Contrassegnato con segnalibro (nessun referrer) <br>7: E-mail <br>8: Nessun JavaScript <br>9: Social network | tinyint unsigned |
| **`referrer`** | La dimensione [Referrer](/help/components/dimensions/referrer.md). Tieni presente che `referrer` utilizza un tipo di dati varchar(255), `post_referrer` utilizza un tipo di dati varchar(244). | varchar(255) |
| **`resolution`** | ID numerico che rappresenta la risoluzione del monitoraggio. Utilizzato in dimensione [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md). Usa la tabella di ricerca `resolution.tsv`. | smallint senza segno |
| **`s_kwcid`** | ID parola chiave utilizzato nelle integrazioni Adobe Advertising.  | varchar(255) |
| **`s_resolution`** | Valore di risoluzione dello schermo non elaborato. Raccolto utilizzando la funzione JavaScript `screen.width x screen.height`. | char(20) |
| **`search_engine`** | Un ID numerico che rappresenta il motore di ricerca che ha indirizzato il visitatore al sito. Utilizzato nelle dimensioni [Motore di ricerca](/help/components/dimensions/search-engine.md). Fa riferimento alla tabella di ricerca `search_engines.tsv`. | smallint senza segno |
| **`search_page_num`** | Utilizzato dalla dimensione [Classificazione di tutte le pagine di ricerca](/help/components/dimensions/all-search-page-rank.md). Indica in quale pagina dei risultati di ricerca è stato visualizzato il sito prima che l’utente facesse clic su esso. | smallint senza segno |
| **`secondary_hit`** | Flag che determina se l’hit è un hit secondario. Questo flag in genere ha origine dall’assegnazione di tag a più suite e dalle regole VISTA che consentono di copiare gli hit. | tinyint unsigned |
| **`sourceid`** | ID sorgente | int senza segno |
| **`state`** | Variabile di stato. | varchar(50) |
| **`stats_server`** | Non è utile. Server interno di Adobe che ha elaborato l’hit. | char(30) |
| **`t_time_info`** | Ora locale del visitatore. Il formato è: `M/D/YYYY HH:MM:SS Month (0-11, 0=January) Timezone offset (in minutes)` | varchar(100) |
| **`tnt`** | Utilizzato nelle integrazioni Adobe Target. Rappresenta tutti i test attualmente qualificati per. Il formato è: `TargetCampaignID:TargetRecipeID:TargetType\|Event/Action`. | testo |
| **`tnt_action`** | Utilizzato nelle integrazioni Adobe Target. Rappresenta tutti i test per i quali l’hit è qualificato. | testo |
| **`tnt_instances`** | Utilizzato nelle integrazioni Adobe Target. Variabile delle istanze Target. | testo |
| **`transactionid`** | Identificatore univoco in cui è possibile caricare diversi punti dati in un secondo momento tramite origini dati. Raccolte utilizzando la variabile [`transactionID`](/help/implement/vars/page-vars/transactionid.md). | testo |
| **`truncated_hit`** | Flag che indica che la richiesta di immagine è stata troncata. Indica che è stato ricevuto un hit parziale. <br>Y: hit troncato; hit parziale ricevuto <br>N: hit non troncato; hit completo ricevuto | char(1) |
| **`user_agent`** | Stringa dell’agente utente inviata nell’intestazione HTTP della richiesta di immagine. | testo |
| **`user_hash`** | Non è utile. Hash sull&#39;ID suite di rapporti. Usa `username` invece. | int senza segno |
| **`user_server`** | Utilizzato nella dimensione [Server](/help/components/dimensions/server.md). | varchar(100) |
| **`userid`** | Non è utile. ID numerico dell&#39;ID suite di rapporti. Usa `username` invece. | int senza segno |
| **`username`** | ID suite di rapporti per l&#39;hit. | char(40) |
| **`va_closer_detail`** | La dimensione [Dettaglio ultimo contatto](/help/components/dimensions/last-touch-detail.md). | varchar(255) |
| **`va_closer_id`** | ID numerico che identifica la dimensione [Canale di ultimo contatto](/help/components/dimensions/last-touch-channel.md). La ricerca per questo ID si trova in Marketing Channel Manager. | tinyint unsigned |
| **`va_finder_detail`** | La dimensione [Dettaglio primo contatto](/help/components/dimensions/first-touch-detail.md). | varchar(255) |
| **`va_finder_id`** | ID numerico che identifica la dimensione [Canale di primo contatto](/help/components/dimensions/first-touch-channel.md). La ricerca per questo ID si trova in Marketing Channel Manager. | tinyint unsigned |
| **`va_instance_event`** | Un flag che identifica il canale di marketing [Istanze](/help/components/metrics/instances.md). | tinyint unsigned |
| **`va_new_engagement`** | Un flag che identifica il canale di marketing [Nuovi impegni](/help/components/metrics/new-engagements.md). | tinyint unsigned |
| **`video`** | La dimensione [Contenuto](/help/components/dimensions/sm-core.md) elemento multimediale in streaming. | varchar(255) |
| **`videoad`** | La dimensione [Ad](/help/components/dimensions/sm-ads.md) dei file multimediali in streaming. | varchar(255) |
| **`videoadinpod`** | La dimensione [Annuncio in posizione pod](/help/components/dimensions/sm-ads.md) elemento multimediale in streaming. | varchar(255) |
| **`videoadlength`** | La dimensione [Lunghezza annuncio (variabile)](/help/components/dimensions/sm-ads.md) dei file multimediali in streaming. | numero intero |
| **`videoadload`** | La dimensione [Ad carica](/help/components/dimensions/sm-ads.md) Streaming Media. | varchar(255) |
| **`videoadname`** | La dimensione [Nome annuncio (variabile)](/help/components/dimensions/sm-ads.md) elemento multimediale in streaming. | varchar(255) |
| **`videoadplayername`** | La dimensione [Nome lettore annuncio](/help/components/dimensions/sm-ads.md) elemento multimediale in streaming. | varchar(255) |
| **`videoadpod`** | La dimensione [Annuncio pod](/help/components/dimensions/sm-ads.md) di Streaming Media. | varchar(255) |
| **`videoadvertiser`** | La dimensione Streaming Media dell&#39;inserzionista[](/help/components/dimensions/sm-ads.md). | varchar(255) |
| **`videoaudioalbum`** | La [dimensione Album](/help/components/dimensions/sm-audio-metadata.md) Streaming Media. | varchar(255) |
| **`videoaudioartist`** | La dimensione [Artista](/help/components/dimensions/sm-audio-metadata.md) elemento multimediale in streaming. | varchar(255) |
| **`videoaudioauthor`** | La dimensione [Autore](/help/components/dimensions/sm-audio-metadata.md) elemento multimediale in streaming. | varchar(255) |
| **`videoaudiolabel`** | La dimensione [Etichetta](/help/components/dimensions/sm-audio-metadata.md) dei file multimediali in streaming. | varchar(255) |
| **`videoaudiopublisher`** | La dimensione [Editore](/help/components/dimensions/sm-audio-metadata.md) dei file multimediali in streaming. | varchar(255) |
| **`videoaudiostation`** | La dimensione [Stazione](/help/components/dimensions/sm-audio-metadata.md) di Streaming Media. | varchar(255) |
| **`videocampaign`** | La dimensione [ID campagna](/help/components/dimensions/sm-ads.md) elemento multimediale in streaming. | varchar(255) |
| **`videochannel`** | La dimensione [Canale contenuto](/help/components/dimensions/sm-core.md) File multimediali in streaming. | varchar(255) |
| **`videochapter`** | La dimensione [Capitolo](/help/components/dimensions/sm-chapters.md) elemento multimediale in streaming. | varchar(255) |
| **`videocontenttype`** | Tipo [di contenuto](/help/components/dimensions/sm-core.md) Dimensione Streaming multimediale. | varchar(255) |
| **`videodaypart`** | La [parte](/help/components/dimensions/sm-video-metadata.md) Day Streaming Media dimensione. | varchar(255) |
| **`videoepisode`** | La dimensione [Episodio](/help/components/dimensions/sm-video-metadata.md) Elemento multimediale in streaming. | varchar(255) |
| **`videofeedtype`** | Tipo [di feed](/help/components/dimensions/sm-video-metadata.md) Media Dimensione Streaming multimediale. | varchar(255) |
| **`videogenre`** | La [dimensione Genere](/help/components/dimensions/sm-video-metadata.md) Streaming Media. Questa dimensione consente più valori nello stesso hit, delimitati da una virgola. | testo |
| **`videolength`** | La dimensione [Lunghezza del contenuto (variabile)](/help/components/dimensions/sm-core.md) dei contenuti multimediali in streaming. | numero intero |
| **`videomvpd`** | La dimensione [MVPD](/help/components/dimensions/sm-video-metadata.md) dei file multimediali in streaming. | varchar(255) |
| **`videoname`** | La dimensione [Nome contenuto (variabile)](/help/components/dimensions/sm-core.md) elemento multimediale in streaming. | varchar(255) |
| **`videonetwork`** | La dimensione [Network](/help/components/dimensions/sm-video-metadata.md) Streaming Media. | varchar(255) |
| **`videopath`** | La dimensione [Percorso file multimediali](/help/components/dimensions/sm-core.md) in streaming. | varchar(100) |
| **`videoplayername`** | La dimensione [Nome del lettore di contenuti](/help/components/dimensions/sm-core.md) di contenuti multimediali in streaming. | varchar(255) |
| **`videotime`** | La metrica [Tempo contenuto trascorso](/help/components/metrics/sm-core.md) per Streaming Media. | numero intero |
| **`videoqoebitrateaverageevar`** | La dimensione [Velocità in bit media](/help/components/dimensions/sm-quality.md) dei file multimediali in streaming. | varchar(255) |
| **`videoqoebitratechangecountevar`** | [Modifiche al bitrate](/help/components/dimensions/sm-quality.md) dimensione Contenuti multimediali in streaming. | varchar(255) |
| **`videoqoebuffercountevar`** | La dimensione [Eventi buffer](/help/components/dimensions/sm-quality.md) File multimediali in streaming. | varchar(255) |
| **`videoqoebuffertimeevar`** | La dimensione [Durata totale del buffer](/help/components/dimensions/sm-quality.md) dei file multimediali in streaming. | varchar(255) |
| **`videoqoedroppedframecountevar`** | La dimensione [Frame rilasciati](/help/components/dimensions/sm-quality.md) dei file multimediali in streaming. | varchar(255) |
| **`videoqoeerrorcountevar`** | La dimensione [Errori](/help/components/dimensions/sm-quality.md) dei file multimediali in streaming. | varchar(255) |
| **`videoqoeextneralerrors`** | La dimensione [ID errore esterni](/help/components/dimensions/sm-quality.md) dei file multimediali in streaming. Questa dimensione consente più valori nello stesso hit. | testo |
| **`videoqoeplayersdkerrors`** | Gli ID di errore dell&#39;SDK [del lettore Dimensione](/help/components/dimensions/sm-quality.md) Streaming multimediale. Questa dimensione consente più valori nello stesso hit. | testo |
| **`videoqoetimetostartevar`** | La [dimensione Ora di avviare](/help/components/dimensions/sm-quality.md) lo streaming multimediale. | varchar(255) |
| **`videoseason`** | La [dimensione Season](/help/components/dimensions/sm-video-metadata.md) Streaming Media. | varchar(255) |
| **`videosegment`** | La dimensione [Segmento di contenuto](/help/components/dimensions/sm-core.md) elemento multimediale in streaming. | varchar(255) |
| **`videoshow`** | La dimensione [Mostra](/help/components/dimensions/sm-video-metadata.md) file multimediali in streaming. | varchar(255) |
| **`videoshowtype`** | La dimensione [Mostra tipo](/help/components/dimensions/sm-video-metadata.md) di Streaming Media. | varchar(255) |
| **`videostreamtype`** | La dimensione [Tipo di flusso](/help/components/dimensions/sm-core.md) elemento multimediale in streaming. | varchar(255) |
| **`visid_high`** | Utilizzato con `visid_low` per identificare in modo univoco un visitatore. | Bigint senza segno |
| **`visid_low`** | Utilizzato con `visid_high` per identificare in modo univoco un visitatore. | Bigint senza segno |
| **`visid_new`** | Flag che determina se l’hit contiene un ID visitatore appena generato. | char(1) |
| **`visid_timestamp`** | Se un ID visitatore è stato generato di recente, fornisce la marca temporale in UNIX® dell’ora in cui è stato generato l’ID visitatore. | Intero |
| **`visid_type`** | Non per uso esterno; utilizzato internamente da Adobe per l’elaborazione delle ottimizzazioni. Un ID numerico che rappresenta il metodo utilizzato per identificare il visitatore.<br>`0`: ID visitatore personalizzato o sconosciuto/non applicabile<br>`1`: fallback dell’IP e dell’agente utente <br>`2`: intestazione dell’abbonato mobile HTTP <br>`3`: valore cookie legacy (`s_vi`) <br>`4` valore cookie di fallback (`s_fid`) <br>`5`: servizio identità | tinyint unsigned |
| **`visit_keywords`** | La dimensione [Parola chiave di ricerca](/help/components/dimensions/search-keyword.md). Questa colonna utilizza un limite di caratteri non standard di varchar(244) per adattarsi alla logica back-end utilizzata da Adobe. | varchar(244) |
| **`visit_num`** | La [dimensione del numero di](/help/components/dimensions/visit-number.md) visita. Inizia a 1 e viene incrementato ogni volta che inizia una nuova visita per visitatore. | int senza segno |
| **`visit_page_num`** | La [dimensione Profondità](/help/components/dimensions/hit-depth.md) hit. Aumenta di 1 per ogni hit generato dal visitatore. Ripristina ogni visita. | int senza segno |
| **`visit_ref_domain`** | In base alla colonna `visit_referrer`. Il primo dominio di riferimento della visita. | varchar(100) |
| **`visit_ref_type`** | ID numerico che rappresenta il tipo di referente del primo referente del visita. Fa riferimento alla tabella di ricerca `referrer_type.tsv`. | tinyint unsigned |
| **`visit_referrer`** | Il primo referrer della visita. | varchar(255) |
| **`visit_search_engine`** | Un ID numerico che rappresenta il primo motore di ricerca della visita. Fa riferimento alla tabella di ricerca `search_engines.tsv`. | smallint senza segno |
| **`visit_start_page_url`** | Il primo URL della visita. | varchar(255) |
| **`visit_start_pagename`** | Il valore Nome pagina nel primo hit della visita. | varchar(100) |
| **`visit_start_time_gmt`** | Marca temporale (in tempo UNIX®) del primo hit della visita. | Intero |
| **`weekly_visitor`** | Flag che determina se l’hit è un nuovo visitatore settimanale. | tinyint unsigned |
| **`yearly_visitor`** | Flag che determina se l’hit è un nuovo visitatore annuale. | tinyint unsigned |
| **`zip`** | Consente di popolare la dimensione [Codice postale](/help/components/dimensions/zip-code.md). Consulta anche `geo_zip`. | varchar(50) |

{style="table-layout:auto"}

## Colonne inutilizzate o ritirate

Il seguente elenco di colonne non è utilizzato e in genere non contiene dati. Le colonne che contengono dati non sono supportate dalle librerie di raccolta dati correnti e non sono dimensioni disponibili in Analysis Workspace.

* `adclassificationcreative`
* `click_action`
* `click_action_type`
* `click_context`
* `click_context_type`
* `click_sourceid`
* `click_tag`
* `hier1` - `hier5`
* `homepage`
* `ip2`
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
* `mobiledayssincelastupgrade`
* `mobiledeeplinkid.name`
* `mobileinstalls`
* `mobilelaunches`
* `mobilelaunchessincelastupgrade`
* `mobileltv`
* `mobileltvtotal`
* `mobilemessageclicks`
* `mobilemessageid.dest`
* `mobilemessageid.name`
* `mobilemessageid.type`
* `mobilemessageimpressions`
* `mobilemessagepushpayloadid.name`
* `mobilemessageviews`
* `mobilemonthlyengagedusers`
* `mobileosenvironment`
* `mobileplacedwelltime`
* `mobileplaceentry`
* `mobileplaceexit`
* `mobileprevsessionlength`
* `mobilerelaunchcampaigntrackingcode.name`
* `mobileupgrades`
* `namespace`
* `p_plugins`
* `page_event_var3`
* `partner_plugins`
* `plugins`
* `prev_page`
* `product_merchandising`
* `service`
* `socialaccountandappids`
* `socialassettrackingcode`
* `socialauthor`
* `socialaveragesentiment`
* `socialaveragesentiment (deprecated)`
* `socialcontentprovider`
* `socialfbstories`
* `socialfbstorytellers`
* `socialinteractioncount`
* `socialinteractiontype`
* `sociallanguage`
* `sociallatlong`
* `sociallikeadds`
* `sociallink`
* `sociallink (deprecated)`
* `socialmentions`
* `socialowneddefinitioninsighttype`
* `socialowneddefinitioninsightvalue`
* `socialowneddefinitionmetric`
* `socialowneddefinitionpropertyvspost`
* `socialownedpostids`
* `socialownedpropertyid`
* `socialownedpropertyname`
* `socialownedpropertypropertyvsapp`
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
* `survey`
* `survey_instances`
* `tnt_post_vista`
* `ua_color`
* `ua_os`
* `ua_pixels`
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
