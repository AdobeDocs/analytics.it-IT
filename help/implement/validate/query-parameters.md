---
title: Parametri query della raccolta dati
description: Elenca tutti i parametri della stringa di query utilizzati nelle richieste di immagini.
feature: Implementation Basics
exl-id: 2eb2ade7-a3db-4b00-8a70-2632d1c0aaaf
role: Admin, Developer, Leader, User
TQID: https://experienceleague.adobe.com/aB92GXPxYSkjcDD9wi0vj47jijqndMbOGaECvXs38-Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 7d733a6375f6c6009563bc53f5a3ff090dbc48ed
workflow-type: tm+mt
source-wordcount: 725
ht-degree: 92%

---

# Parametri query della raccolta dati

Nella tabella seguente sono elencati tutti i parametri delle stringhe di query utilizzati da Adobe nelle richieste di immagini. Queste informazioni possono essere utilizzate durante il debug con [Analizzatori di pacchetti](packet-monitor.md), quando si effettuano [richieste di immagini a codifica fissa](../other/hardcoded.md) o quando si utilizzano [Variabili dinamiche](../vars/page-vars/dynamic-variables.md).

| Parametro | Variabile di implementazione di Analytics | Descrizione |
| --- | --- | --- |
| `aamlh` | Nessuno | Hint posizione Audience Manager Utilizzato nell&#39;integrazione di CX Enterprise Shared Profile. |
| `aamb` | Nessuno | Blob di Audience Manager Utilizzato nell&#39;integrazione di CX Enterprise Shared Profile. |
| `aid` | Nessuno | ID visitatore Analytics |
| `AQB` | Nessuno | Indica l’inizio di una stringa di query di richiesta immagine. |
| `AQE` | Nessuno | Indica la fine di una richiesta di immagine, ovvero che la richiesta non è stata troncata. |
| `bh` | Nessuno | Altezza browser (in pixel). Utilizzato nella dimensione [Altezza browser](/help/components/dimensions/browser-height.md). |
| `bw` | Nessuno | Larghezza browser (in pixel). Utilizzato nella dimensione [Larghezza browser](/help/components/dimensions/browser-width.md). |
| `c` | Nessuno | Qualità del colore (in bit). Utilizzato nella dimensione [Profondità colore](/help/components/dimensions/color-depth.md). |
| `c.` | [`contextData`](../vars/page-vars/contextdata.md) | Indica l’inizio delle variabili di dati di contesto. Non contiene mai un valore. |
| `.c` | [`contextData`](../vars/page-vars/contextdata.md) | Indica la fine delle variabili di dati di contesto. Non contiene mai un valore. |
| `c1` - `c75` | [`prop1` - `prop75`](../vars/page-vars/prop.md) | [Prop](/help/components/dimensions/prop.md), o variabili di traffico personalizzate. |
| `cc` | [`currencyCode`](../vars/config-vars/currencycode.md) | Tipo di valuta utilizzato nell’hit. |
| `cdp` | [`cookieDomainPeriods`](../vars/config-vars/cookiedomainperiods.md) | Il numero di periodi in un dominio. Utilizzato per aiutare a memorizzare correttamente i cookie. |
| `ce` | [`charSet`](../vars/config-vars/charset.md) | Codifica dei caratteri della richiesta di immagine. |
| `cl` | [`cookieLifetime`](../vars/config-vars/cookielifetime.md) | Il ciclo di vita dei cookie del visitatore. |
| `ch` | [`channel`](../vars/page-vars/channel.md) | Utilizzato nella dimensione [Sezioni del sito](/help/components/dimensions/site-section.md). |
| `cp` | Nessuno | Utilizzato nella dimensione [Tipo di hit](/help/components/dimensions/hit-type.md). |
| `ct` | Nessuno | Utilizzato nella dimensione [Tipo di connessione](/help/components/dimensions/connection-type.md). |
| `D` | [`dynamicVariablePrefix`](../vars/config-vars/dynamicvariableprefix.md) | Indica cosa utilizzare per le variabili dinamiche. |
| `ev` | [`events`](../vars/page-vars/events/events-overview.md) | Abbreviazione per la stringa di query `events`. |
| `events` | [`events`](../vars/page-vars/events/events-overview.md) | Elenco di eventi separato da virgole sulla pagina. Utilizzato dalla maggior parte delle [metriche](/help/components/metrics/overview.md). |
| `g` | [`pageURL`](../vars/page-vars/pageurl.md) | L’URL corrente della pagina, fino a 255 byte. Utilizzato nella dimensione [URL pagina](/help/components/dimensions/page-url.md). |
| `-g` | [`pageURL`](../../components/dimensions/page-url.md) | Gli URL più lunghi di 255 byte vengono suddivisi. I primi 255 byte vengono visualizzati nel parametro `g` e tutti i byte rimanenti vengono visualizzati nel parametro `-g`. |
| `gn` | [`pageName`](../vars/page-vars/pagename.md) | Abbreviazione per la stringa di query `pageName`. |
| `gt` | [`pageType`](../vars/page-vars/pagetype.md) | Abbreviazione per la stringa di query `pageType`. |
| `h.` | [`collectHighEntropyUserAgentHints`](../vars/config-vars/collecthighentropyuseragenthints.md) | Prefisso per diverse variabili che rappresentano [Hint client](/help/technotes/client-hints.md). |
| `h1` - `h5` | [`hier1` - `hier5`](../vars/page-vars/hier.md) | Dimensioni gerarchiche. |
| `hp` | Nessuno | Non più utilizzato. Nelle versioni precedenti di Adobe Analytics, determinava se l’URL corrente era la pagina home del browser. |
| `j` | Nessuno | La versione JavaScript installata nel browser. |
| `k` | Nessuno | Utilizzata nella dimensione [Supporto cookie](/help/components/dimensions/cookie-support.md). |
| `l1` - `l3` | [`list1` - `list3`](../vars/page-vars/list.md) | Variabili elenco. |
| `lrt` | Nessuno | La “tempistica dell’ultima richiesta”, che è la durata del ciclo di andata e ritorno per l’ultima richiesta, in millisecondi. Viene inviato solo quando da una pagina vengono inviate più richieste o quando la pagina è un’applicazione a pagina singola (SPA). |
| `mid` | Nessuno | ID visitatore di CX Enterprise. |
| `ndh` | Nessuno | Flag che indica se la richiesta di immagine proviene da AppMeasurement. |
| `ns` | [`visitorNameSpace`](../vars/config-vars/visitornamespace.md) | Consente di determinare dove vengono impostati i cookie. |
| `oid` | [`s_objectID`](../vars/page-vars/s-objectid.md) | Identificatore oggetto per l’ultima pagina. Utilizzato in Activity Map. |
| `ot` | Nessuno | Nome oggetto per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `p` | Nessuno | Non più utilizzato. Elenco dei plug-in utilizzati nel browser. |
| `pageName` | [`pageName`](../vars/page-vars/pagename.md) | Utilizzato nella dimensione [Pagina](/help/components/dimensions/page.md). |
| `pageType` | [`pageType`](../vars/page-vars/pagetype.md) | Utilizzato nella dimensione [Pagine non trovate](/help/components/dimensions/pages-not-found.md). |
| `pccr` | Nessuno | Impostato solo per i nuovi visitatori e sempre su `true`. Consente di evitare reindirizzamenti infiniti se un visitatore rifiuta i cookie. |
| `pe` | [`tl()`](../vars/functions/tl-method.md) | Determina il tipo di collegamento personalizzato. Obbligatorio per [Collegamenti personalizzati](/help/components/dimensions/custom-link.md), [Collegamenti download](/help/components/dimensions/download-link.md), e [Collegamenti di uscita](/help/components/dimensions/exit-link.md). |
| `pev1` | [`linkURL`](../vars/config-vars/linkurl.md) | L’URL su cui si è verificato il collegamento personalizzato. |
| `pev2` | [`tl()`](../vars/functions/tl-method.md) | Nome descrittivo del collegamento personalizzato. |
| `pev3` | Nessuno | Non più utilizzato. Attività cardine tracciate nelle versioni precedenti dei rapporti video. |
| `pf` | Nessuno | Flag della piattaforma; solo per Adobe. Non modificare. |
| `pid` | Nessuno | Identificatore della pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `pidt` | Nessuno | Tipo di identificatore della pagina per l’ultima pagina. Utilizzato nelle versioni precedenti di Activity Map. |
| `pl` | [`products`](../vars/page-vars/products.md) | Abbreviazione per la stringa di query `products`. |
| `products` | [`products`](../vars/page-vars/products.md) | Variabile dei prodotti. Utilizzata nelle dimensioni [Prodotto](/help/components/dimensions/product.md) e [Categoria](/help/components/dimensions/category.md). |
| `purchaseID` | [`purchaseID`](../vars/page-vars/purchaseid.md) | Utilizzata per deduplicare gli acquisti. |
| `r` | [`referrer`](../vars/page-vars/referrer.md) | URL di provenienza dell’hit. Utilizzato nelle dimensioni delle origini del traffico, ad esempio [Referrer](/help/components/dimensions/referrer.md) e [Dominio di riferimento](/help/components/dimensions/referring-domain.md) |
| `s` | Nessuno | Risoluzione dello schermo, in `width x height`. Utilizzata nella dimensione [Risoluzione monitor](/help/components/dimensions/monitor-resolution.md) |
| `server` | [`server`](../vars/page-vars/server.md) | Dimensione [server](/help/components/dimensions/server.md). |
| `sv` | [`server`](../vars/page-vars/server.md) | Abbreviazione per la stringa di query `server`. |
| `state` | [`state`](../vars/page-vars/state.md) | Dimensione stato. |
| `t` | Nessuno | Data/ora generata dell’hit. Utilizza il formato `dd/mm/yyyy hh:mm:ss w o`.<br>-`dd/mm/yyyy hh:mm:ss` è data/ora in JavaScript. Il mese `0` è gennaio, mentre il mese `11` è dicembre.<br>-`w` è il giorno della settimana. `0` è domenica, mentre `6` è sabato.<br>- `o` è l&#39;offset GMT negativo in minuti. Ad esempio: `420` è GMT-7. |
| `ts` | [`timestamp`](../vars/page-vars/timestamp.md) | La marca temporale personalizzata impostata con l’hit. Generalmente utilizzata per il tracciamento offline. |
| `v` | Nessuno | Utilizzato nella dimensione [Java abilitato](/help/components/dimensions/java-enabled.md). |
| `v0` | [`campaign`](../vars/page-vars/campaign.md) | Dimensione [Codice di tracciamento](/help/components/dimensions/tracking-code.md). |
| `v1` - `v250` | [`evar1` - `eVar250`](../vars/page-vars/evar.md) | [eVar](/help/components/dimensions/evar.md) o dimensioni di conversione personalizzate. |
| `vid` | [`visitorID`](../vars/config-vars/visitorid.md) | Variabile ID visitatore. |
| `vidn` | Nessuno | Impostato da AppMeasurement per i nuovi visitatori. Contiene il valore ID memorizzato nel cookie visitatore. |
| `vmk` | `vmk` | Non più utilizzato. Chiave di migrazione del visitatore, che ha aiutato a migrare le implementazioni da cookie di terze parti a cookie di prime parti. |
| `vvp` | `variableProvider` | Utilizzato nei connettori dati. |
| `xact` | [`transactionID`](../vars/page-vars/transactionid.md) | Utilizzato con Origini dati per collegare dati online e offline. |
| `zip` | [`zip`](../vars/page-vars/zip.md) | Utilizzato nella dimensione [Codice postale](/help/components/dimensions/zip-code.md). |
