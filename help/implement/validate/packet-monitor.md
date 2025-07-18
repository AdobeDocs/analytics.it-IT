---
title: Analizzatori di pacchetti
description: Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall’implementazione ai server di raccolta dati di Adobe.
keywords: packet sniffer, stato http, 200, 302, charles
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
source-git-commit: 29ab0cc535bd8f74b50428c11756bf8b446a23ab
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 1%

---

# Analizzatori di pacchetti

Gli analizzatori di pacchetti consentono di visualizzare i dati inviati dall’implementazione ai server di raccolta dati di Adobe.

Analogamente al debugger di Adobe Experience Cloud, un monitor di pacchetto mostra quali parametri di dati vengono trasmessi in una richiesta di immagine; tuttavia, i monitor di pacchetto forniscono funzionalità aggiuntive:

* Visualizzare le richieste di immagini per il tracciamento dei collegamenti personalizzati
* Visualizzare le richieste di immagini utilizzando metodi di implementazione diversi da JavaScript, ad esempio richieste di immagini hardcoded o [!DNL Appmeasurement]

Per visualizzare le richieste di Analytics, filtra le richieste in uscita utilizzando &quot;b/ss&quot;.

In casi molto rari, il debugger segnalerà una richiesta di immagine, anche se nessuna richiesta lo farà ai server di elaborazione [!DNL Analytics] di Adobe. L&#39;utilizzo di un monitor di pacchetto è un ottimo modo per essere sicuri al 100% che una richiesta di immagine specifica venga attivata correttamente.

Sebbene Adobe non fornisca un monitoraggio ufficiale dei pacchetti, ce ne sono un&#39;ampia gamma su Internet. Di seguito sono riportati alcuni monitor di pacchetti che altri hanno trovato utili.

>[!TIP]
>
>Questi elenchi non sono intesi come completi, ma piuttosto informazioni sui monitor utilizzati di frequente.

| Firefox | Internet Explorer | Chrome | Programmi autonomi |
|---|---|---|---|
| [Osserva punto](https://www.observepoint.com/product#plugin) (visualizzatore tag) | [HttpWatch](https://www.httpwatch.com/) | [Osserva punto](https://www.observepoint.com/product#plugin) (visualizzatore tag) | [Charles](https://www.charlesproxy.com/) |
| [HttpFox](https://addons.thunderbird.net/en-us/firefox/addon/httpfox/) |  | [Strumenti per gli sviluppatori di Chrome](https://code.google.com/chrome/devtools/docs/overview.html) | [Filtro](https://www.telerik.com/fiddler) |
| [Dati manomessi](https://addons.mozilla.org/en-US/firefox/addon/tamper-data-for-ff-quantum/) |  | [Firebug Lite](https://chromewebstore.google.com/detail/firebug-lite-for-google-c/ehemiojjcpldeipjhjkepfdaohajpbdo) | [Wireshark](https://www.wireshark.org/) |
| [HttpWatch](https://www.httpwatch.com/) |  |  |  |
| [Firebug](https://getfirebug.com/) |  |  |  |

>[!NOTE]
>
>Adobe NON supporta o non risolve i problemi che si verificano con questi monitor di pacchetti. Per assistenza, consultare il sito di origine del monitor pacchetti.

## Codici di stato di risposta HTTP tipici

Quando AppMeasurement invia i dati ai server di raccolta dati di Adobe, questi rispondono con un codice di stato di risposta.

* **200 OK**: la risposta più comune dai server di raccolta dati. La richiesta di immagine è stata ricevuta e restituita un&#39;immagine trasparente.
* **302 TROVATO**: possibili motivi per ricevere questa risposta:
   * Prima richiesta di immagine di un visitatore: si verifica un reindirizzamento se un utente visita il sito per la prima volta. Questo reindirizzamento consiste nell’ottenere un cookie visitatore. Non influisce sulla raccolta dei dati.
   * Integrazione tra Comscore e Adobe: se l’organizzazione utilizza un’integrazione Comscore/Analytics, ogni richiesta di immagine genera sempre una risposta 302.
* **404 NON TROVATO**: questa risposta indica che la richiesta di immagine non è stata trovata e che i dati non vengono inviati ai server di raccolta dati di Adobe. Questa risposta è possibile anche quando le richieste di immagini codificate non vengono formattate correttamente. Collabora con il singolo utente o il team che ha implementato Analytics per risolvere questo problema.

## NS_BINDING_ABORTED nei codici di risposta

Questo messaggio si verifica perché la richiesta di immagine per il tracciamento dei collegamenti è progettata per consentire al browser di passare alla pagina successiva prima di attendere una risposta dai server di raccolta dati di Adobe.

La risposta di Adobe alla richiesta di immagine è semplicemente un’immagine trasparente 1x1 vuota, che non è pertinente al contenuto della pagina. Adobe Se nel monitor pacchetti viene visualizzata una riga con una risposta di **[!UICONTROL 200 OK]** o di **[!UICONTROL NS_BINDING_ABORTED]**, i dati hanno raggiunto i server di Adobe. Non è più necessario attendere la pagina.

I monitor per pacchetti integrati come plug-in raramente ottengono una risposta completa. Tendono a vedere la richiesta interrotta perché la risposta completa non è stata ricevuta. Inoltre, questi monitor raramente distinguono tra la richiesta o la risposta interrotta. In genere, il monitor di un pacchetto indipendente visualizza messaggi più dettagliati e segnala lo stato in modo più preciso. Ad esempio, un utente potrebbe ricevere un messaggio in *Charles* che indica che il client ha chiuso la connessione prima di ricevere l&#39;intera risposta. Ciò significa che i dati hanno effettivamente raggiunto i nostri server, solo che il browser è passato alla pagina successiva prima che il pixel 1x1 venisse ricevuto.

Se un sistema di monitoraggio dei pacchetti esterno segnala che la richiesta di raccolta dati è stata interrotta, anziché la risposta, si tratta di un problema. Adobe [!DNL Customer Care] può fornire assistenza nella risoluzione dei problemi.
