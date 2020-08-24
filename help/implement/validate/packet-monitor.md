---
title: Analizzatore pacchetti
description: Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall'implementazione ai server di raccolta dati  Adobe.
keywords: packet sniffer, http status, 200, 302, charles
translation-type: tm+mt
source-git-commit: b359582fe8ab6ee04bb478825d9989d850390f96
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 1%

---


# Analizzatore pacchetti

Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall&#39;implementazione ai server di raccolta dati  Adobe.

Come per Adobe Experience Cloud Debugger, un monitor di pacchetti mostra quali parametri di dati vengono passati in una richiesta di immagine; tuttavia, i monitor a pacchetti offrono funzionalità aggiuntive:

* Visualizza richieste di immagini per tracciamento collegamenti personalizzati
* Visualizzare le richieste di immagini utilizzando metodi di implementazione diversi da JavaScript, ad esempio richieste di immagini hardcoded o [!DNL Appmeasurement]

Per visualizzare le richieste di Analytics, filtra le richieste in uscita utilizzando &quot;b/s&quot;.

In casi molto rari, il debugger segnalerà una richiesta di immagine anche se nessuna richiesta viene effettuata a  server di [!DNL Analytics] elaborazione  Adobe. L&#39;utilizzo di un monitor a pacchetti rappresenta un ottimo modo per garantire al 100% che una specifica richiesta di immagine venga attivata correttamente.

Sebbene  Adobe non fornisca un monitor di pacchetti ufficiale, ce ne sono molti su Internet. Di seguito sono riportati alcuni monitor di pacchetti che altri hanno trovato utili.

>[!TIP]
>
>Questi elenchi non sono completi, ma informazioni sui monitor più utilizzati.

| Firefox | Internet Explorer | Chrome | Programmi standalone |
|---|---|---|---|
| [Punto](https://www.observepoint.com/product#plugin) di osservazione (visualizzatore tag) | [HttpWatch](https://www.httpwatch.com/) | [Punto](https://www.observepoint.com/product#plugin) di osservazione (visualizzatore tag) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Strumenti per sviluppatori Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Dati mantra](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
> Adobe NON supporta o risolve eventuali problemi riscontrati con questi monitor. Per assistenza, consultare il sito di origine del monitor del pacchetto.

## Codici di stato tipici della risposta HTTP

Quando AppMeasurement invia i dati  server di raccolta dati di Adobe, i server rispondono con un codice di stato della risposta.

* **200 OK**: La risposta più comune dai server di raccolta dati. La richiesta dell&#39;immagine è stata ricevuta e viene restituita un&#39;immagine trasparente.
* **302 TROVATO**: Esistono due possibili motivi per ricevere questa risposta:
   * La prima richiesta di immagine di un visitatore: Un reindirizzamento si verifica se un utente visita il sito per la prima volta. Questo reindirizzamento consiste nel ottenere un cookie visitatore. Non influisce sulla raccolta dei dati.
   * Integrazione tra Comscore e  Adobe: Se l’organizzazione utilizza un’integrazione Comscore/Analytics, ogni richiesta di immagine genera sempre una risposta 302.
* **404 NON TROVATO**: Questa risposta indica che la richiesta di immagine non è stata trovata e che i dati non vengono inviati  server di raccolta dati del Adobe. Questa risposta è possibile anche quando le richieste di immagini hardcoded non sono formattate correttamente. Per risolvere il problema, collabora con il singolo o il team che ha implementato Analytics.

## NS_BINDING_ABORTED nei codici di risposta

Questo messaggio si verifica perché la richiesta dell&#39;immagine di tracciamento del collegamento è progettata per consentire al browser di passare alla pagina successiva prima di attendere una risposta dai server di raccolta dei dati del Adobe .

 Adobe  risposta alla richiesta dell’immagine è semplicemente un’immagine trasparente 1x1 vuota, che non è pertinente al contenuto della pagina. Se viene visualizzato un elemento di riga nel monitor dei pacchetti  Adobe, con una **[!UICONTROL 200 OK]** risposta o una **[!UICONTROL NS_BINDING_ABORTED]** risposta, i dati hanno raggiunto  server  Adobi. Non è più necessario attendere la pagina.

I monitor Packet integrati come plug-in raramente visualizzano la risposta completa. Essi tendono a vedere la richiesta come interrotta perché non è stata ricevuta la risposta completa. Raramente questi monitor distinguono tra la richiesta o la risposta che è stata interrotta. In genere, un monitor a pacchetti indipendente contiene messaggi più dettagliati e segnala lo stato con maggiore precisione. Ad esempio, un utente potrebbe ricevere un messaggio in *Charles* che dice &quot;Connessione chiusa dal client prima di ricevere l&#39;intera risposta.&quot; Ciò significa che i dati sono arrivati ai nostri server, solo il browser si è spostato sulla pagina successiva prima che venisse ricevuto il pixel 1x1.

Se un monitoraggio dei pacchetti esterno segnala che la richiesta di raccolta dei dati viene interrotta e non la risposta, ciò è motivo di preoccupazione.  Adobe [!DNL Customer Care] può fornire assistenza nella risoluzione dei problemi.
