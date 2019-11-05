---
description: Le intestazioni di richiesta e risposta HTTP vengono utilizzate per raccogliere dati aggiuntivi oltre a quanto raccolto da AppMeasurement. Questa sezione descrive le intestazioni utilizzate durante la raccolta dei dati.
keywords: Implementazione di Analytics
seo-description: Le intestazioni di richiesta e risposta HTTP vengono utilizzate per raccogliere dati aggiuntivi oltre a quanto raccolto da AppMeasurement. Questa sezione descrive le intestazioni utilizzate durante la raccolta dei dati.
seo-title: Intestazioni HTTP della raccolta dati
solution: Analytics
title: Intestazioni HTTP della raccolta dati
topic: Sviluppatore e implementazione
uuid: 3325e13c-b300-46e4-a592-3a83ed59718b
translation-type: tm+mt
source-git-commit: 57fe1f6d613b9f54a5191ac8684d36bccfebf4e5

---


# Intestazioni HTTP della raccolta dati

Le intestazioni di richiesta e risposta HTTP vengono utilizzate per raccogliere dati aggiuntivi oltre a quanto raccolto da AppMeasurement. Questa sezione descrive le intestazioni utilizzate durante la raccolta dei dati.

## Intestazioni richiesta HTTP {#section_C1DE3416CCC241A898155C915A01A0FC}

<table id="table_84D1F4B54ABE4423A2EBE840C49D3876"> 
 <tbody> 
  <tr> 
   <td> <b>Intestazione</b> </td> 
   <td> <b>Utilizzo</b> </td> 
  </tr> 
  <tr> 
   <td> Cookie </td> 
   <td> <p>Lettura dei cookie creati in precedenza dai nostri server di raccolta dati. </p> <p> A partire dal 2014, i server Adobe scaricheranno tutti i cookie che accompagnano una chiamata al server, ad eccezione di quelli impostati da Adobe. Consulta <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/"> Cookie utilizzati in Experience Cloud</a> per l'elenco completo dei cookie Adobe. </p> </td> 
  </tr> 
  <tr> 
   <td> Agente utente </td> 
   <td> Utilizzato per il rilevamento di browser, sistemi operativi e dispositivi mobili. </td> 
  </tr> 
  <tr> 
   <td> X-Device-User-Agent </td> 
   <td> Utilizzato come alternativa a User-Agent per il corretto rilevamento di browser, sistemi operativi e dispositivi mobili per alcuni browser come OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Original-User-Agent </td> 
   <td> Utilizzato come alternativa a User-Agent per il corretto rilevamento di browser, sistemi operativi e dispositivi mobili per alcuni browser come OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-OperaMini-Phone-UA </td> 
   <td> Utilizzato come alternativa a User-Agent per il corretto rilevamento di browser, sistemi operativi e dispositivi mobili per alcuni browser come OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Skyfire-Phone </td> 
   <td> Utilizzato come alternativa a User-Agent per il corretto rilevamento di browser, sistemi operativi e dispositivi mobili per alcuni browser come OperaMini. </td> 
  </tr> 
  <tr> 
   <td> X-Bolt-Phone-UA </td> 
   <td> Utilizzato come alternativa a User-Agent per il corretto rilevamento di browser, sistemi operativi e dispositivi mobili per alcuni browser come OperaMini. </td> 
  </tr> 
  <tr> 
   <td> UA-OS </td> 
   <td> Utilizzata come alternativa era identificare il sistema operativo. </td> 
  </tr> 
  <tr> 
   <td> UA-Pixel </td> 
   <td> Utilizzato come origine alternativa per la risoluzione dello schermo dello schermo client. </td> 
  </tr> 
  <tr> 
   <td> UA-Color </td> 
   <td> Utilizzato come origine alternativa per la profondità colore dello schermo client. </td> 
  </tr> 
  <tr> 
   <td> X-moz </td> 
   <td> Rilevamento della richiesta di raccolta dati effettuata come parte del preacquisizione di una pagina Web. </td> 
  </tr> 
  <tr> 
   <td> X-Purpose </td> 
   <td> Rilevamento della richiesta di raccolta dati eseguita mentre il browser visualizzava l'anteprima di una pagina Web. </td> 
  </tr> 
  <tr> 
   <td> Accetta </td> 
   <td> Utilizzato per identificare i formati immagine supportati dal browser, in modo da sapere se è necessario restituire un'immagine GIF o WBMP. </td> 
  </tr> 
  <tr> 
   <td> Referrer </td> 
   <td> Utilizzato come fallback per ottenere informazioni sull’URL della pagina da cui è stata richiesta la raccolta dati quando non è stata passata sulla stringa di query o quando è diversa dal valore nella stringa di query. </td> 
  </tr> 
  <tr> 
   <td> X-Forwarded-For </td> 
   <td> Utilizzato per trovare l'indirizzo IP corretto per il client che ha eseguito la richiesta di raccolta dati. L'indirizzo IP viene utilizzato per generare aree geografiche, portatori di dispositivi mobili e altri rapporti. </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Le implementazioni che utilizzano variabili dinamiche possono essere lette in altre intestazioni di richiesta HTTP non elencate sopra.

## Intestazioni di risposta HTTP {#section_A9C7035198C84037A21A8033CC408F0E}

| **Intestazione** | **Utilizzo** |
|---|---|
| Access-Control-Allow-Origin | Utilizzato per abilitare il supporto per le richieste di raccolta dati in stile di condivisione delle risorse tra origini ai nostri server. |
|  Scadenza | Controllo di memorizzazione nella cache del browser. |
| Ultima modifica | Controllo di memorizzazione nella cache del browser. |
| Cache-Control | Controllo di memorizzazione nella cache del browser. |
| Praga | Controllo di memorizzazione nella cache del browser. |
| ETag | Controllo di memorizzazione nella cache del browser. |
| Varia | Controllo di memorizzazione nella cache del browser. |
| P3P | Fornisce il criterio P3P predefinito o personalizzato per la richiesta di raccolta dati. |
| Stato | Contiene lo stato "SUCCESS" o "FAILURE" per una richiesta di assenza di contenuto. Utilizzato solo quando la richiesta specifica che non deve essere restituito alcun contenuto. |
| Motivo | Contiene il motivo dell'errore nello stato di una richiesta di assenza di contenuto. Utilizzato solo quando la richiesta specifica che non deve essere restituito alcun contenuto. |
| Posizione | Utilizzato per reindirizzare il client che invia la richiesta di raccolta dati a un URL diverso. Un esempio è il nostro cookie handshake per rilevare la capacità di impostare il cookie dell’ID visitatore. |
| Content-Type | Specifica il tipo di contenuto inviato al client (GIF, testo, Javascript, ecc.). |
| Content-Length | Specifica la dimensione del contenuto inviato al client. |

> [!NOTE] È possibile impostare altre intestazioni HTTP nella risposta per il monitoraggio dello stato interno. Alcune di queste intestazioni potrebbero essere restituite al browser, ma non è necessario che le ricevano.
