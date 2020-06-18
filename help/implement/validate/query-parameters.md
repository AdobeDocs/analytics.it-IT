---
title: Parametri query della raccolta dati
description: Elenca tutti i parametri della stringa di query utilizzati nelle richieste di immagini.
translation-type: tm+mt
source-git-commit: edf3ac3ebc99444b86bcd9239cef9ed84d797565
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 6%

---


# Parametri query della raccolta dati

Nella tabella seguente sono elencati tutti i parametri della stringa di query utilizzati da Adobe nelle richieste di immagini. Queste informazioni possono essere utilizzate per il debug con gli analizzatori [di](packet-monitor.md)pacchetti, per la [codifica di richieste](../other/hardcoded.md)di immagini o per l&#39;utilizzo di variabili [](../vars/page-vars/dynamic-variables.md)dinamiche.

| Parametro | , variabile di implementazione Analytics | Descrizione |
| --- | --- | --- |
| `aamlh` | None |  hint posizione Audience Manager. Utilizzata nell&#39;integrazione  profilo condiviso di Experience Cloud. |
| `aamb` | None | BLOB  Audience Manager. Utilizzata nell&#39;integrazione  profilo condiviso di Experience Cloud. |
| `aid` | None |  ID visitatore Analytics. |
| `AQB` | None | Indica l’inizio di una stringa di query per la richiesta di immagini. |
| `AQE` | None | Indica la fine di una richiesta di immagine, il che significa che la richiesta non è stata troncata. |
| `bh` | None | Altezza browser (in pixel). Utilizzata nella dimensione dell&#39;altezza [del](/help/components/dimensions/browser-height.md) browser. |
| `bw` | None | Larghezza browser (in pixel). Utilizzata nella dimensione Larghezza [](/help/components/dimensions/browser-width.md) browser. |
| `c` | None | Qualità del colore (in bit). Utilizzata nella dimensione [Profondità](/help/components/dimensions/color-depth.md) colore. |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica l&#39;inizio delle variabili dei dati di contesto. Non contiene mai un valore. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica la fine delle variabili dei dati contestuali. Non contiene mai un valore. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Proprietà](/help/components/dimensions/prop.md)o variabili di traffico personalizzate. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Il tipo di valuta utilizzata nell&#39;hit. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Il numero di periodi in un dominio. Utilizzato per memorizzare correttamente i cookie. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Codifica dei caratteri della richiesta di immagine. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Durata del cookie del visitatore. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Utilizzata nella dimensione delle sezioni [](/help/components/dimensions/site-section.md) Sito. |
| `cp` | None | Utilizzata nella dimensione Tipo [](/help/components/dimensions/hit-type.md) hit. |
| `ct` | None | Utilizzata nella dimensione Tipo [di](/help/components/dimensions/connection-type.md) connessione. |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica cosa utilizzare per le variabili dinamiche. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Abbreviazione della stringa di `events` query. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Elenco degli eventi della pagina separati da virgole. Utilizzata dalla maggior parte delle [metriche](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | L&#39;URL corrente della pagina, fino a 255 byte. Utilizzata nella dimensione URL [](/help/components/dimensions/page-url.md) pagina. |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Gli URL di lunghezza superiore a 255 byte vengono suddivisi. I primi 255 byte vengono visualizzati nel `g` parametro e tutti i byte rimanenti appaiono nel `-g` parametro. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Abbreviazione della stringa di `pageName` query. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Abbreviazione della stringa di `pageType` query. |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensioni della gerarchia. |
| `hp` | None | Non più utilizzato. Nelle versioni precedenti di Adobe  Analytics, veniva determinato se l’URL corrente era la home page del browser. |
| `j` | None | La versione JavaScript installata nel browser. |
| `k` | None | Utilizzata nella dimensione [Cookie support](/help/components/dimensions/cookie-support.md) . |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variabili elenco. |
| `mid` | None |  ID visitatore Experience Cloud. |
| `ndh` | None | Flag che indica se la richiesta di immagine è nata da AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Consente di determinare dove vengono impostati i cookie. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificatore oggetto per l’ultima pagina. Utilizzata in  Activity Map. |
| `ot` | None | Nome oggetto per l’ultima pagina. Utilizzato nelle versioni precedenti di  Activity Map. |
| `p` | None | Non più utilizzato. Elenco dei plug-in utilizzati nel browser. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Utilizzata nella dimensione [Pagina](/help/components/dimensions/page.md) . |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Utilizzato nelle [pagine la dimensione non trovata](/help/components/dimensions/pages-not-found.md) . |
| `pccr` | None | Impostato solo per i nuovi visitatori e impostato sempre su `true`. Consente di evitare reindirizzamenti infiniti. |
| `pe` | [`linkType`](../vars/config-vars/linktype.md) | Determina il tipo di collegamento personalizzato. Obbligatorio per collegamenti [](/help/components/dimensions/custom-link.md)personalizzati, collegamenti [](/help/components/dimensions/download-link.md)per il download e collegamenti [](/help/components/dimensions/exit-link.md)di uscita. |
| `pev1` | None | L&#39;URL su cui si è verificato il collegamento personalizzato. |
| `pev2` | [`linkName`](../vars/config-vars/linkname.md) | Nome descrittivo del collegamento personalizzato. |
| `pev3` | None | Non più utilizzato. Elementi cardine tracciati nelle versioni precedenti del reporting video. |
| `pf` | None | bandiera Platform; solo per Adobe. Non modificare. |
| `pid` | None | Identificatore pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di  Activity Map. |
| `pidt` | None | Identificatore pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di  Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Abbreviazione della stringa di `products` query. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabile dei prodotti. Utilizzata nelle dimensioni [Prodotto](/help/components/dimensions/product.md) e [Categoria](/help/components/dimensions/category.md) . |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Utilizzato per deduplicare gli acquisti. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL di riferimento dell’hit. Utilizzata nelle dimensioni delle origini di traffico, come [Referente](/help/components/dimensions/referrer.md) e Dominio [di riferimento](/help/components/dimensions/referring-domain.md) |
| `s` | None | Risoluzione dello schermo, in `width x height`. Utilizzata nella dimensione delle risoluzioni [del](/help/components/dimensions/monitor-resolution.md) monitor. |
| `server` | [`server`](../vars/page-vars/server.md) | [Dimensioni del server](/help/components/dimensions/server.md) . |
| `sv` | [`server`](../vars/page-vars/server.md) | Abbreviazione della stringa di `server` query. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimensione stato. |
| `t` | None | Data/ora generata dell’hit. Utilizza il formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` è data/ora in JavaScript. Il mese `0` è gennaio, mentre il mese `11` è dicembre.<br>- `w` è il giorno della settimana. `0` è domenica, mentre `6` è sabato.<br>- `o` è l&#39;offset GMT negativo in minuti. Ad esempio, `420` è GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Il set di marche temporali personalizzato con l’hit. Generalmente utilizzato per il tracciamento offline. |
| `v` | None | Utilizzata nella dimensione [Java abilitata](/help/components/dimensions/java-enabled.md) . |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Dimensione codice](/help/components/dimensions/tracking-code.md) di tracciamento. |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md)o dimensioni di conversione personalizzate. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabile ID visitatore. |
| `vmk` | `vmk` | Non più utilizzato. Chiave di migrazione dei visitatori, che ha contribuito alla migrazione delle implementazioni dai cookie di terze parti a quelli di prime parti. |
| `vvp` | `variableProvider` | Utilizzata nei connettori dati. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Utilizzato con Origini dati per collegare i dati online e offline. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Utilizzata nella dimensione del codice [](/help/components/dimensions/zip-code.md) ZIP. |
