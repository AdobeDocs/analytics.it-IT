---
description: Esistono ulteriori requisiti e configurazioni per implementare Analytics senza javascript.
keywords: Implementazione di Analytics; distinzione tra maiuscole e minuscole; parametri di query di codifica; caratteri non validi; richieste di immagini sicure; lunghezza variabile massima; riferimento; url; memorizzazione nella cache; namespace
seo-description: Esistono ulteriori requisiti e configurazioni per implementare Analytics senza javascript.
seo-title: Implementazione senza linee guida javascript
solution: Analytics
title: Implementazione senza linee guida javascript
topic: Sviluppatore e implementazione
uuid: c 672 dd 63-1 c 74-4 f 66-8992-9257 c 5 a 75 e 36
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Implementazione senza linee guida javascript

Esistono ulteriori requisiti e configurazioni per implementare Analytics senza javascript.

Puoi visualizzare il codice di esempio per comprendere ulteriormente l'implementazione. Le informazioni seguenti delineano i requisiti e le configurazioni aggiuntive:

<!--Meike, I converted this from a table. Table within a table was a mess, and I'm not sure I captured everything. Please check this content against the orginal. -Bob -->

**Distinzione tra maiuscole e minuscole**

The parameter names (`pageName`, `purchaseID`, and so forth) are case-sensitive and will not properly record data unless they appear as designated in the table displayed in [Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md).

**Parametri di query codificati**

I valori per ciascuno dei parametri della stringa query devono essere codificati dall'URL. URL encoding converts characters that are normally illegal when appearing in a query string, such as a space character, into an encoded character beginning with `%`. For example, a space character is converted into `%20`.

La versione javascript di questa funzione è chiamata escape (e per decodificare, annullare la unescape). Microsoft IIS versione 5.0 include anche una funzione Esc e Unescape per le stringhe di query. Altri linguaggi di script del server Web offrono anche utilità di codifica/decodifica.

**Lunghezza massima variabile**

Ciascuna variabile ha una lunghezza massima. This length is specified for each variable in [Analytics Variables](../../../implement/js-implementation/c-variables/sc-variables.md). Il superamento della lunghezza massima di una variabile determina il troncamento del valore di questa variabile per l'archiviazione e la visualizzazione in Analytics.

**Caratteri non validi**

I caratteri con codici di caratteri superiori a decimali 128 non sono validi, così come i codici di caratteri non stampabili inferiori a 128. Anche la formattazione HTML (" &lt; h 1 &gt;") non è valida, come marchi, marchi registrati e simboli di copyright.

**Protetto (&lt; https: &gt; vs. Non-Secure (&lt; http: &gt;) Richieste di immagini**

Nelle pagine accessibili tramite https (protocollo protetto), la porzione URL della richiesta di immagine cambia in modo da contenere un set diverso di server di raccolta dati.

Le informazioni seguenti illustrano i diversi URL utilizzati per richieste di immagini sicure e non sicure.

* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe utilizza diversi centri dati ed è necessario implementare l'URL corretto nell'organizzazione. Tutti i codici scaricati da Admin Console all'interno dell'account della società presentano automaticamente il centro dati corretto. Potrebbe essere necessario correggere il codice fornito da origini esterne per indirizzarlo al centro dati corretto.
* Per i clienti che utilizzano più suite di rapporti, devono essere elencati solo nella sezione della directory e non nella sezione del dominio dell'URL, come illustrato di seguito.
* The `*` in the URL above denotes a data-center specific URL that is provided to you by your Adobe Consultant. Adobe utilizza diversi centri dati ed è necessario implementare l'URL corretto a cui è stata assegnata l'organizzazione.

**URL e URL di provenienza**

The URL and Referring URL may be populated from the server in the `g=` and `r=` variables. Use the Request ServerVariables (`HTTP\_REFERRER`) or Request ServerVariables `(URL) (IIS/ASP)`, or the appropriate variable for your server/scripting technology. The referring URL `( r=)` is extremely important for tracking referring URLs, domains, search engines, and search terms.

Se pagename non viene utilizzato, è necessario che il campo URL corrente sia compilato in modo univoco. If neither pageName nor Current URL `(g=)` is populated, the record is invalid and is not processed. Come minimo, l'URL è un campo obbligatorio per l'elaborazione del record.

**Effetti del caching**

HTML e altre pagine Web possono essere memorizzate nella cache da browser o server tra il visitatore e il sito Web che distribuisce il contenuto. La memorizzazione nella cache impedisce un conteggio accurato delle visualizzazioni di pagina e di altri eventi, a meno che non venga impiegata una tecnica "cache-broken".

Javascript standard di Adobe include un metodo dinamico di modifica della richiesta di immagini per evitare la cache delle pagine e delle immagini, consentendo un conteggio accurato delle visualizzazioni di pagina.

Tuttavia, durante la creazione di una richiesta di immagine lato server, tale randomizzazione non viene eseguita. I ricarici delle pagine e le pagine memorizzate nella cache (nella cache del browser o in un server proxy) non vengono conteggiati in alcuni casi quando si utilizzano richieste di immagini lato server.

SSL (`https:`) pages are not, by definition, ever cached so this warning applies only to non-secure (`http:`) pages. Additionally, pages with parameters (`https://www.samplesite.com/page.asp?parameter=1`) or certain file extensions (`.asp`, `.jsp`, etc.) non sono memorizzate nella cache.

Gli esempi seguenti illustrano anche una soluzione javascript minima che assembla principalmente la richiesta di immagine lato server e tattica su un numero casuale nel browser. Questo metodo sostituisce il caching che si verifica in caso contrario sulle pagine HTML statiche a cui si accede tramite https: protocollo.

**Variabile namespace**

Per le implementazioni non javascript è necessario il parametro della stringa query namespace.

Esempio: ns = namespace

Contattate il vostro Adobe Consulente o Account Manager per ottenere il valore namespace dell'organizzazione.
