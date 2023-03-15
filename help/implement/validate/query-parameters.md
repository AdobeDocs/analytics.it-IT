---
title: Parametri query della raccolta dati
description: Elenca tutti i parametri della stringa di query utilizzati nelle richieste di immagini.
feature: Validation
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
source-git-commit: 74920ff0e518d18697df9aaac8de92e831bb7c03
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 7%

---

# Parametri query della raccolta dati

Nella tabella seguente sono elencati tutti i parametri delle stringhe di query utilizzati dall’Adobe nelle richieste di immagini. Queste informazioni possono essere utilizzate durante il debug con [Analizzatori di pacchetti](packet-monitor.md), quando [richieste di immagini a codifica fissa](../other/hardcoded.md), o quando si utilizza [Variabili dinamiche](../vars/page-vars/dynamic-variables.md).

| Parametro | Variabile di implementazione di Analytics | Descrizione |
| --- | --- | --- |
| `aamlh` | Nessuno | Audience Manager di posizione hint. Utilizzato nell’integrazione di profilo condiviso di Experience Cloud. |
| `aamb` | Nessuno | BLOB Audience Manager. Utilizzato nell’integrazione di profilo condiviso di Experience Cloud. |
| `aid` | Nessuno | ID visitatore di Analytics. |
| `AQB` | Nessuno | Indica l&#39;inizio di una stringa di query di richiesta immagine. |
| `AQE` | Nessuno | Indica la fine di una richiesta di immagine, ovvero che la richiesta non è stata troncata. |
| `bh` | Nessuno | Altezza browser (in pixel). Utilizzato in [Altezza browser](/help/components/dimensions/browser-height.md) dimensione. |
| `bw` | Nessuno | Larghezza browser (in pixel). Utilizzato in [Larghezza browser](/help/components/dimensions/browser-width.md) dimensione. |
| `c` | Nessuno | Qualità del colore (in bit). Utilizzato in [Profondità colore](/help/components/dimensions/color-depth.md) dimensione. |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica l’inizio delle variabili di dati di contesto. Non contiene mai un valore. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica la fine delle variabili di dati di contesto. Non contiene mai un valore. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Proprietà](/help/components/dimensions/prop.md), o variabili di traffico personalizzate. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Tipo di valuta utilizzato nell’hit. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Il numero di periodi in un dominio. Utilizzato per aiutare a memorizzare correttamente i cookie. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Codifica dei caratteri della richiesta di immagine. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Durata del cookie visitatore. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Utilizzato in [Sezioni del sito](/help/components/dimensions/site-section.md) dimensione. |
| `cp` | Nessuno | Utilizzato in [Tipo di hit](/help/components/dimensions/hit-type.md) dimensione. |
| `ct` | Nessuno | Utilizzato in [Tipo di connessione](/help/components/dimensions/connection-type.md) dimensione. |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica cosa utilizzare per le variabili dinamiche. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Mano corta per il `events` stringa di query. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Elenco di eventi separato da virgole sulla pagina. Utilizzato dalla maggior parte [metriche](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | L’URL corrente della pagina, fino a 255 byte. Utilizzato in [URL della pagina](/help/components/dimensions/page-url.md) dimensione. |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Gli URL più lunghi di 255 byte vengono suddivisi. I primi 255 byte vengono visualizzati nel `g` e tutti i byte rimanenti vengono visualizzati nel `-g` parametro. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Mano corta per il `pageName` stringa di query. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Mano corta per il `pageType` stringa di query. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefisso per diverse variabili che rappresentano [Hint client](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensioni gerarchiche. |
| `hp` | Nessuno | Non più utilizzato. Nelle versioni precedenti di Adobe Analytics, determinava se l’URL corrente era la pagina home del browser. |
| `j` | Nessuno | La versione JavaScript installata nel browser. |
| `k` | Nessuno | Utilizzato in [Supporto per cookie](/help/components/dimensions/cookie-support.md) dimensione. |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variabili elenco. |
| `lrt` | Nessuno | L’&quot;ultima tempistica richiesta&quot;, che è la durata del ciclo di andata e ritorno per l’ultima richiesta, in millisecondi. Viene inviato solo quando da una pagina vengono inviate più richieste o quando la pagina è un’applicazione a pagina singola (SPA). |
| `mid` | Nessuno | ID visitatore Experience Cloud. |
| `ndh` | Nessuno | Flag che indica se la richiesta di immagine proviene da AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Consente di determinare dove vengono impostati i cookie. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificatore oggetto per l&#39;ultima pagina. Utilizzato in Activity Map. |
| `ot` | Nessuno | Nome oggetto per l&#39;ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `p` | Nessuno | Non più utilizzato. Elenco dei plug-in utilizzati nel browser. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Utilizzato in [Pagina](/help/components/dimensions/page.md) dimensione. |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Utilizzato in [Pagine non trovate](/help/components/dimensions/pages-not-found.md) dimensione. |
| `pccr` | Nessuno | Impostato solo per i nuovi visitatori e sempre su `true`. Consente di evitare reindirizzamenti infiniti se un visitatore rifiuta i cookie. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determina il tipo di collegamento personalizzato. Obbligatorio per [Collegamenti personalizzati](/help/components/dimensions/custom-link.md), [Collegamenti di download](/help/components/dimensions/download-link.md), e [Collegamenti di uscita](/help/components/dimensions/exit-link.md). |
| `pev1` | Nessuno | L’URL su cui si è verificato il collegamento personalizzato. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Nome descrittivo del collegamento personalizzato. |
| `pev3` | Nessuno | Non più utilizzato. Milestone tracciati nelle versioni precedenti dei rapporti video. |
| `pf` | Nessuno | Flag della piattaforma; solo per Adobe. Non modificare. |
| `pid` | Nessuno | Identificatore della pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `pidt` | Nessuno | Tipo di identificatore della pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Mano corta per il `products` stringa di query. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabile dei prodotti. Utilizzato in [Prodotto](/help/components/dimensions/product.md) e [Categoria](/help/components/dimensions/category.md) dimensioni. |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Utilizzato per deduplicare gli acquisti. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL di riferimento dell’hit. Utilizzato nelle dimensioni delle origini del traffico, ad esempio [Referrer](/help/components/dimensions/referrer.md) e [Dominio di riferimento](/help/components/dimensions/referring-domain.md) |
| `s` | Nessuno | Risoluzione dello schermo, in `width x height`. Utilizzato in [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md) dimensione. |
| `server` | [`server`](../vars/page-vars/server.md) | [Server](/help/components/dimensions/server.md) dimensione. |
| `sv` | [`server`](../vars/page-vars/server.md) | Mano corta per il `server` stringa di query. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimensione stato. |
| `t` | Nessuno | Data/ora generata dell’hit. Utilizza il formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` è data/ora in JavaScript. Mese `0` è gennaio, mentre mese `11` è dicembre.<br>- `w` è il giorno della settimana. `0` è domenica, mentre `6` è sabato.<br>- `o` è lo scostamento GMT negativo in minuti. Ad esempio: `420` è GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | Il timestamp personalizzato impostato con l’hit. Generalmente utilizzato per il tracciamento offline. |
| `v` | Nessuno | Utilizzato in [Java abilitato](/help/components/dimensions/java-enabled.md) dimensione. |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | [Codice di tracciamento](/help/components/dimensions/tracking-code.md) dimensione. |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md), o dimensioni di conversione personalizzate. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabile ID visitatore. |
| `vidn` | Nessuno | Impostato da AppMeasurement per i nuovi visitatori. Contiene il valore ID memorizzato nel cookie visitatore. |
| `vmk` | `vmk` | Non più utilizzato. Chiave di migrazione del visitatore, che ha aiutato a migrare le implementazioni da cookie di terze parti a cookie di prime parti. |
| `vvp` | `variableProvider` | Utilizzato in Data Connectors. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Utilizzato con Origini dati per collegare dati online e offline. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Utilizzato in [Codice postale](/help/components/dimensions/zip-code.md) dimensione. |
