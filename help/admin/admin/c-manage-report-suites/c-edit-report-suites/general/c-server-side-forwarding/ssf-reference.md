---
description: Elenco completo e descrizioni delle variabili di configurazione, intestazioni HTTP e segnali di dati nelle chiamate di inoltro lato server.
title: Dati inoltro lato server e codice
feature: Server-Side Forwarding
exl-id: 6ab7bbb6-0709-427b-b9fa-a179dbe55fc9
source-git-commit: a17297af84e1f5e7fe61f886eb3906c462229087
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 100%

---

# Dati inoltro lato server e codice

Elenco completo e descrizioni delle variabili di configurazione, intestazioni HTTP e segnali di dati nelle chiamate di inoltro lato server.

## Variabili di configurazione {#section_AD402B5EB9B24BF3B2039DA80FCA901E}

I parametri con prefisso `d_*` identificano specifiche coppie chiave-valore a livello di sistema utilizzate dai [server di raccolta dati](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/system-components/components-data-collection.html?lang=it) (DCS, data colelction servers). Vedi anche [Attributi supportati per le chiamate API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html?lang=it).

| Parametro | Descrizione |
|--- |--- |
| `d_rs` | Viene impostato con inoltro lato server legacy/basato su server di tracciamento <br>Impostato sulle suite di rapporti passate con l’hit in Analytics. |
| `d_dst_filter` | Viene impostato con inoltro lato server basato su suite di rapporti <br>Impostato sugli ID suite di rapporti passati con l’hit in Analytics. |
| `d_dst` | Imposta `d_dst=1` <br>se la richiesta ad Analytics prevede che il contenuto della destinazione venga rimandato al client. |
| `d_mid` | ID di Experience Cloud passato ad Analytics. |

## Intestazioni HTTP {#section_0549705E76004F9585224AEF872066C0}

Queste intestazioni sono campi che contengono informazioni come richieste di dati e risposte in una chiamata HTTP.

| Intestazione HTTP | Descrizione | h_ key accettata da Audience Manager |
| --- | --- | --- |
| Host | Questo è impostato sul nome host specifico del client di raccolta dati specificato nel file di configurazione host di Analytics. Viene visualizzato come `host name .demdex.net`. Consulta [Informazioni sulle chiamate al dominio demdex](https://experienceleague.adobe.com/docs/audience-manager/user-guide/reference/demdex-calls.html?lang=it). | `h_host` |
| User-Agent | Impostato sull’intestazione Utente-agente passata ad Analytics. | `h_user-agent` |
| Accept-Language | Impostato sull’intestazione `Accept-Language` trasmessa ad Analytics. | `h_accept-language` |
| Referer | Impostato sull’URL della pagina passato ad Analytics o raccolto dall’intestazione `Referer` trasmessa ad Analytics. | `h_referer` |
| Destinatario che inoltra | Impostato sull’URL della pagina passato ad Analytics o raccolto dall’intestazione `Referrer` trasmessa ad Analytics. | `h_referrer` |
| Date | Impostato sull’intestazione `Date` trasmessa ad Analytics. | `h_date` |

Inoltre, un segnale `h_ip` viene generato dall’IP dell’host che invia la richiesta a DCS.

## Segnali definiti dal cliente {#section_8F8C39E87BDE48BAA59E25CB7E86215D}

I parametri con prefisso `c_` identificano le variabili definite dal cliente. Consulta anche [Attributi supportati per le chiamate API DCS](https://experienceleague.adobe.com/docs/audience-manager/user-guide/api-and-sdk-code/dcs/dcs-api-reference/dcs-keys.html).

| Segnale | Descrizione |
| --- |--- |
| `c_browserWidth` e `c_browserHeight` | Larghezza e altezza della finestra del browser. |
| `c_campaign` | Impostato da `s.campaign`. |
| `c_channel` | Impostato da `s.channel`. |
| `c_clientDateTime` | Marca temporale formattata come `dd/mm/yyy hh:mm:ss  W TZ`. `TZ` è in minuti e corrisponde al risultato del metodo `Date.getTimezoneOffset`. |
| `c_colorDepth` | Specificato come colore a 16 o 32 bit. |
| `c_connectionType` | Specifica il tipo di connessione. Le opzioni includono:<ul><li>modem</li><li>lan</li></ul> |
| `c_contextData.*` | Esempi:<ul><li>AppMeasurement: `s.contextData`</li><li>[“categoria”] = “news”;</li><li>Segnale: `c_contextData.category=news`</li></ul> |
| `c_cookiesEnabled` | Specifica se i cookie possono essere abilitati. Le opzioni includono: sì, no, sconosciuto |
| `c_currencyCode` | Tipo di valuta utilizzata per la transazione. |
| `c_evar#` | eVar personalizzate |
| `c_events` | Impostate da `s.events`. |
| `c_hier#` | Variabili di gerarchia personalizzate. |
| `c_javaEnabled` | Specifica se Java può essere abilitato. Le opzioni includono: sì, no, sconosciuto |
| `c_javaScriptVersion` | Versione di JavaScript supportata da un browser. |
| `c_latitude` | Latitudine numerica |
| `c_linkClick` | Le opzioni includono: personalizzato, download, uscita |
| `c_linkCustomName` | Nome personalizzato (se presente) fornito per il collegamento. |
| `c_linkDownloadURL` | URL dei collegamenti per il download. |
| `c_linkExitURL` | URL del collegamento di uscita. |
| `c_list#` | Variabili elenco personalizzate. |
| `c_longitude` | Longitudine numerica. |
| `c_mediaPlayerType` | Per richieste di tracciamento del flusso multimediale. Le opzioni includono: altro, primetime |
| `c_pageName` | Nome della pagina (se impostato). |
| `c_pageURL` | Indirizzo della pagina nella barra degli indirizzi del browser. |
| `c_products` | La stringa di prodotto (impostata da `s.products`). |
| `c_prop` | Proprietà personalizzate. |
| `c_purchaseID` | Un ID univoco per l’acquisto. |
| `c_referrer` | La pagina precedente alla pagina corrente. |
| `c_screenResolution` | Larghezza e altezza dello schermo (in pixel). |
| `c_server` | Nome server Web (impostato da `s.server`). |
| `c_state` | Area geografica (impostata da `s.state`). |
| `c_timezone` | Offset tempo (in ore). |
| `c_transactionID` | Un ID univoco per una transazione. |
| `c_zip` | Codice postale (impostato da `s.zip`). |
