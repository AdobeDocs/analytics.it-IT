---
title: Parametri query della raccolta dati
description: Elenca tutti i parametri della stringa di query utilizzati nelle richieste di immagini.
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
source-git-commit: 7025d132da9d281da6d57973a195a5e86a39bf18
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 5%

---

# Parametri query della raccolta dati

Nella tabella seguente sono elencati tutti i parametri della stringa di query utilizzati dall’Adobe nelle richieste di immagini. Queste informazioni possono essere utilizzate durante il debug utilizzando [Analizzatori di pacchetti](packet-monitor.md), quando [richieste di immagini di codifica fissa](../other/hardcoded.md) o quando si utilizza [Variabili dinamiche](../vars/page-vars/dynamic-variables.md).

| Parametro | Variabile di implementazione di Analytics | Descrizione |
| --- | --- | --- |
| `aamlh` | None | Audience Manager di hint di posizione. Utilizzato nell’integrazione del profilo condiviso di Experience Cloud. |
| `aamb` | Nessuno | BLOB di Audience Manager. Utilizzato nell’integrazione del profilo condiviso di Experience Cloud. |
| `aid` | Nessuno | ID visitatore di Analytics. |
| `AQB` | Nessuno | Indica l&#39;inizio di una stringa di query di richiesta di immagine. |
| `AQE` | Nessuno | Indica la fine di una richiesta di immagine, il che significa che la richiesta non è stata troncata. |
| `bh` | Nessuno | Altezza browser (in pixel). Utilizzato nella dimensione [Altezza browser](/help/components/dimensions/browser-height.md). |
| `bw` | Nessuno | Larghezza browser (in pixel). Utilizzato nella dimensione [Larghezza browser](/help/components/dimensions/browser-width.md). |
| `c` | Nessuno | Qualità del colore (in bit). Utilizzato nella dimensione [Profondità colore](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica l&#39;inizio delle variabili di dati di contesto. Non contiene mai un valore. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica la fine delle variabili di dati di contesto. Non contiene mai un valore. |
| `c1` - `c75` | [`prop1` -  `prop75`](../vars/page-vars/prop.md) | [Proprietà](/help/components/dimensions/prop.md) o variabili di traffico personalizzate. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Il tipo di valuta utilizzato nell&#39;hit. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Il numero di periodi in un dominio. Utilizzato per memorizzare correttamente i cookie. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Codifica caratteri della richiesta di immagine. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Durata del cookie del visitatore. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Utilizzato nella dimensione [Sezioni del sito](/help/components/dimensions/site-section.md). |
| `cp` | Nessuno | Utilizzato nella dimensione [Tipo di hit](/help/components/dimensions/hit-type.md). |
| `ct` | Nessuno | Utilizzato nella dimensione [Tipo di connessione](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica cosa utilizzare per le variabili dinamiche. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Abbreviazione della stringa di query `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Elenco degli eventi nella pagina separati da virgole. Utilizzato dalla maggior parte delle [metriche](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | L’URL corrente della pagina, fino a 255 byte. Utilizzato nella dimensione [URL pagina](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Gli URL di lunghezza superiore a 255 byte vengono suddivisi. I primi 255 byte vengono visualizzati nel parametro `g` e tutti i byte rimanenti vengono visualizzati nel parametro `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Abbreviazione della stringa di query `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Abbreviazione della stringa di query `pageType`. |
| `h1` -  `h5` | [`hier1` -  `hier5`](../vars/page-vars/hier.md) | Dimensioni gerarchiche. |
| `hp` | Nessuno | Non più utilizzato. Nelle versioni precedenti di Adobe Analytics, veniva determinato se l’URL corrente era la home page del browser. |
| `j` | Nessuno | Versione JavaScript installata nel browser. |
| `k` | Nessuno | Utilizzato nella dimensione [Supporto cookie](/help/components/dimensions/cookie-support.md). |
| `l1` -  `l3` | [`list1` -  `list3`](../vars/page-vars/list.md) | Variabili elenco. |
| `lrt` | Nessuno | Il &quot;tempo dell’ultima richiesta&quot;, che è il tempo di andata e ritorno per l’ultima richiesta, in millisecondi. Viene inviato solo quando più richieste escono da una pagina o quando la pagina è un’applicazione a pagina singola (SPA). |
| `mid` | Nessuno | Experience Cloud di ID visitatore. |
| `ndh` | Nessuno | Flag che indica se la richiesta di immagine è stata originata da AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Consente di determinare dove vengono impostati i cookie. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificatore oggetto per l&#39;ultima pagina. Utilizzato in Activity Map. |
| `ot` | Nessuno | Nome dell’oggetto per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `p` | Nessuno | Non più utilizzato. Elenco dei plug-in utilizzati nel browser. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Utilizzato nella dimensione [Pagina](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Utilizzato nella dimensione [Pagine non trovate](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Nessuno | Impostato solo per i nuovi visitatori e sempre impostato su `true`. Consente di evitare reindirizzamenti infiniti. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determina il tipo di collegamento personalizzato. Obbligatorio per [Collegamenti personalizzati](/help/components/dimensions/custom-link.md), [Download link](/help/components/dimensions/download-link.md) e [Esci](/help/components/dimensions/exit-link.md). |
| `pev1` | Nessuno | URL su cui si è verificato il collegamento personalizzato. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Nome descrittivo collegamento personalizzato. |
| `pev3` | Nessuno | Non più utilizzato. Tracciati punti cardine nelle versioni precedenti del reporting video. |
| `pf` | Nessuno | bandiera della piattaforma; ad Adobe, solo per uso. Non modificare. |
| `pid` | Nessuno | Identificatore pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `pidt` | Nessuno | Tipo di identificatore della pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Abbreviazione della stringa di query `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabile dei prodotti. Utilizzato nelle dimensioni [Product](/help/components/dimensions/product.md) e [Category](/help/components/dimensions/category.md) . |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Utilizzato per deduplicare gli acquisti. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL di riferimento dell’hit. Utilizzato nelle dimensioni delle origini di traffico, ad esempio [Referrer](/help/components/dimensions/referrer.md) e [Dominio di riferimento](/help/components/dimensions/referring-domain.md) |
| `s` | Nessuno | Risoluzione dello schermo, in `width x height`. Utilizzato nella dimensione [risoluzioni monitor](/help/components/dimensions/monitor-resolution.md). |
| `server` | [`server`](../vars/page-vars/server.md) | [](/help/components/dimensions/server.md) Serverdimension. |
| `sv` | [`server`](../vars/page-vars/server.md) | Abbreviazione della stringa di query `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimensione stato. |
| `t` | Nessuno | Data/ora dell’hit generata. Utilizza il formato `dd/mm/yyyy hh:mm:ss w o`.<br>-  `dd/mm/yyyy hh:mm:ss` è la data/ora in JavaScript. Il mese `0` è gennaio, mentre il mese `11` è dicembre.<br>-  `w` è il giorno della settimana. `0` è domenica, mentre  `6` è sabato.<br>-  `o` è l&#39;offset GMT negativo in minuti. Ad esempio, `420` è GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Il timestamp personalizzato impostato con l&#39;hit. Utilizzato in genere per il tracciamento offline. |
| `v` | Nessuno | Utilizzato nella dimensione [Java enabled](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Dimensione ](/help/components/dimensions/tracking-code.md) codice di tracciamento. |
| `v1` -  `v250` | [`evar1` -  `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md) o dimensioni di conversione personalizzate. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabile ID visitatore. |
| `vmk` | `vmk` | Non più utilizzato. Chiave di migrazione dei visitatori, che ha aiutato a migrare le implementazioni dai cookie di terze parti a quelli di prima parte. |
| `vvp` | `variableProvider` | Utilizzato nei Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Utilizzato con Origini dati per collegare dati online e offline. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Utilizzato nella dimensione [Codice postale](/help/components/dimensions/zip-code.md). |
