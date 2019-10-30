---
description: Osserva le variabili e i loro limiti di livello elevato.
keywords: Implementazione di Analytics;variabile;limitazioni;limiti
seo-description: Osserva le variabili e i loro limiti di livello elevato.
seo-title: Variabili e limitazioni
solution: Analytics
subtopic: Variabili
title: Variabili e limitazioni
topic: Sviluppatore e implementazione
uuid: 028677a7-2132-4ee7-9cc1-697c2c09b087
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Variabili e limitazioni

Osserva le variabili e i loro limiti di livello elevato.

> [!NOTE] Consulta Variabili [di](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00) configurazione e variabili [di](../../../implement/js-implementation/c-variables/page-variables.md#concept_37933DFF2FC547A0A3B296D5E646B6A3) pagina per un'analisi approfondita delle variabiliAnalytics più comuni.

La tabella seguente fornisce informazioni dettagliate sulle [!DNL Analytics] variabili:

| Variabile | Descrizione |
|---|---|
| s_account | Determina la suite di rapporti in cui i dati vengono memorizzati e segnalati. |
| browserHeight | Visualizza l'altezza della finestra del browser. |
| browserWidth | Visualizza la larghezza della finestra del browser. |
| campaign | Identifica le campagne di marketing utilizzate per portare i visitatori sul sito. Il valore di *`campaign`* viene in genere ricavato da un parametro di stringa di query. |
| channel | In genere identifica una sezione del sito Web. Ad esempio, un esercente può avere sezioni quali Elettronica, Giocattoli o Abbigliamento. Un sito multimediale può contenere sezioni quali News, Sport o Business. |
| charSet | Converte il set di caratteri della pagina Web in UTF-8. |
| colorDepth | Visualizza il numero di bit utilizzati per visualizzare il colore su ogni pixel dello schermo. |
| connectionType | Indica (in Microsoft Internet Explorer) se il browser è configurato su una connessione LAN o modem. |
| cookieDomainPeriods | Determines the domain on which the [!DNL Analytics] [!UICONTROL visitor ID] (s_vi) cookie will be set by determining the number of periods in the domain of the page URL. Ad `www.mysite.com`esempio, *`cookieDomainPeriods`* dovrebbe essere "2". Ad `www.mysite.co.jp`esempio, *`cookieDomainPeriods`* dovrebbe essere "3". |
| cookieLifetime | Utilizzata sia da JavaScript che [!DNL Analytics] da server per determinare la durata di vita di un cookie. |
| cookiesEnabled | Indica se un cookie di sessione di prime parti può essere impostato da JavaScript. |
| currencyCode | Determina il tasso di conversione da applicare alle entrate quando queste entrano nei [!DNL Analytics] database. [!DNL Analytics] i database memorizzano tutti gli importi monetari in una valuta di vostra scelta. Se la valuta è la stessa specificata in *`currencyCode`*, o *`currencyCode`* è vuota, non viene applicata alcuna conversione. |
| dc | Consente di impostare il centro dati a cui vengono inviati i dati. |
| doPlugins | *`doPlugins`* è un riferimento alla *`s_doPlugins`* funzione. Consente di chiamare la *`s_doPlugins`* funzione nella posizione appropriata all'interno del file JavaScript. |
| dynamicAccountList | Seleziona dinamicamente una suite di rapporti a cui vengono inviati i dati. La *`dynamicAccountList`* variabile contiene le regole utilizzate per determinare la suite di rapporti di destinazione. |
| dynamicAccountMatch | Utilizza l'oggetto DOM per recuperare la sezione dell'URL a cui *`dynamicAccountList`* vengono applicate tutte le regole. Questa variabile è valida solo se *`dynamicAccountSelection`* è impostata su 'True'. |
| dynamicAccountSelection | Consente di selezionare dinamicamente la suite di rapporti in base all'URL di ogni pagina. |
| dynamicVariablePrefix | Consente alla distribuzione di contrassegnare le variabili che devono essere popolate in modo dinamico. I cookie, le intestazioni delle richieste e i parametri delle stringhe delle query sulle immagini possono essere compilati in modo dinamico. |
| eVarN | Utilizzato per la creazione di rapporti personalizzati all'interno dell' [!DNL Analytics] area [!UICONTROL Conversion Module]. Quando un'eVar viene impostata su un valore per un visitatore, [!DNL Analytics] ricorda tale valore fino alla scadenza. Eventuali eventi di successo riscontrati da un visitatore mentre il valore eVar è attivo vengono conteggiati per il valore eVar. |
| events | Registra gli eventi di successo comuni del carrello e gli eventi di successo personalizzati. |
| fpCookieDomainPeriods | Determina il dominio in cui verranno impostati [!DNL Analytics] i cookie diversi dal cookie [!UICONTROL visitor ID] (s_vi), determinando il numero di punti nel dominio della pagina. |
| hierN | Determina la posizione di una pagina nella gerarchia del sito. Questa variabile è particolarmente utile per i siti con più di tre livelli nella struttura del sito. |
| homepage | Indica (in Internet Explorer) se la pagina corrente è impostata come home page dell'utente. |
| javaEnabled | Indica se Java è abilitato nel browser. |
| javascriptVersion | Visualizza la versione di JavaScript supportata dal browser. |
| linkDownloadFileTypes | Un elenco separato da virgole di estensioni di file. Se il sito contiene collegamenti a file con una di queste estensioni, gli URL di tali collegamenti vengono visualizzati nel [!UICONTROL File Downloads] rapporto. |
| linkExternalFilters | Se il sito contiene molti collegamenti a siti esterni e non si desidera tenere traccia di tutti i collegamenti di uscita, *`linkExternalFilters`* è possibile utilizzare per generare rapporti su un sottoinsieme specifico di collegamenti di uscita. |
| linkInternalFilters | Determina quali collegamenti sul sito sono collegamenti di uscita. Si tratta di un elenco di filtri separati da virgole che rappresentano i collegamenti che fanno parte del sito. |
| linkLeftQueryString | Determina se la stringa di query deve essere inclusa o meno nei [!UICONTROL Exit Links] report e [!UICONTROL File Download] . |
| linkName | Variabile opzionale utilizzata in [!UICONTROL Link Tracking] che determina il nome di un collegamento personalizzato, di download o di uscita. La *`linkName`* variabile non è normalmente necessaria perché il terzo parametro della *`tl()`* funzione la sostituisce. |
| linkTrackEvents | Contiene gli eventi che devono essere inviati con collegamenti personalizzati, di download e di uscita. Questa variabile viene considerata solo se *`linkTrackVars`* contiene "events". |
| linkTrackVars | Elenco separato da virgole di variabili che verranno inviate con collegamenti personalizzati, di uscita e di download. Se *`linkTrackVars`* è impostato su "", tutte le variabili con valori vengono inviate con dati di collegamento. |
| linkType | Variabile opzionale utilizzata nel tracciamento dei collegamenti che determina quale report verrà visualizzato un nome o un URL collegamento (personalizzato, scaricato o esce dai collegamenti). *`linkType`* di norma non è necessario perché il secondo parametro della *`tl()`* funzione lo sostituisce. |
| mediaLength | Specifica la lunghezza totale del contenuto multimediale riprodotto. |
| mediaName | Specifica il nome del video o dell’elemento multimediale. È disponibile solo tramite [!UICONTROL Data Insertion API] e [!UICONTROL Full Processing Data Source]. |
| mediaPlayer | Specifica il lettore utilizzato per utilizzare un elemento video o multimediale. |
| mediaSession | Specifica i segmenti di una risorsa video o multimediale utilizzata. |
| Media.trackEvents | Identifica gli eventi da inviare con un hit multimediale. È applicabile solo con JavaScript [!UICONTROL ActionSource.]. |
| Media.trackVars | Identifica le variabili da inviare con un hit per file multimediali. È applicabile solo con JavaScript [!UICONTROL ActionSource.]. |
| dispositivi mobili | Controlla l'ordine in cui i cookie e gli ID utente iscritto vengono utilizzati per identificare i visitatori. |
| s_objectID | Variabile globale da impostare in caso [!UICONTROL onClick] di collegamento. Creando un ID oggetto univoco per un collegamento o una posizione di collegamento su una pagina, puoi migliorare il monitoraggio dei clic del visitatore o utilizzare la mappa dei clic del visitatore per segnalare un tipo di collegamento o una posizione, anziché l’URL del collegamento. |
| pageName | Contiene il nome di ogni pagina del sito. Se *`pageName`* è vuoto, l’URL viene utilizzato per rappresentare il nome della pagina in [!DNL Analytics]. |
| pageType | Utilizzato solo per indicare una pagina 404 Page Not Found Error (Impossibile trovare la pagina 404). Ha un solo valore possibile, che è "errorPage". In una pagina di errore 404, la *`pageName`* variabile non deve essere compilata. |
| pageURL | In alcuni rari casi, l’URL della pagina non è l’URL in cui si desidera visualizzare i rapporti [!DNL Analytics]. Per far fronte a queste situazioni, [!DNL Analytics] offre la *`pageURL`* variabile, che sostituisce l’URL effettivo della pagina. |
| plugins | Nei browser Netscape e Mozilla, elenca i plug-in installati nel browser. |
| products | Utilizzato per tenere traccia di prodotti e categorie di prodotti, nonché della quantità di acquisto e del prezzo di acquisto. La *`products`* variabile deve sempre essere impostata insieme a un evento success. Facoltativamente, la *`products`* [!UICONTROL Merchandising] variabile può tenere traccia di eventi numerici e valutari personalizzati, nonché di eVar. |
| propN | Utilizzato per la creazione di rapporti personalizzati all'interno dell' [!DNL Analytics] area [!UICONTROL Traffic Module]. [!UICONTROL props] può essere utilizzato come contatori (per contare il numero di volte che una visualizzazione di pagina viene inviata), per i report dei percorsi o nei report delle correlazioni. |
| purchaseID | Utilizzato per evitare che un ordine venga conteggiato più volte da [!DNL Analytics]. Ogni volta che l'evento di acquisto viene utilizzato sul sito, è necessario utilizzare la *`purchaseID`* variabile. |
| referrer | Ripristina le informazioni di referente perse. |
| resolution | Visualizza la risoluzione del monitor del visitatore che visualizza la pagina Web. |
| server | Mostra il dominio di una pagina Web (per mostrare i domini a cui arrivano gli utenti) o il server che distribuisce la pagina (per un riferimento rapido per il bilanciamento del carico). |
| state | Acquisisce lo stato in cui risiede un visitatore sul sito. |
| trackDownloadLinks | Impostate *`trackDownloadLinks`* su 'true' se desiderate tenere traccia dei collegamenti ai file scaricabili sul sito. Se *`trackDownloadLinks`* è 'true', *`linkDownloadFileTypes`* determina quali collegamenti sono file scaricabili. |
| trackExternalLinks | Se *`trackExternalLinks`* è "true" *`linkInternalFilters`* e *`linkExternalFilters`* determina se un collegamento selezionato è un collegamento di uscita. |
| trackingServer | Utilizzato per l’implementazione di cookie di prime parti per specificare il dominio in cui vengono scritti la richiesta di immagine e il cookie. Utilizzato per pagine non sicure. |
| trackingServerSecure | Utilizzato per l’implementazione di cookie di prime parti per specificare il dominio in cui vengono scritti la richiesta di immagine e il cookie. Utilizzato per pagine sicure. |
| trackInlineStats | Determina se i dati della mappa clic visitatore vengono raccolti. |
| transactionID | Collega i dati offline a una transazione online (come un lead o un acquisto generato online). Ogni singolo *`transactionID`* inviato ad Adobe viene registrato in preparazione del [!UICONTROL Data Sources] caricamento di informazioni offline sulla transazione. Consulta la Guida alle origini [dati](https://marketing.adobe.com/resources/help/en_US/sc/datasources/). |
| s_usePlugins | Se la *`s_doPlugins`* funzione è disponibile e contiene codice utile, [!UICONTROL s_usePlugins] deve essere impostata su 'true'. Quando [!UICONTROL usePlugins] è 'true', la *`s_doPlugins`* funzione viene chiamata prima di ogni richiesta di immagine. |
| visitorID | I visitatori possono essere identificati dal *`visitorID`* tag o dall'indirizzo IP/Agente utente. I caratteri *`visitorID`* possono contenere fino a 100 caratteri alfanumerici e non devono contenere un trattino. |
| visitorNamespace | Se *`visitorNamespace`* viene utilizzato nel file JavaScript, non eliminarlo o modificarlo. Questa variabile viene utilizzata per identificare il dominio con cui sono impostati i cookie. Se *`visitorNamespace`* vengono apportate modifiche, tutti i visitatori segnalati in [!DNL Analytics] possono diventare nuovi visitatori. In breve, non modificate questa variabile senza l'approvazione di un consulente Adobe. |
| zip | Acquisisce il codice ZIP in cui risiede un visitatore del sito. |

