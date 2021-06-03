---
title: Domande frequenti sull’implementazione
description: Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.
exl-id: 4bab6d51-0077-42ce-8091-f75207d4c4db
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 100%

---

# Domande frequenti sull’implementazione di Analytics

Domande frequenti sull’implementazione e collegamenti a ulteriori informazioni.

## Qual è la differenza tra l’ID visitatore Experience Cloud e l’ID visitatore Analytics?

Identity Service assegna un identificatore univoco e permanente che può essere condiviso tra le altre soluzioni Experience Cloud. L’ID visitatore di Analytics è utilizzato solo da Analytics. Adobe consiglia di utilizzare il servizio ID visitatori di Experience Cloud per la tua implementazione.

## Come si implementa il Tracciamento video Heartbeat?

Vedi la sezione [Misurazione di audio e video in Adobe Analytics](https://docs.adobe.com/content/help/it-IT/experience-cloud/user-guides/home.translate.html).

## Un’interruzione del servizio Adobe può influire sulle prestazioni?

No. Il file JavaScript non è ospitato sui server Adobe, pertanto un’interruzione da parte di Adobe non influirà sulla libreria AppMeasurement. Se utilizzi Adobe Experience Platform Launch, il file JavaScript è ospitato da Akamai o in una posizione server determinata dalla tua organizzazione.

## L’invio di dati dal browser ai servizi Adobe riduce le prestazioni?

AppMeasurement crea un oggetto immagine all’interno della pagina HTML e il browser quindi richiede l’oggetto immagine ai server di raccolta dati Adobe. Se i server di raccolta dati dovessero essere lenti o non rispondere, la gestione del thread della richiesta verrebbe ritardata fino al ritorno dell’immagine o al verificarsi di un timeout. Poiché i browser gestiscono immagini con più thread, un’interruzione di Adobe avrebbe un impatto minimo sul tempo di caricamento della pagina, bloccando un thread mentre gli altri continuano a funzionare.

## Come posso annullare o rimuovere un’implementazione di Analytics?

A volte un’organizzazione desidera rimuovere un’implementazione a causa della scadenza del contratto o per ridurre il numero di chiamate al server.

* **Implementazioni eseguite con Launch**: disabilita o disinstalla l’estensione Adobe Analytics nella scheda [!UICONTROL Extensions], quindi pubblica.
* **Implementazioni legacy di AppMeasurement**: sostituisci l’intero contenuto del file `s_code.js` con la seguente riga di codice:

```js
var s = new Object();
```

>[!WARNING]
>
>Assicurati di:
>
>* NON cambiare la suite di rapporti in un valore non valido, in quanto crea un carico non necessario sui server di Adobe.
>* NON rimuovere completamente il file `s_code.js`, a meno di non rimuovere anche tutti i riferimenti al file su ogni pagina.
>* NON modificare la variabile `trackingServer` in modo che non punti ad Adobe. AppMeasurement invia comunque le richieste di immagini, che restituiscono errori 404.


## Ho eseguito AppMeasurement tramite un analizzatore di codice, e ha segnalato il suo utilizzo di `Math.random()` come potenziale rischio per la sicurezza. `Math.random()` viene utilizzato con dati sensibili?

No. I numeri che utilizzano `Math.random()` non vengono utilizzati per mascherare, inviare o ricevere dati sensibili. I dati inviati ai server di raccolta dati di Adobe si basano sulla sicurezza della connessione HTTPS sottostante. <!-- AN-173590 -->

AppMeasurement utilizza `Math.random()` in tre aree chiave:

* **Campionamento**: a seconda dell’implementazione, alcune informazioni potrebbero essere raccolte solo per una piccola percentuale di visitatori del sito. `Math.random()` viene utilizzato per determinare se un visitatore può inviare dati. La maggior parte delle implementazioni non utilizza il campionamento.
* **ID visitatore di fallback**: se l’ID visitatore non può essere recuperato dai cookie, viene generato un ID visitatore casuale. Questa parte di AppMeasurement utilizza due chiamate a `Math.random()`.
* **Cache busting**: viene aggiunto un numero casuale alla fine degli URL di richiesta dell’immagine per evitare che venga caricata un la versione già presente nella cache del browser.
