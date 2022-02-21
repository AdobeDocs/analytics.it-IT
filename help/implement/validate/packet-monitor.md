---
title: Analizzatore pacchetti
description: Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall’implementazione ai server di raccolta dati di Adobe.
keywords: packet sniffer, stato http, 200, 302, charles
feature: Validation
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '661'
ht-degree: 1%

---

# Analizzatore pacchetti

Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall’implementazione ai server di raccolta dati di Adobe.

Analogamente al debugger Adobe Experience Cloud, un monitoraggio dei pacchetti mostra quali parametri di dati vengono trasmessi in una richiesta di immagine; tuttavia, i monitor a pacchetti offrono funzionalità aggiuntive:

* Visualizza richieste di immagini di tracciamento dei collegamenti personalizzati
* Visualizza le richieste di immagini utilizzando metodi di implementazione diversi da JavaScript, ad esempio richieste di immagini codificate o [!DNL Appmeasurement]

Per visualizzare le richieste di Analytics, filtra le richieste in uscita utilizzando &quot;b/s&quot;.

In casi molto rari, il debugger segnalerà una richiesta di immagine anche se non viene effettuata alcuna richiesta al Adobe [!DNL Analytics] server di elaborazione. L&#39;utilizzo di un monitor a pacchetti è un ottimo modo per essere sicuri al 100% che una specifica richiesta di immagine venga attivata correttamente.

Mentre l&#39;Adobe non fornisce un monitor ufficiale a pacchetti, ce ne sono molti su Internet. Di seguito sono riportati alcuni monitor per pacchetti che altri hanno trovato utili.

>[!TIP]
>
>Questi elenchi non sono intesi come completi, ma come informazioni sui monitor più utilizzati.

| Firefox | Internet Explorer | Chrome | Programmi autonomi |
|---|---|---|---|
| [Punto di osservazione](https://www.observepoint.com/product#plugin) (visualizzatore di tag) | [HttpWatch](https://www.httpwatch.com/) | [Punto di osservazione](https://www.observepoint.com/product#plugin) (visualizzatore di tag) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Strumenti per sviluppatori Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Dati manomissione](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>L&#39;Adobe NON supporta o risolve eventuali problemi riscontrati con questi monitor di pacchetti. Per assistenza, consultare il sito di origine del monitor del pacchetto.

## Codici di stato tipici della risposta HTTP

Quando AppMeasurement invia dati ai server di raccolta dati di Adobe, i server rispondono con un codice di stato della risposta.

* **200 OK**: Risposta più comune dai server di raccolta dati. La richiesta di immagine è stata ricevuta e è stata restituita un&#39;immagine trasparente.
* **302 TROVATI**: Ci sono un paio di possibili motivi per ricevere questa risposta:
   * La prima richiesta di immagine di un visitatore: Un reindirizzamento si verifica se un utente visita il tuo sito per la prima volta. Questo reindirizzamento serve a ottenere un cookie visitatore. Non influisce sulla raccolta dei dati.
   * Integrazione tra Comscore e Adobe: Se l’organizzazione utilizza un’integrazione Comscore/Analytics, ogni richiesta di immagine genera sempre una risposta 302.
* **404 NON TROVATO**: Questa risposta indica che la richiesta di immagine non è stata trovata e che i dati non vengono inviati ai server di raccolta dati di Adobe. Questa risposta è possibile anche quando le richieste di immagini codificate non sono formattate correttamente. Collabora con la persona o il team che ha implementato Analytics per risolvere questo problema.

## NS_BINDING_ABORTED nei codici di risposta

Questo messaggio si verifica perché la richiesta di immagine di tracciamento del collegamento è progettata per consentire al browser di passare alla pagina successiva prima di attendere una risposta dai server di raccolta dati di Adobe.

La risposta dell’Adobe alla richiesta di immagine è semplicemente un’immagine trasparente 1x1 vuota, che non è pertinente al contenuto della pagina. Se viene visualizzata una riga nel monitor dei pacchetti dall&#39;Adobe, con un **[!UICONTROL 200 OK]** risposta o **[!UICONTROL NS_BINDING_ABORTED]** i dati hanno raggiunto i server di Adobe. Non è più necessario attendere la pagina.

I monitor per pacchetti integrati come plug-in visualizzano raramente la risposta completa. Tendono a vedere la richiesta come interrotta perché non è stata ricevuta la risposta completa. Raramente, questi monitor distinguono tra la richiesta o la risposta che è stata interrotta. In genere, un monitor a pacchetti autonomo presenta messaggi più dettagliati e segnala lo stato con maggiore precisione. Ad esempio, un utente può ricevere un messaggio in *Charles* dicendo &quot;Connessione chiusa dal client prima di ricevere l&#39;intera risposta.&quot; Ciò significa che i dati sono arrivati ai nostri server, solo il browser è passato alla pagina successiva prima che il pixel 1x1 fosse ricevuto.

Se un monitoraggio dei pacchetti esterno segnala che la richiesta di raccolta dei dati viene interrotta e non la risposta, questo è motivo di preoccupazione. Adobe [!DNL Customer Care] può fornire assistenza nella risoluzione dei problemi.
