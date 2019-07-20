---
description: Gli analisti di pacchetti consentono di visualizzare i dati inviati dall'implementazione ai server di raccolta dati Adobe.
keywords: Implementazione di Analytics
seo-description: Gli analisti di pacchetti consentono di visualizzare i dati inviati dall'implementazione ai server di raccolta dati Adobe.
seo-title: Analyet analyzer
solution: Analytics
subtopic: Strumento di debug
title: Analyet analyzer
topic: Sviluppatore e implementazione
uuid: 3597 c 23 a -1 c 72-46 e 6-909 d-f 861 cbeef 490
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Analyet analyzer

Gli analisti di pacchetti consentono di visualizzare i dati inviati dall'implementazione ai server di raccolta dati Adobe.

Simliar to the [!DNL DigitalPulse Debugger], a packet monitor shows what data parameters are being passed in an image request; however, packet monitors provide added functionality:

* Visualizzare le richieste di immagini personalizzate per il tracciamento dei collegamenti
* View image requests using implementation methods other than JavaScript, such as hard-coded image requests or [!DNL Appmeasurement]

Per visualizzare le richieste di Analytics, filtrate le richieste in uscita utilizzando «b/ss».

In very rare cases, the debugger will report an image request although no request makes it to Adobe's [!DNL Analytics] processing servers. L'utilizzo di un monitor packet è un ottimo metodo per fare in modo che una richiesta di immagine specifica venga avviata correttamente.

Adobe non fornisce un monitor ufficiale per i pacchetti, ma ne dispone su Internet. Di seguito sono riportati alcuni monitor di pacchetti che altri utenti hanno scoperto.

>[!NOTE]
>
>Questi elenchi non devono essere completi, ma piuttosto informazioni sui monitor utilizzati più frequentemente. If you have a packet monitor you successfully use and find useful, feel free to provide feedback using the [!UICONTROL Feedback] button on the right side of this window.

| Firefox | Internet Explorer | Chrome | Programmi indipendenti |
|---|---|---|---|
| [Punto di osservazione](https://www.observepoint.com/product#plugin) (visualizzatore tag) | [Httpwatch](https://www.httpwatch.com/) | [Punto di osservazione](https://www.observepoint.com/product#plugin) (visualizzatore tag) | [Charles](https://www.charlesproxy.com/) |
| [Httpfox](https://addons.mozilla.org/en-US/firefox/addon/httpfox/) |  | [Strumenti per sviluppatori Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Fiddler](https://www.fiddler2.com/fiddler2/) |
| [Dati Tamper](https://addons.mozilla.org/en-us/firefox/addon/tamper-data/) |  | [Firebug Lite](https://chrome.google.com/webstore/detail/bmagokdooijbeehmkpknfglimnifench) | [Wireshark](https://www.wireshark.org/) |
| [Httpwatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe NON supporta o risolvono problemi che potrebbero verificarsi con questi monitor pacchetti. Consultate il sito di origine del monitor per ottenere assistenza.

<!-- 

debugger_ns_binding.xml

 -->

Questo errore si verifica perché la richiesta di immagini di tracciamento del collegamento è stata progettata per consentire al browser di passare alla pagina successiva prima di attendere una risposta dai server di raccolta dati Adobe.

La risposta di Adobe alla richiesta immagine è semplicemente un'immagine trasparente da 1 x 1 trasparente, che non è pertinente al contenuto della pagina. If you see a line item in your packet monitor from Adobe, either with a **[!UICONTROL 200 OK]** response or an **[!UICONTROL NS_BINDING_ABORTED]** response, the data has reached our servers. Non è necessario attendere più la pagina.

I monitor dei pacchetti integrati come plug-in raramente vedono la risposta completa. Tendono a vedere la richiesta come interrotta perché la risposta completa non è stata ricevuta. Anche questi monitor raramente fanno una distinzione tra la richiesta o la risposta interrotta. In genere, un monitor indipendente contiene messaggi più dettagliati e segnala lo stato con maggiore precisione. For example, a user may get a message in *Charles* saying "Client closed connection before receiving entire response." Ciò significa che i dati hanno raggiunto i nostri server, ma solo il browser è stato spostato nella pagina successiva prima della ricezione di 1 x 1 pixel.

Se un sniffer di pacchetti esterno segnala che la richiesta di raccolta dati viene interrotta, anziché la risposta, questo è un problema. Adobe [!DNL Customer Care] can provide help in troubleshooting.
