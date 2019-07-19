---
description: Un elenco completo e descrizioni delle variabili di configurazione, delle intestazioni HTTP e dei segnali dati nelle chiamate di inoltro lato server.
seo-description: Un elenco completo e descrizioni delle variabili di configurazione, delle intestazioni HTTP e dei segnali dati nelle chiamate di inoltro lato server.
seo-title: Dati inoltri lato server e riferimento a un codice
title: Dati inoltri lato server e riferimento a un codice
uuid: 3 eb 3 ea 0 f-a 530-448 d-bba 5-6408 b 2490 dc 8
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Dati inoltri lato server e riferimento a un codice

Un elenco completo e descrizioni delle variabili di configurazione, delle intestazioni HTTP e dei segnali dati nelle chiamate di inoltro lato server.

## Variabili di configurazione {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parameters prefixed with `d_*` identify special, system-level key-value pairs used by our [data collection servers](https://marketing.adobe.com/resources/help/en_US/aam/c_compcollect.html) (DCS). See also [Supported Attributes for DCS API calls](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

| Parametro | Descrizione |
|--- |--- |
| d_ rs | (Gets set with legacy/tracking-server-based server-side forwarding) <br>Set to the report suites passed in with the hit to Analytics. |
| d_ dst_ filter | (Gets set with report-suite-based server-side forwarding)  <br>Set to the report suite IDs passed in with the hit to Analytics. |
| d_ dst | Set  d_dst=1  <br>if the request to Analytics is expecting content about the destination to be sent back to the client. |
| d_mid | L'ID Experience Cloud passato ad Analytics. |

## HTTP Headers {#section_0549705E76004F9585224AEF872066C0}

Tali intestazioni contengono informazioni come richieste di dati e risposte in una chiamata HTTP.

<!-- Meike, missing link in table below: "See Understanding Calls to the Demdex Domain" -->

| Intestazione HTTP | Descrizione |
|--- |--- |
| Host | Viene impostato sul nome host della raccolta dati del client specificato nel file di configurazione host di Analytics. It appears as   `host name .demdex.net` .  Vedi Informazioni sulle chiamate al dominio demdex . |
| Agente utente | Impostare sull'intestazione Agente utente trasmesso ad Analytics. |
| X-Original-User-Agent | Only set if an alternate user agent was specified by one of these headers: </br>`X-Device-User-Agent\ `  </br>`X-Original-User-Agent\`   </br>`X-OperaMini-Phone-UA\`   </br>`X-Skyfire-Phone\`    </br>`X-Bolt-Phone-UA\` |
| X-inoltr@-@ for | Impostare l'indirizzo IP del client richiedente. Analytics will have already parsed the incoming  `X-Forwarded-For`  header and determined the correct IP address to use. |
| Accept-Language | Set to the  `Accept-Language`  header passed in to Analytics. |
| Referente | Imposta l'URL della pagina trasmesso ad Analytics o raccolto dall'intestazione Referer passata ad Analytics. |

## Customer-Defined Signals {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parameters prefixed with `c_` identify customer-defined variables. See also [Supported Attributes for DCS API Calls](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html).

| Segnale | Descrizione |
|--- |--- |
| c_ browserwidth e c_ browserheight | Larghezza e altezza della finestra del browser. |
| c_ campaign | Impostato per s. campaign. |
| c_ channel | Impostato da s. channel. |
| c_ clientdatetime | Timestamp formattato come gg/mm/aaaa hh: mm: ss W TZ. TZ è in minuti e corrisponde al ritorno del metodo Date. gettimezoneoffset. |
| c_ colordepth | Specificato come colore a 16 o 32 bit. |
| c_ connectiontype | Specifica il tipo di connessione. Le opzioni includono:<ul><li>modem</li><li>lan</li></ul> |
| c_ contextdata.* | Esempi:<ul><li>Appmeasurement: s. contextdata</li><li>[" category "] =" news ";</li><li>Segnale: c_ contextdata. category = news</li></ul> |
| c_ cookiesenabled | Specifica se i cookie possono essere abilitati. Le opzioni includono: yes, no, unknown |
| c_ currencycode | Tipo di valuta utilizzata per la transazione. |
| c_ evar # | Variabili evar personalizzate |
| c_ events | Impostato per s. events. |
| c_ hier # | Variabili gerarchiche personalizzate. |
| c_ javaenabled | Specifica se è possibile abilitare Java. Le opzioni includono: yes, no, unknown |
| c_ javascriptversion | Versione di javascript supportata da un browser. |
| c_ latitude | Latitudine numerica |
| c_ linkclick | Le opzioni includono: custom, download exit |
| c_ linkcustomname | Eventuale nome personalizzato fornito per il collegamento. |
| c_ linkdownloadurl | L'URL dei collegamenti di download. |
| c_ linkexiturl | L'URL di collegamento uscita. |
| c_ list # | Variabili elenco personalizzate. |
| c_ longitude | Longitudine numerica. |
| c_ mediaplayertype | Per richieste di tracciamento flussi multimediali. Le opzioni includono: other, primetime |
| c_ pagename | Il nome della pagina (se impostato). |
| c_ pageurl | L'indirizzo della pagina nella barra degli indirizzi del browser. |
| c_ products | Stringa di prodotto (impostata da s. products). |
| c_ prop | Proprietà personalizzate. |
| c_ purchaseid | ID univoco per l'acquisto. |
| c_ referrer | Pagina prima della pagina corrente. |
| c_ screenresolution | Larghezza e altezza dello schermo (in pixel). |
| c_ server | Nome server Web (impostato da s. server). |
| c_ state | Area geografica (impostata da s. state). |
| c_ timezone | Offset tempo (in ore). |
| c_ transactionid | Un ID univoco per una transazione. |
| c_ zip | Codice postale (impostato da s.zip). |
