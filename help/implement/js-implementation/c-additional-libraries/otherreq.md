---
description: Esistono requisiti e configurazioni aggiuntivi per implementare Analytics senza JavaScript.
keywords: Implementazione di Analytics;distinzione tra maiuscole e minuscole;parametri di query di codifica;caratteri non validi;richieste di immagini protette;lunghezza massima della variabile;riferimento;url;caching;namespace
seo-description: Esistono requisiti e configurazioni aggiuntivi per implementare Analytics senza JavaScript.
seo-title: Implementazione senza linee guida JavaScript
solution: Analytics
title: Implementazione senza linee guida JavaScript
topic: Sviluppatore e implementazione
uuid: c672dd63-1c74-4f66-8992-9257c5a75e36
translation-type: tm+mt
source-git-commit: 757cea821bae49fabe819a65b921797070d328fc

---


# Implementazione senza linee guida JavaScript

Esistono requisiti e configurazioni aggiuntivi per implementare Analytics senza JavaScript.

Potete visualizzare il codice di esempio per comprendere meglio l'implementazione. Le seguenti informazioni descrivono i requisiti e le configurazioni aggiuntivi:

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Distinzione tra maiuscole e minuscole**

I nomi dei parametri (`pageName`, `purchaseID`e così via) sono con distinzione tra maiuscole e minuscole e non registrano correttamente i dati a meno che non vengano visualizzati come indicato nella tabella visualizzata in Parametri [](/help/implement/js-implementation/data-collection/query-parameters.md)query.

**Codifica parametri query**

I valori per ciascuno dei parametri della stringa di query devono essere codificati nell’URL. La codifica URL converte i caratteri normalmente non validi quando vengono visualizzati in una stringa di query, ad esempio un carattere spazio, in un carattere codificato che inizia con `%`. Ad esempio, un carattere spazio viene convertito in `%20`.

La versione JavaScript di questa funzione è denominata escape (e per decodificare, unescape). Microsoft IIS versione 5.0 include anche una funzione Escape e Unescape per la codifica delle stringhe di query. Altri linguaggi di script del server Web forniscono anche utility di codifica/decodifica.

**Lunghezza massima variabile**

Ogni variabile ha una lunghezza massima. Questa lunghezza è specificata per ogni variabile in Variabili [](/help/implement/js-implementation/c-variables/sc-variables.md)Analytics. Se si supera la lunghezza massima per una variabile, il valore di questa variabile viene troncato per l'archiviazione e la visualizzazione in Analytics.

**Caratteri non validi**

I caratteri con codici di carattere al di sopra della cifra decimale 128 non sono validi, così come i codici di carattere non stampabili al di sotto di 128. Anche la formattazione HTML ("&lt;h1&gt;") non è valida, così come i simboli di marchio, marchio registrato e copyright.

**Richieste di immagini sicure (&lt;https:&gt; e non sicure (&lt;http:&gt;)**

Nelle pagine a cui si accede tramite https (protocollo sicuro), la parte URL della richiesta di immagine viene modificata per contenere un set diverso di server di raccolta dati.

Le informazioni seguenti illustrano i diversi URL utilizzati per le richieste di immagini sicure e non sicure.

* L’URL `*` riportato sopra indica un URL specifico per il centro dati fornito dal consulente Adobe. Adobe utilizza diversi data center ed è necessario implementare l’URL corretto assegnato alla tua organizzazione. Per qualsiasi codice scaricato da Admin Console all'interno dell'account aziendale, viene automaticamente fornito il centro dati corretto. Il codice fornito da fonti esterne potrebbe dover essere corretto per puntare al centro dati corretto.
* Per i client che utilizzano più suite di rapporti, devono essere elencati solo nella sezione directory, e non nella sezione dominio dell'URL, come mostrato di seguito.
* L’URL `*` riportato sopra indica un URL specifico per il centro dati fornito dal consulente Adobe. Adobe utilizza diversi data center ed è necessario implementare l'URL corretto al quale è stata assegnata la tua organizzazione.

**URL e URL di riferimento**

L’URL e l’URL di riferimento possono essere popolati dal server nelle `g=` variabili e `r=` . Utilizzare Request ServerVariables (`HTTP\_REFERRER`) o Request ServerVariables `(URL) (IIS/ASP)`, oppure la variabile appropriata per la tecnologia server/script. L’URL di provenienza `( r=)` è estremamente importante per tenere traccia degli URL di provenienza, dei domini, dei motori di ricerca e dei termini di ricerca.

Se pageName non viene utilizzato, è fondamentale che il campo URL corrente sia popolato in modo univoco. Se né pageName né Current URL `(g=)` vengono compilati, il record non è valido e non viene elaborato. Come minimo, l'URL è un campo obbligatorio per l'elaborazione del record.

**Effetti della cache**

HTML e altre pagine Web possono essere memorizzate nella cache da browser o server che si trovano tra il visitatore e il sito Web che distribuisce il contenuto. La memorizzazione nella cache impedisce un conteggio accurato delle visualizzazioni di pagina e di altri eventi a meno che non venga utilizzata una tecnica di "cache-busting".

Il codice JavaScript standard di Adobe include un metodo dinamico per modificare la richiesta di immagine per evitare il caching delle pagine e delle immagini, consentendo un conteggio accurato delle visualizzazioni delle pagine.

Tuttavia, durante la creazione di una richiesta di immagine sul lato server, questa randomizzazione non si verifica. I ricarichi di pagina e le pagine memorizzate nella cache (nella cache del browser o in un server proxy) non vengono conteggiati in alcuni casi quando si utilizzano richieste di immagini sul lato server.

SSL (`https:`) le pagine non sono, per definizione, mai memorizzate nella cache, pertanto questo avviso si applica solo alle pagine non sicure (`http:`). Inoltre, pagine con parametri (`https://www.samplesite.com/page.asp?parameter=1`) o determinate estensioni di file (`.asp`, `.jsp`ecc.) non vengono memorizzate nella cache.

Gli esempi seguenti illustrano anche una soluzione JavaScript minima che assembla principalmente il lato server della richiesta di immagini e che effettua il tocco su un numero casuale nel browser. Questo metodo supera il caching che altrimenti si verificava sulle pagine HTML statiche a cui si accedeva tramite https: protocollo.

**nameSpace, variabile**

Il parametro della stringa di query nameSpace è richiesto per le implementazioni non JavaScript.

Esempio: ns=nameSpace

Contatta il tuo consulente Adobe o l'Account Manager per ottenere il valore nameSpace della tua organizzazione.
