---
description: Esaminate le variabili e le relative limitazioni.
keywords: Implementazione di Analytics; variable; limitazioni; limits
seo-description: Esaminate le variabili e le relative limitazioni.
seo-title: Variabili e limitazioni
solution: Analytics
subtopic: Variabili
title: Variabili e limitazioni
topic: Sviluppatore e implementazione
uuid: 028677 a 7-2132-4 ee 7-9 cc 1-697 c 2 c 09 b 087
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Variabili e limitazioni

Esaminate le variabili e le relative limitazioni.

>[!NOTE]
>
>See [Configuration Variables](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_8FCA630706334F54B4DCB607378BCD00) and [Page Variables](../../../implement/js-implementation/c-variables/page-variables.md#concept_37933DFF2FC547A0A3B296D5E646B6A3) for an in-depth look at the most common Analytics variables.

The following table provides at-a-glance information about [!DNL Analytics] variables:

| Variabile | Descrizione |
|---|---|
| s_account | Determina la suite di rapporti in cui i dati vengono memorizzati e segnalati. |
| browserHeight | Visualizza l'altezza della finestra del browser. |
| browserWidth | Visualizza la larghezza della finestra del browser. |
| campaign | Identifica le campagne di marketing utilizzate per portare visitatori sul sito. The value of *`campaign`* is usually taken from a query string parameter. |
| channel | In genere identifica una sezione del sito Web. Ad esempio, un esercente potrebbe avere sezioni come Electronics, Toys o Apparel. Un sito multimediale può avere sezioni come News, Sport o Business. |
| charSet | Converte il set di caratteri della pagina Web in UTF -8. |
| colorDepth | Visualizza il numero di bit utilizzati per visualizzare il colore su ciascun pixel della schermata. |
| connectionType | Indica (in Microsoft Internet Explorer) se il browser è configurato su una connessione LAN o modem. |
| Cookiedomainperiod | Determines the domain on which the [!DNL Analytics] [!UICONTROL visitor ID] (s_vi) cookie will be set by determining the number of periods in the domain of the page URL. For `www.mysite.com`, *`cookieDomainPeriods`* should be "2." For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3." |
| cookieLifetime | Used by both JavaScript and [!DNL Analytics] servers to determine the lifespan of a cookie. |
| cookiesEnabled | Indica se un cookie di sessione first-party può essere impostato da javascript. |
| currencyCode | Determines the conversion rate to be applied to revenue as it enters the [!DNL Analytics] databases. [!DNL Analytics] i database archiviano tutti gli importi monetari in una valuta di vostra scelta. If that currency is the same as that specified in *`currencyCode`*, or *`currencyCode`* is empty, no conversion is applied. |
| dc | Consente di impostare il centro dati in cui i dati vengono inviati. |
| Doplugins | *`doPlugins`* è un riferimento alla *`s_doPlugins`* funzione. It allows the *`s_doPlugins`* function to be called at the appropriate location within the JavaScript file. |
| Dynamicaccountlist | Seleziona in modo dinamico una suite di rapporti a cui vengono inviati i dati. The *`dynamicAccountList`* variable contains the rules that used to determine the destination report suite. |
| Dynamicaccountmatch | Uses the DOM object to retrieve the section of the URL to which all rules in *`dynamicAccountList`* are applied. This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' |
| Dynamicaccountselection | Consente di selezionare in modo dinamico la suite di rapporti in base all'URL di ciascuna pagina. |
| dynamicVariablePrefix | Consente la distribuzione di variabili da compilare dinamicamente. I cookie, le intestazioni della richiesta e i parametri delle stringhe di query immagine sono disponibili per essere inseriti in modo dinamico. |
| Evarn | Used for building custom reports within the [!DNL Analytics] [!UICONTROL Conversion Module]. When an eVar is set to a value for a visitor, [!DNL Analytics] remembers that value until it expires. Tutti gli eventi di successo rilevati da un visitatore mentre il valore evar è attivo vengono conteggiati verso il valore evar. |
| events | Registra eventi comuni di successo del carrello acquisti e eventi di successo personalizzati. |
| Fpcookiedomainperiod | Determines the domain on which [!DNL Analytics] cookies other than the [!UICONTROL visitor ID] (s_vi) cookie will be set by determining the number of periods in the domain of the page. |
| Hiern | Determina la posizione di una pagina nella gerarchia del sito. Questa variabile è particolarmente utile per i siti con più di tre livelli nella struttura del sito. |
| homepage | Indica (in Internet Explorer) se la pagina corrente è impostata come home page dell'utente. |
| javaEnabled | Indica se Java è abilitato nel browser. |
| Javascriptversion | Visualizza la versione di javascript supportata dal browser. |
| Linkdownloadfiletypes | Un elenco separato da virgole di estensioni di file. If your site contains links to files with any of these extensions, the URLs of these links appear in the [!UICONTROL File Downloads] report. |
| Linkexternalfilters | If your site contains many links to external sites, and you don't want to track all exit links, *`linkExternalFilters`* can be used to report on a specific subset of exit links. |
| Linkinternalfilters | Determina i collegamenti sul sito che consentono di uscire dai collegamenti. È un elenco di filtri separati da virgole che rappresentano i collegamenti che fanno parte del sito. |
| Linkleavequerystring | Determines whether or not the query string should be included in the [!UICONTROL Exit Links] and [!UICONTROL File Download] reports. |
| linkName | An optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link. The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it. |
| linkTrackEvents | Contiene gli eventi che devono essere inviati con collegamenti personalizzati, scaricati e exit. This variable is only considered if *`linkTrackVars`* contains "events." |
| linkTrackVars | Un elenco separato da virgole di variabili che verrà inviato con collegamenti personalizzati, exit e download. If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. |
| linkType | Una variabile opzionale utilizzata nel tracciamento dei collegamenti che determina quale rapporto verrà visualizzato un Nome collegamento o un URL (personalizzato, scarica o uscita). *`linkType`* solitamente non è necessario perché il secondo parametro nella *`tl()`* funzione lo sostituisce. |
| Medialength | Specifica la lunghezza totale del supporto in fase di riproduzione. |
| Medianame | Specifica il nome dell'elemento video o multimediale. It is only available via the [!UICONTROL Data Insertion API] and [!UICONTROL Full Processing Data Source]. |
| Mediaplayer | Specifica il lettore utilizzato per utilizzare un video o un elemento multimediale. |
| Mediasession | Specifica i segmenti di una risorsa video o multimediale consumata. |
| Media. trackevents | Identifica gli eventi da inviare con un hit di supporto. It is only applicable with JavaScript [!UICONTROL ActionSource.]. |
| Media. trackvars | Identifica le variabili da inviare con un hit di supporto. It is only applicable with JavaScript [!UICONTROL ActionSource.]. |
| dispositivi mobili | Controlla l'ordine in cui i cookie e gli ID utente sono utilizzati per identificare i visitatori. |
| s_ objectid | A global variable that should be set in the [!UICONTROL onClick] event of a link. Creando un ID oggetto univoco per un collegamento o una posizione di collegamento su una pagina, puoi migliorare il tracciamento della mappa del visitatore o utilizzare la mappa clic visitatore per generare rapporti su un tipo di collegamento o su una posizione, piuttosto che sull'URL del collegamento. |
| pageName | Contiene il nome di ogni pagina sul sito. If *`pageName`* is blank, the URL is used to represent the page name in [!DNL Analytics]. |
| pageType | Utilizzata solo per designare una pagina di errore 404 pagina non trovata. È disponibile solo un possibile valore, che è "errorpage". On a 404 Error page, the *`pageName`* variable should not be populated. |
| pageURL | In rare cases, the URL of the page is not the URL that you would like reported in [!DNL Analytics]. To accommodate these situations, [!DNL Analytics] offers the *`pageURL`* variable, which overrides the actual URL of the page. |
| plugins | Sui browser Netscape e Mozilla sono elencati i plug-in installati nel browser. |
| products | Utilizzato per tenere traccia dei prodotti e delle categorie di prodotti, nonché quantità di acquisto e prezzo di acquisto. The *`products`* variable should always be set in conjunction with a success event. Optionally, the *`products`* variable can track custom numeric and currency events, as well as [!UICONTROL Merchandising] eVars. |
| propN | Used for building custom reports within the [!DNL Analytics] [!UICONTROL Traffic Module]. [!UICONTROL props] possono essere utilizzati come contatori (per calcolare il numero di volte in cui viene inviata una visualizzazione di pagina), per i rapporti percorsi o nei rapporti di correlazione. |
| purchaseID | Used to keep an order from being counted multiple times by [!DNL Analytics]. Whenever the purchase event is used on your site, you should use the *`purchaseID`* variable. |
| referrer | Ripristina le informazioni relative al referente. |
| resolution | Visualizza la risoluzione del monitor del visitatore che visualizza la pagina Web. |
| server | Mostra il dominio di una pagina Web (per mostrare quali domini arrivano) o il server che distribuisce la pagina (per un riferimento rapido al bilanciamento del carico). |
| state | Acquisisce lo stato in cui risiede un visitatore del sito. |
| Trackdownloadlinks | Set *`trackDownloadLinks`* to 'true' if you want to track links to downloadable files on your site. If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* determines which links are downloadable files. |
| Trackexternallinks | If *`trackExternalLinks`* is 'true,' *`linkInternalFilters`* and *`linkExternalFilters`* determines whether any link clicked is an exit link. |
| trackingServer | Utilizzato per l'implementazione dei cookie di prime parti per specificare il dominio in cui viene scritto il cookie e il cookie immagine. Utilizzato per pagine non sicure. |
| trackingServerSecure | Utilizzato per l'implementazione dei cookie di prime parti per specificare il dominio in cui viene scritto il cookie e il cookie immagine. Utilizzato per le pagine sicure. |
| Trackinlinestats | Determina se i dati della mappa clic del visitatore vengono raccolti. |
| transactionID | Associa dati offline a una transazione online (come un lead o un acquisto generato online). Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. See the [Data Sources Guide](https://marketing.adobe.com/resources/help/en_US/sc/datasources/). |
| s_ useplugins | If the *`s_doPlugins`* function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.' When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request. |
| visitorID | Visitors may be identified by the *`visitorID`* tag, or by IP address/User Agent. The *`visitorID`* may be up to 100 alphanumeric characters and must not contain a hyphen. |
| visitorNamespace | If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. Questa variabile viene utilizzata per identificare il dominio con cui sono impostati i cookie. If *`visitorNamespace`* changes, all visitors reported in [!DNL Analytics] may become new visitors. In breve, non modificate questa variabile senza l'approvazione di un consulente Adobe. |
| zip | Acquisisce il codice ZIP in cui risiede un visitatore del sito. |

