---
description: Elenco completo e descrizioni delle variabili di configurazione, intestazioni HTTP e segnali di dati nelle chiamate di inoltro lato server.
title: Dati inoltri lato server e riferimento al codice
uuid: 3eb3ea0f-a530-448d-bba5-6408b2490dc8
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
source-git-commit: f1e1a30e29faab66995b683acbf6748aeeec91fc
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 11%

---

# Dati inoltri lato server e riferimento al codice

Elenco completo e descrizioni delle variabili di configurazione, intestazioni HTTP e segnali di dati nelle chiamate di inoltro lato server.

## Variabili di configurazione {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

Parametri con prefisso `d_*` identificare coppie chiave-valore speciali a livello di sistema utilizzate dal nostro [server di raccolta dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=it) (DCS). Vedi anche [Attributi supportati per le chiamate API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=it).

| Parametro | Descrizione |
|--- |--- |
| d_rs | (viene impostato con inoltro lato server legacy/basato su server) <br>Imposta sulle suite di rapporti passate con l&#39;hit in Analytics. |
| d_dst_filter | (viene impostato con inoltro lato server basato su suite di rapporti)  <br>Imposta gli ID suite di rapporti passati con l&#39;hit in Analytics. |
| d_dst | Imposta d_dst=1  <br>se la richiesta ad Analytics prevede che il contenuto della destinazione venga rimandato al client. |
| d_mid | L&#39;ID Experience Cloud passato ad Analytics. |

## Intestazioni HTTP {#section_0549705E76004F9585224AEF872066C0}

Queste intestazioni sono campi che contengono informazioni come richieste di dati e risposte in una chiamata HTTP.

| Intestazione HTTP | Descrizione | h_ chiavi accettate dall&#39;Audience Manager |
| --- | --- | --- |
| Host | Questo è impostato sul nome host specifico del client di raccolta dati specificato nel file di configurazione host di Analytics. Viene visualizzato come `host name .demdex.net`. Vedi [Informazioni sulle chiamate al dominio demdex](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=it). | `h_host` |
| Utente-agente | Imposta l&#39;intestazione Utente-Agente passata ad Analytics. | `h_user-agent` |
| Accept-Language | Imposta su  `Accept-Language`  intestazione trasmessa ad Analytics. | `h_accept-language` |
| Referer | Impostato sull&#39;URL della pagina passato ad Analytics o raccolto dal `Referer` intestazione trasmessa ad Analytics. | `h_referer` |
| Referrer | Impostato sull&#39;URL della pagina passato ad Analytics o raccolto dal `Referrer` intestazione trasmessa ad Analytics. | `h_referrer` |
| IP | Segnale generato dall’IP dell’host che invia la richiesta al DCS. | `h_ip` |

## Segnali definiti dal cliente {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

Parametri con prefisso `c_` identificare le variabili definite dal cliente. Vedi anche [Attributi supportati per le chiamate API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Segnale | Descrizione |
|--- |--- |
| c_browserWidth e c_browserHeight | Larghezza e altezza della finestra del browser. |
| c_campaign | Impostato da s.campaign . |
| c_channel | Impostato da s.channel . |
| c_clientDateTime | Timestamp formattato come gg/mm/aaaa hh:mm:ss W TZ .    Il valore TZ è espresso in minuti e corrisponde al valore restituito dal metodo Date.getTimezoneOffset. |
| c_colorDepth | Specificato come colore a 16 o 32 bit. |
| c_connectionType | Specifica il tipo di connessione. Le opzioni includono:<ul><li>modem</li><li>lan</li></ul> |
| c_contextData.* | Esempi:<ul><li>AppMeasurement: s.contextData</li><li>[&quot;categoria&quot;] = &quot;news&quot;;</li><li>Segnale: c_contextData.category=news</li></ul> |
| c_cookiesEnabled | Specifica se i cookie possono essere abilitati. Le opzioni includono: sì, no, sconosciuto |
| c_currencyCode | Tipo di valuta utilizzata per la transazione. |
| c_evar# | Evar personalizzati |
| c_events | Impostato da s.events . |
| c_hier# | Variabili di gerarchia personalizzate. |
| c_javaEnabled | Specifica se Java può essere abilitato. Le opzioni includono: sì, no, sconosciuto |
| c_javaScriptVersion | Versione di JavaScript supportata da un browser. |
| c_latitude | Latitudine numerica |
| c_linkClick | Le opzioni includono: custom, download exit |
| c_linkCustomName | Nome personalizzato (se presente) fornito per il collegamento. |
| c_linkDownloadURL | URL dei collegamenti per il download. |
| c_linkExitURL | URL del collegamento di uscita. |
| c_list# | Variabili elenco personalizzate. |
| c_longitude | longitudine numerica. |
| c_mediaPlayerType | Per richieste di tracciamento del flusso multimediale. Le opzioni includono: altro, primetime |
| c_pageName | Nome della pagina (se impostato). |
| c_pageURL | Indirizzo della pagina nella barra degli indirizzi del browser. |
| c_products | La stringa di prodotto (impostata da s.products ). |
| c_prop | Proprietà personalizzate. |
| c_purchaseID | Un ID univoco per l&#39;acquisto. |
| c_referrer | La pagina precedente alla pagina corrente. |
| c_screenResolution | Larghezza e altezza dello schermo (in pixel). |
| c_server | Nome del server Web (impostato da s.server ). |
| c_state | Area geografica (impostata da s.state ). |
| c_timezone | Offset tempo (in ore). |
| c_transactionID | Un ID univoco per una transazione. |
| c_zip | Codice postale (impostato da s.zip ). |
