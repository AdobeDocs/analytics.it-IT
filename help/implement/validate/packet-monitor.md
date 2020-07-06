---
title: Analizzatore pacchetti
description: Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall'implementazione ai server di raccolta dati Adobe.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 2%

---


# Analizzatore pacchetti

Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall&#39;implementazione ai server di raccolta dati Adobe.

Analogamente al debugger di Adobe Experience Cloud, un monitor di pacchetti mostra quali parametri di dati vengono passati in una richiesta di immagine; tuttavia, i monitor a pacchetti offrono funzionalità aggiuntive:

* Visualizza richieste di immagini per tracciamento collegamenti personalizzati
* Visualizzare le richieste di immagini utilizzando metodi di implementazione diversi da JavaScript, ad esempio richieste di immagini hardcoded o [!DNL Appmeasurement]

Per visualizzare  richieste Analytics, filtrate le richieste in uscita utilizzando &quot;b/s&quot;.

In casi molto rari, il debugger segnalerà una richiesta di immagine anche se non viene inviata alcuna richiesta ai server di [!DNL Analytics] elaborazione di Adobe. L&#39;utilizzo di un monitor a pacchetti rappresenta un ottimo modo per garantire al 100% che una specifica richiesta di immagine venga attivata correttamente.

Adobe non fornisce un monitor di pacchetti ufficiale, ma ne offre un&#39;ampia gamma su Internet. Di seguito sono riportati alcuni monitor di pacchetti che altri hanno trovato utili.

>[!NOTE]
>
>Questi elenchi non sono completi, ma informazioni sui monitor più utilizzati. Se disponete di un monitor a pacchetti che potete utilizzare e che vi consente di ottenere un feedback, potete utilizzare il [!UICONTROL Feedback] pulsante sul lato destro della finestra.

| Firefox | Internet Explorer | Chrome | Programmi standalone |
|---|---|---|---|
| [Punto](https://www.observepoint.com/product#plugin) di osservazione (visualizzatore tag) | [HttpWatch](https://www.httpwatch.com/) | [Punto](https://www.observepoint.com/product#plugin) di osservazione (visualizzatore tag) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Strumenti per sviluppatori Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Dati mantra](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe NON supporta o risolve eventuali problemi riscontrati con questi monitor. Per assistenza, consultare il sito di origine del monitor del pacchetto.

## NS_BINDING_ABORTED nei codici di risposta

Questo errore si verifica perché la richiesta dell&#39;immagine di tracciamento del collegamento è progettata per consentire al browser di passare alla pagina successiva prima di attendere una risposta dai server di raccolta dati Adobe.

La risposta di Adobe alla richiesta di immagini è semplicemente un&#39;immagine trasparente 1x1 vuota, che non è pertinente al contenuto della pagina. Se viene visualizzato un elemento di riga nel monitor dei pacchetti da Adobe, con una **[!UICONTROL 200 OK]** risposta o una **[!UICONTROL NS_BINDING_ABORTED]** risposta, i dati hanno raggiunto i nostri server. Non è più necessario attendere la pagina.

I monitor Packet integrati come plug-in raramente visualizzano la risposta completa. Essi tendono a vedere la richiesta come interrotta perché non è stata ricevuta la risposta completa. Raramente questi monitor distinguono tra la richiesta o la risposta che è stata interrotta. In genere, un monitor a pacchetti indipendente contiene messaggi più dettagliati e segnala lo stato con maggiore precisione. Ad esempio, un utente potrebbe ricevere un messaggio in *Charles* che dice &quot;Connessione chiusa dal client prima di ricevere l&#39;intera risposta.&quot; Ciò significa che i dati sono arrivati ai nostri server, solo il browser si è spostato sulla pagina successiva prima che venisse ricevuto il pixel 1x1.

Se un packet sniffer esterno segnala che la richiesta di raccolta dei dati viene interrotta e non la risposta, ciò è motivo di preoccupazione. Adobe [!DNL Customer Care] può fornire assistenza nella risoluzione dei problemi.
