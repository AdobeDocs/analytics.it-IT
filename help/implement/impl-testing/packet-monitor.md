---
description: Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall'implementazione ai server di raccolta dati Adobe.
keywords: Analytics Implementation
solution: Analytics
subtopic: Debugger
title: Analizzatore pacchetti
topic: Developer and implementation
uuid: 3597c23a-1c72-46e6-909d-f861cbeef490
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Analizzatore pacchetti

Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall'implementazione ai server di raccolta dati Adobe.

Simile a [!DNL DigitalPulse Debugger], un monitor di pacchetti mostra i parametri di dati trasmessi in una richiesta di immagine; tuttavia, i monitor a pacchetti offrono funzionalità aggiuntive:

* Visualizza richieste immagine per tracciamento collegamenti personalizzati
* Visualizzare le richieste di immagini utilizzando metodi di implementazione diversi da JavaScript, ad esempio richieste di immagini hardcoded o [!DNL Appmeasurement]

Per visualizzare le richieste di Analytics, filtra le richieste in uscita utilizzando "b/s".

In casi molto rari, il debugger segnalerà una richiesta di immagine anche se non viene inviata alcuna richiesta ai server di [!DNL Analytics] elaborazione di Adobe. L'utilizzo di un monitor a pacchetti rappresenta un ottimo modo per garantire al 100% che una specifica richiesta di immagine venga attivata correttamente.

Adobe non fornisce un monitor di pacchetti ufficiale, ma ne offre un'ampia gamma su Internet. Di seguito alcuni monitor di pacchetti che altri hanno trovato utili.

> [!NOTE] Questi elenchi non sono completi, ma informazioni sui monitor più utilizzati. Se disponete di un monitor a pacchetti che potete utilizzare e che vi consente di ottenere un feedback, potete utilizzare il [!UICONTROL Feedback] pulsante a destra della finestra.

| Firefox | Internet Explorer | Chrome | Programmi standalone |
|---|---|---|---|
| [Punto](https://www.observepoint.com/product#plugin) di osservazione (visualizzatore tag) | [HttpWatch](https://www.httpwatch.com/) | [Punto](https://www.observepoint.com/product#plugin) di osservazione (visualizzatore tag) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Chrome Developer Tools](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Dati mantra](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

> [!NOTE] Adobe NON supporta o risolve eventuali problemi riscontrati con questi monitor. Per assistenza, consultare il sito di origine del monitor del pacchetto.

<!-- 

debugger_ns_binding.xml

 -->

Questo errore si verifica perché la richiesta dell'immagine di tracciamento del collegamento è progettata per consentire al browser di passare alla pagina successiva prima di attendere una risposta dai server di raccolta dati Adobe.

La risposta di Adobe alla richiesta di immagini è semplicemente un'immagine trasparente 1x1 vuota, che non è pertinente al contenuto della pagina. Se viene visualizzato un elemento di riga nel monitor dei pacchetti da Adobe, con una **[!UICONTROL 200 OK]** risposta o una **[!UICONTROL NS_BINDING_ABORTED]** risposta, i dati hanno raggiunto i nostri server. Non è più necessario attendere la pagina.

I monitor Packet integrati come plug-in raramente visualizzano la risposta completa. Essi tendono a vedere la richiesta come interrotta perché non è stata ricevuta la risposta completa. Raramente questi monitor distinguono tra la richiesta o la risposta che è stata interrotta. In genere, un monitor a pacchetti indipendente contiene messaggi più dettagliati e segnala lo stato con maggiore precisione. Ad esempio, un utente potrebbe ricevere un messaggio in *Charles* che dice "Connessione chiusa dal client prima di ricevere l'intera risposta." Ciò significa che i dati sono arrivati ai nostri server, solo il browser si è spostato sulla pagina successiva prima che venisse ricevuto 1x1 pixel.

Se un packet sniffer esterno segnala che la richiesta di raccolta dei dati viene interrotta e non la risposta, ciò è motivo di preoccupazione. Adobe [!DNL Customer Care] può fornire assistenza nella risoluzione dei problemi.
