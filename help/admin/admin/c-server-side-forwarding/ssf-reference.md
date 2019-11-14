---
description: Un elenco completo e una descrizione delle variabili di configurazione, delle intestazioni HTTP e dei segnali di dati nelle chiamate di inoltro lato server.
title: Dati inoltri lato server e riferimento al codice
uuid: 3eb3ea0f-a530-448d-bba5-6408b2490dc8
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Dati inoltri lato server e riferimento al codice

Un elenco completo e una descrizione delle variabili di configurazione, delle intestazioni HTTP e dei segnali di dati nelle chiamate di inoltro lato server.

## Variabili di configurazione {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parametri con prefisso per `d_*` identificare coppie chiave-valore a livello di sistema speciali utilizzate dai nostri server [di raccolta](https://marketing.adobe.com/resources/help/en_US/aam/c_compcollect.html) dati (DCS). Consultate anche Attributi [supportati per le chiamate](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html)API DCS.

| Parametro | Descrizione |
|--- |--- |
| d_rs | (Ottiene l'impostazione con l'inoltro lato server legacy/di tracciamento) <br>Impostato sulle suite di rapporti passate con l'hit in Analytics. |
| d_dst_filter | (Ottiene l'impostazione con l'inoltro lato server basato su suite di rapporti) <br>Impostato sugli ID suite di rapporti passati con l'hit ad Analytics. |
| d_dst | Impostate d_dst=1 <br>se la richiesta ad Analytics è in attesa che il contenuto della destinazione venga restituito al client. |
| d_mid | L’ID Experience Cloud passato ad Analytics. |

## Intestazioni HTTP {#section_0549705E76004F9585224AEF872066C0}

Queste intestazioni sono campi che contengono informazioni come richieste di dati e risposte in una chiamata HTTP.

<!-- Meike, missing link in table below: "See Understanding Calls to the Demdex Domain" -->

| Intestazione HTTP | Descrizione |
|--- |--- |
| Host | Questo è impostato sul nome host di raccolta dati specifico del client specificato nel file di configurazione dell'host di Analytics. Viene visualizzato come `host name .demdex.net` .  Vedi Informazioni sulle chiamate al dominio demdex . |
| Agente utente | Impostato sull’intestazione Agente utente passata ad Analytics. |
| X-Original-User-Agent | Impostato solo se un agente utente alternativo è stato specificato da una delle seguenti intestazioni: </br>`X-Device-User-Agent\ `  </br>`X-Original-User-Agent\`   </br>`X-OperaMini-Phone-UA\`   </br>`X-Skyfire-Phone\`    </br>`X-Bolt-Phone-UA\` |
| X-Forwarded-For | Impostate l'indirizzo IP del client richiedente. Analytics avrà già analizzato l’ `X-Forwarded-For` intestazione in entrata e determinato l’indirizzo IP corretto da utilizzare. |
| Accept-Language | Impostato sull’ `Accept-Language` intestazione passata ad Analytics. |
| Referente | Impostato sull’URL della pagina passato ad Analytics o raccolto dall’intestazione Referente passato ad Analytics. |

## Segnali definiti dal cliente {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parametri con prefisso per `c_` identificare le variabili definite dal cliente. Consultate anche Attributi [supportati per le chiamate](https://marketing.adobe.com/resources/help/en_US/aam/dcs-keys.html)API DCS.

| Segnale | Descrizione |
|--- |--- |
| c_browserWidth e c_browserHeight | Larghezza e altezza della finestra del browser. |
| c_campaign | Impostato da s.campaign. |
| c_channel | Impostato da s.channel. |
| c_clientDateTime | Timestamp formattato come gg/mm/aaaa hh:mm:ss W TZ.    TZ è espresso in minuti e corrisponde al valore restituito dal metodo Date.getTimezoneOffset. |
| c_colorDepth | Specificato come colore a 16 o 32 bit. |
| c_connectionType | Specifica il tipo di connessione. Le opzioni includono:<ul><li>modem</li><li>lan</li></ul> |
| c_contextData.* | Esempi:<ul><li>AppMeasurement: s.contextData</li><li>["category"] = "news";</li><li>Segnale:  c_contextData.category=news</li></ul> |
| c_cookiesEnabled | Specifica se i cookie possono essere attivati. Le opzioni includono: sì, no, sconosciuto |
| c_currencyCode | Tipo di valuta utilizzata per la transazione. |
| c_evar# | Evar personalizzati |
| c_events | Impostato da s.events. |
| c_hier# | Variabili della gerarchia personalizzata. |
| c_javaEnabled | Specifica se Java può essere abilitato. Le opzioni includono: sì, no, sconosciuto |
| c_javaScriptVersion | Versione di JavaScript supportata da un browser. |
| c_latitude | Latitudine numerica |
| c_linkClick | Le opzioni includono: custom, download exit |
| c_linkCustomName | Il nome personalizzato (se presente) fornito per il collegamento. |
| c_linkDownloadURL | URL dei collegamenti di download. |
| c_linkExitURL | L’URL del collegamento di uscita. |
| c_list# | Variabili elenco personalizzate. |
| c_longitude | longitudine numerica. |
| c_mediaPlayerType | Per richieste di tracciamento del flusso multimediale. Le opzioni includono:  altro, primetime |
| c_pageName | Il nome della pagina (se impostato). |
| c_pageURL | Indirizzo della pagina nella barra degli indirizzi del browser. |
| c_products | Stringa del prodotto (impostata da s.products ). |
| c_prop | Proprietà personalizzate. |
| c_purchaseID | Un ID univoco per l'acquisto. |
| c_referrer | La pagina precedente a quella corrente. |
| c_screenResolution | Larghezza e altezza dello schermo (in pixel). |
| c_server | Nome server Web (impostato da s.server). |
| c_state | Area geografica (impostata da s.state). |
| c_timezone | Offset tempo (in ore). |
| c_transactionID | Un ID univoco per una transazione. |
| c_zip | Codice postale (impostato da s.zip). |
