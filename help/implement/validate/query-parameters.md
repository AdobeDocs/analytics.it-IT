---
title: Parametri query della raccolta dati
description: Elenca tutti i parametri della stringa di query utilizzati nelle richieste di immagini.
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Parametri query della raccolta dati

Nella tabella seguente sono elencati tutti i parametri della stringa di query utilizzati da Adobe nelle richieste di immagini. Queste informazioni possono essere utilizzate per il debug con gli analizzatori [di](packet-monitor.md)pacchetti, per la [codifica di richieste](../other/hardcoded.md)di immagini o per l&#39;utilizzo di variabili [](../vars/page-vars/dynamic-variables.md)dinamiche.

| Parametro | Variabile di implementazione di Analytics | Descrizione |
| --- | --- | --- |
| `aamlh` | Nessuno | Suggerimento sulla posizione di Audience Manager. Utilizzata nell&#39;integrazione del profilo condiviso di Experience Cloud. |
| `aamb` | Nessuno | BLOB di Audience Manager. Utilizzata nell&#39;integrazione del profilo condiviso di Experience Cloud. |
| `aid` | Nessuno | ID visitatore di Analytics. |
| `AQB` | Nessuno | Indica l’inizio di una stringa di query per la richiesta di immagini. |
| `AQE` | Nessuno | Indica la fine di una richiesta di immagine, il che significa che la richiesta non è stata troncata. |
| `bh` | Nessuno | Altezza browser (in pixel). Utilizzata nella dimensione Altezza browser. |
| `bw` | Nessuno | Larghezza browser (in pixel). Utilizzata nella dimensione Larghezza browser. |
| `c` | Nessuno | Qualità del colore (in bit). Utilizzata nella dimensione Profondità colore. |
| `c.` | `contextData` | Indica l&#39;inizio delle variabili dei dati di contesto. Non contiene mai un valore. |
| `.c` | `contextData` | Indica la fine delle variabili dei dati contestuali. Non contiene mai un valore. |
| `c1` - `c75` | `prop1` - `prop75` | Variabili di traffico personalizzate. |
| `cc` | `currencyCode` | Il tipo di valuta utilizzata nell&#39;hit. |
| `cdp` | `cookieDomainPeriods` | Numero di periodi in un dominio. Utilizzato per memorizzare correttamente i cookie. |
| `ce` | `charSet` | Codifica dei caratteri della richiesta di immagine. |
| `cl` | `cookieLifetime` | Durata del cookie del visitatore. |
| `ch` | `channel` | Utilizzata nella dimensione Sezioni sito. |
| `cp` | Nessuno | Utilizzata nella dimensione Tipo di hit. |
| `ct` | Nessuno | Utilizzata nella dimensione Tipo di connessione. |
| `D` | `dynamicVariablePrefix` | Indica cosa utilizzare per le variabili dinamiche. |
| `ev` | `events` | Abbreviazione della stringa di `events` query. |
| `events` | `events` | Elenco degli eventi della pagina separati da virgole. |
| `g` | `pageURL` | L&#39;URL corrente della pagina, fino a 255 byte. |
| `-g` | `pageURL` | Gli URL di lunghezza superiore a 255 byte vengono suddivisi. I primi 255 byte vengono visualizzati nel `g` parametro e tutti i byte rimanenti appaiono nel `-g` parametro. |
| `gn` | `pageName` | Abbreviazione della stringa di `pageName` query. |
| `gt` | `pageType` | Abbreviazione della stringa di `pageType` query. |
| `h1` - `h5` | `hier1` - `hier5` | Variabili di gerarchia. |
| `hp` | Nessuno |  Non più utilizzato. Nelle versioni precedenti di Adobe Analytics, veniva determinato se l’URL corrente era la pagina principale del browser. |
| `j` | Nessuno | La versione JavaScript installata nel browser. |
| `k` | Nessuno | Utilizzata nella dimensione Cookie Support. |
| `l1` - `l3` | `list1` - `list3` | Elenca le variabili. |
| `mid` | Nessuno | ID visitatore Experience Cloud. |
| `ndh` | Nessuno | Flag che indica se la richiesta di immagine è nata da AppMeasurement. |
| `ns` | `visitorNameSpace` | Consente di determinare dove vengono impostati i cookie. |
| `oid` | `objectID` | Identificatore oggetto per l’ultima pagina. Utilizzata in Activity Map. |
| `ot` | Nessuno | Nome oggetto per l’ultima pagina. Utilizzata nelle versioni precedenti di Activity Map. |
| `p` | Nessuno |  Non più utilizzato. Elenco dei plug-in utilizzati nel browser. |
| `pageName` | `pageName` | Utilizzata nella dimensione Pagina. |
| `pageType` | `pageType` | Utilizzata nella dimensione Pagine non trovate. |
| `pccr` | Nessuno | Impostato solo per i nuovi visitatori e impostato sempre su `true`. Impedisce reindirizzamenti infiniti. |
| `pe` | `linkType` | Determina il tipo di collegamento personalizzato. |
| `pev1` | Nessuno | L&#39;URL su cui si è verificato il collegamento personalizzato. |
| `pev2` | Nessuno | Nome descrittivo del collegamento personalizzato. |
| `pev3` | Nessuno |  Non più utilizzato. Elementi cardine tracciati nelle versioni precedenti del reporting video. |
| `pf` | Nessuno | bandiera della piattaforma; solo per Adobe. Non modificare. |
| `pid` | Nessuno | Identificatore pagina per l’ultima pagina. Utilizzata nelle versioni precedenti di Activity Map. |
| `pidt` | Nessuno | Identificatore pagina per l’ultima pagina. Utilizzata nelle versioni precedenti di Activity Map. |
| `pl` | `products` | Abbreviazione della stringa di `products` query. |
| `products` | `products` | Variabile dei prodotti. |
| `purchaseID` | `purchaseID` | Utilizzato per deduplicare gli acquisti. |
| `r` | `referrer` | URL di riferimento dell’hit. |
| `s` | Nessuno | Utilizzata nella dimensione Risoluzione monitor. Risoluzione dello schermo, in `width x height`. |
| `server` | `server` | Dimensione server. |
| `sv` | `server` | Abbreviazione della stringa di `server` query. |
| `state` | `state` | Dimensione stato. |
| `t` | Nessuno | Data/ora generata dell’hit. Utilizza il formato `dd/mm/yyyy hh:mm:ss w o`.<br>- `dd/mm/yyyy hh:mm:ss` è data/ora in JavaScript. Il mese `0` è gennaio, mentre il mese `11` è dicembre.<br>- `w` è il giorno della settimana. `0` è domenica, mentre `6` è sabato.<br>- `o` è l&#39;offset GMT negativo in minuti. Ad esempio, `420` è GMT-7. |
| `ts` | `timestamp` | Set di marche temporali personalizzate con l’hit. Generalmente utilizzato per il tracciamento offline. |
| `v` | Nessuno | Utilizzata nella dimensione Java Enabled. |
| `v0` | `campaign` | Dimensione Codice di tracciamento. |
| `v1` - `v250` | `evar1` - `eVar250` | Dimensioni di conversione personalizzate. |
| `vid` | `visitorID` | Variabile ID visitatore. |
| `vmk` | `vmk` |  Non più utilizzato. È stata facilitata la migrazione dai cookie di terze parti a quelli di prime parti. |
| `vvp` | `variableProvider` | Utilizzata nei connettori dati. |
| `xact` | `transactionID` | Utilizzato con Origini dati per collegare i dati. |
| `zip` | `zip` | Utilizzata nella dimensione Codice postale. |
