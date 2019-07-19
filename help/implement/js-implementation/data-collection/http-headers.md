---
description: Le intestazioni di richiesta e risposta HTTP vengono utilizzate per raccogliere dati aggiuntivi oltre il raccolto da appmeasurement. Questa sezione descrive le intestazioni utilizzate durante la raccolta di dati.
keywords: Implementazione di Analytics
seo-description: Le intestazioni di richiesta e risposta HTTP vengono utilizzate per raccogliere dati aggiuntivi oltre il raccolto da appmeasurement. Questa sezione descrive le intestazioni utilizzate durante la raccolta di dati.
seo-title: Intestazioni HTTP della raccolta dati
solution: Analytics
title: Intestazioni HTTP della raccolta dati
topic: Sviluppatore e implementazione
uuid: 3325 e 13 c-b 300-46 e 4-a 592-3 a 83 ed 59718 b
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Intestazioni HTTP della raccolta dati

Le intestazioni di richiesta e risposta HTTP vengono utilizzate per raccogliere dati aggiuntivi oltre il raccolto da appmeasurement. Questa sezione descrive le intestazioni utilizzate durante la raccolta di dati.

## HTTP Request Headers {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>Intestazione</b> </td> 
   <td> <b>Utilizzo</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>I cookie di lettura creati in precedenza dai nostri server di raccolta dati. </p> <p> A partire da 2014, i server Adobe elimineranno tutti i cookie che accompagnano una chiamata al server, eccetto quelli impostati da Adobe. See <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/" format="https" scope="external"> Cookies Used in the Experience Cloud</a> for the full list of Adobe's cookies. </p> </td> 
  </tr> 
  <tr> 
   <td> Agente utente </td> 
   <td> Utilizzato per il browser, il sistema operativo e il rilevamento del dispositivo mobile. </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> Utilizzato come alternativa all'agente utente per il browser corretto, il sistema operativo e il rilevamento del dispositivo mobile per alcuni browser come operamini. </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> Utilizzato come alternativa all'agente utente per il browser corretto, il sistema operativo e il rilevamento del dispositivo mobile per alcuni browser come operamini. </td> 
  </tr> 
  <tr> 
   <td> X-operamini-Phone-UA </td> 
   <td> Utilizzato come alternativa all'agente utente per il browser corretto, il sistema operativo e il rilevamento del dispositivo mobile per alcuni browser come operamini. </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> Utilizzato come alternativa all'agente utente per il browser corretto, il sistema operativo e il rilevamento del dispositivo mobile per alcuni browser come operamini. </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> Utilizzato come alternativa all'agente utente per il browser corretto, il sistema operativo e il rilevamento del dispositivo mobile per alcuni browser come operamini. </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> L'alternativa alternativa era identificare il sistema operativo. </td> 
  </tr> 
  <tr> 
   <td> UA-Pixel </td> 
   <td> Utilizzato come origine alternativa per la risoluzione dello schermo della schermata del client. </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> Utilizzato come origine alternativa per la profondità del colore della schermata client. </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> Rilevare che la richiesta di raccolta dati è stata effettuata durante la preacquisizione di una pagina Web. </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> Rilevare che la richiesta di raccolta dati è stata eseguita come browser mostra un'anteprima di una pagina Web. </td> 
  </tr> 
  <tr> 
   <td> Accetta </td> 
   <td> Utilizzato per identificare i formati immagine supportati dal browser, in modo da sapere se è necessario restituire un'immagine GIF o WBMP. </td> 
  </tr> 
  <tr> 
   <td> Referrer </td> 
   <td> Utilizzato come fallback per ottenere informazioni sull'URL della pagina, la richiesta di raccolta dati veniva effettuata quando non veniva trasmesso sulla stringa query o quando era diverso dal valore nella stringa query. </td> 
  </tr> 
  <tr> 
   <td> X-inoltr@-@ for </td> 
   <td> Utilizzato per trovare l'indirizzo IP corretto per il client che ha eseguito la richiesta di raccolta dati. L'indirizzo IP viene usato per generare un'area geografica, un gestore mobile e altri rapporti. </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Le implementazioni che utilizzano variabili dinamiche possono essere visualizzate in altre intestazioni della richiesta HTTP non elencate sopra.

## HTTP Response Headers {#section_A9C7035198C84037A21A8033CC408F0E}

| **Intestazione** | **Utilizzo** |
|---|---|
| Access-Control-Allow-Origin | Utilizzato per consentire ai server di condividere le richieste di raccolta dati per più origini tra origini. |
| Scade | Controllo del caching del browser. |
| Ultima modifica | Controllo del caching del browser. |
| Cache-Control | Controllo del caching del browser. |
| Pragma | Controllo del caching del browser. |
| Etag | Controllo del caching del browser. |
| Variabili | Controllo del caching del browser. |
| P3P | Fornisce il criterio P 3 P predefinito o personalizzato per la richiesta di raccolta dati. |
| Stato | Contiene lo stato "SUCCESS" o "FAILURE" per nessuna richiesta di contenuto. Utilizzato solo quando la richiesta specifica che non è necessario restituire alcun contenuto. |
| Motivo | Contiene il motivo dello stato non riuscito di una richiesta di contenuto. Utilizzato solo quando la richiesta specifica che non è necessario restituire alcun contenuto. |
| Posizione | Utilizzato per reindirizzare il client verso la richiesta di disattivazione della richiesta di raccolta dati a un URL diverso. Un esempio è l'handshake del cookie per rilevare la capacità di impostare il cookie ID visitatore. |
| Tipo di contenuto | Specifica il tipo di contenuto inviato al client (GIF, testo, Javascript, ecc.). |
| Lunghezza contenuto | Specifica la dimensione del contenuto inviato al client. |

>[!NOTE]
>
>Altre intestazioni HTTP possono essere impostate nella risposta per il monitoraggio dello stato interno. Alcune di queste intestazioni possono essere inviate al browser, ma non sono necessarie.
