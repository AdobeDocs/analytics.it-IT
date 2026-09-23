---
title: Implementazione di Analytics per gli assistenti digitali
description: Implementare Adobe Analytics sugli assistenti digitali, ad esempio Amazon Alexa o Google Home.
feature: Implementation Basics
exl-id: ebe29bc7-db34-4526-a3a5-43ed8704cfe9
role: Developer
TQID: 'https://experienceleague.adobe.com/QKlchx0r3ZDourRQaQAJaMn9Fh3bXiEWHprCkLVALsk'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: f801835bb65be97db52dfccd217ecba268230eea
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 11%
---
# Implementazione di Analytics per gli assistenti digitali

Con i progressi nel cloud computing, nell’apprendimento automatico e nell’elaborazione del linguaggio naturale, gli assistenti digitali fanno parte della vita quotidiana. I consumatori parlano con i loro dispositivi e si aspettano risposte simili a quelle umane, e i marchi possono presentare i loro servizi attraverso queste stesse esperienze. Ad esempio, i consumatori possono chiedere:

* “Alexa, chiedi alla mia macchina quando serve un cambio d’olio.”
* &quot;Ehi Google, qual è il saldo del mio conto corrente?&quot;
* “Siri, manda 20 € a John per cena di ieri sera dall’app della banca.”

Questa pagina fornisce una panoramica su come utilizzare Adobe Analytics per misurare e ottimizzare questi tipi di esperienze.

## Panoramica dell’architettura dell’esperienza digitale

![Flusso di lavoro dell’Assistente digitale](assets/Digital-Assitants.png)

La maggior parte degli assistenti digitali segue un’architettura di alto livello simile:

1. **Dispositivo**: dispositivo (ad esempio un altoparlante o un telefono) con microfono che consente all&#39;utente di porre una domanda.
1. **Assistente digitale**: il servizio che gestisce l&#39;assistente. Converte il riconoscimento vocale in intenti comprensibili dal computer e analizza i dettagli della richiesta. Una volta compresa l’intenzione, l’assistente la trasmette insieme ai relativi dettagli all’app che gestisce la richiesta.
1. **&quot;App&quot;**: un&#39;app sul telefono o un&#39;app vocale che risponde alla richiesta. Risponde all’assistente digitale, che risponde quindi all’utente.

## Invio dei dati ad Adobe Analytics

Un’app di assistente digitale viene in genere eseguita su un server o una piattaforma che non dispone di una libreria lato client di Adobe (AppMeasurement o Web SDK). Invia hit **lato server utilizzando [API di inserimento dati](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/)**. Ogni interazione da misurare diventa una richiesta API di inserimento dati la cui stringa di query (o corpo XML) contiene le variabili descritte in questa pagina, il più delle volte [variabili di dati di contesto](/help/implement/vars/page-vars/contextdata.md) mappate a eVar, prop ed eventi con [regole di elaborazione](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md).

Questa pagina si concentra su *cosa* misurare e come modellarlo in Analytics. Per l&#39;endpoint, la stringa di query e le codifiche XML, i componenti richiesti e i tipi di risposta, vedere la [documentazione API di inserimento dati](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/). Ogni variabile denominata di seguito corrisponde a un parametro della stringa di query e a un tag XML nel [riferimento variabile](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference).

## Dove implementare Analytics

Una delle posizioni migliori per implementare Analytics è all’interno dell’app, che riceve l’intento e i dettagli dall’assistente digitale e determina come rispondere. Durante una richiesta, ci sono due momenti che sono utili per inviare dati ad Adobe Analytics:

1. Quando la richiesta viene inviata all’app.
1. Dopo che la risposta viene restituita dall’app.

Se ti interessa registrare quello che è successo per un’ottimizzazione futura, invia l’hit dopo che la risposta è stata restituita: avrai quindi il contesto completo della richiesta e la risposta del sistema.

## Cosa misurare

### Nuove installazioni

Per gli assistenti che ti inviano una notifica quando qualcuno installa l&#39;abilità (in particolare quando è coinvolta l&#39;autenticazione), invia un evento di installazione impostando la variabile di dati di contesto `a.InstallEvent=1` insieme a `a.InstallDate` e l&#39;ID app (`a.AppID`). Questa funzione non è disponibile su tutte le piattaforme, ma è utile per l’analisi della conservazione quando presente.

### Più assistenti o app

Le organizzazioni spesso creano app per più piattaforme. Includi un ID app in ogni richiesta nella variabile di dati di contesto `a.AppID`, utilizzando il formato `[AppName] [BundleVersion]` (ad esempio, `Spoofify 1.0`). Aggiungere una variabile di dati di contesto del sistema operativo o della piattaforma (ad esempio `OSType`) per distinguere Alexa, l&#39;Assistente Google e altre piattaforme nel reporting.

### Identificazione del visitatore

Adobe Analytics utilizza il [servizio ID visitatore di Adobe](https://experienceleague.adobe.com/it/docs/id-service/using/home) per collegare nel tempo le interazioni alla stessa persona. La maggior parte degli assistenti digitali restituisce un `userID` che è possibile utilizzare come identificatore univoco. Passarlo come override dell&#39;ID visitatore (`vid`). Alcune piattaforme restituiscono un identificatore più lungo dei 100 caratteri consentiti; in questi casi, esegui l’hashing a un valore a lunghezza fissa con un algoritmo standard come MD5 o SHA-1.

L’utilizzo del servizio ID visitatore fornisce il massimo valore quando mappi gli ECID tra dispositivi (ad esempio, da web ad assistente digitale). Se utilizzi un&#39;app per dispositivi mobili, usa Experience Platform Mobile SDK e invia l&#39;ID utente con il metodo `setCustomerID`. Se la tua app è un servizio, usa l&#39;ID utente fornito dal servizio come ID visitatore e impostalo con `setCustomerID`. Per informazioni su come impostare gli identificatori in una richiesta lato server, consulta [Identificazione del visitatore tramite l&#39;API di inserimento dati](../id/data-insertion.md).

### Sessioni

Poiché gli assistenti digitali sono di tipo conversazionale, spesso hanno il concetto di sessione (scambio a più turni). All’avvio di una nuova sessione, Adobe consiglia due cose:

1. **Rivolgiti ad Audience Manager** per ottenere i segmenti a cui appartiene l&#39;utente, in modo da poter personalizzare la risposta.
1. **Inviare un evento di avvio** con la prima risposta impostando la variabile di dati di contesto `a.LaunchEvent=1`.

### Intenti

Ogni assistente rileva gli intenti e li trasmette all&#39;app. Un intento è una breve rappresentazione della richiesta, ad esempio &quot;Siri, invia a John 20 $ per la cena di ieri sera dalla mia app bancaria&quot; potrebbe risolvere l&#39;intento *sendMoney*. Invia ogni intento in una variabile di dati di contesto mappata su un eVar in modo da poter eseguire rapporti di percorsi tra intenti diversi. Assicurati che l&#39;app gestisca le richieste anche senza un intento; Adobe consiglia di inviare `No Intent Specified` invece di omettere la variabile.

### Parametri, slot ed entità

Oltre all’intento, gli assistenti forniscono spesso dettagli chiave/valore della richiesta (denominati slot, entità o parametri). Per &quot;Siri, invia a John 20 $ per la cena di ieri sera&quot;, i parametri potrebbero essere:

* Chi = John
* Importo = 20
* Perché = Cena

In genere esiste un set finito di questi per app. Inviali nelle variabili di dati di contesto e mappali su un eVar.

### Stati di errore

A volte l’assistente passa input che l’app non riesce a gestire (ad esempio, &quot;Siri, invia a John 20 sacchi di carbone dalla mia app bancaria&quot;). In questo caso, chiedere chiarimenti all&#39;app e inviare dati che indicano uno stato di errore, impostare `a.Error=1` insieme a un eVar che specifica il tipo di errore. Includi sia gli errori in cui gli input non sono validi sia gli errori in cui l’app stessa ha avuto un problema.

### Funzionalità del dispositivo

Anche se la maggior parte delle piattaforme non espone il dispositivo esatto, espongono le sue funzionalità (come Audio, Schermo o Video), che definiscono i tipi di contenuto utilizzabili. Quando si misurano le funzionalità dei dispositivi, concatenarle in ordine alfabetico con due punti iniziali e finali, ad esempio `":Audio:Camera:Screen:Video:"`, in modo da poter creare segmenti come &quot;tutti gli hit con funzionalità `:Audio:`&quot;.

* [Riferimento all’interfaccia di Amazon Alexa](https://developer.amazon.com/public/solutions/alexa/alexa-skills-kit/docs/alexa-skills-kit-interface-reference)
* [Funzionalità di superficie di Google Assistant](https://developers.google.com/actions/assistant/surface-capabilities)

## Richiesta di esempio

La seguente richiesta GET API di inserimento dati registra un intento *SendPayment* per un&#39;app bancaria, impostando come dati contestuali l&#39;ID dell&#39;app, un evento di avvio, l&#39;intento e i valori degli slot:

```text
GET /b/ss/examplersid1,examplersid2/1?vid=[UserID]&c.a.AppID=Penmo%201.0&c.a.LaunchEvent=1&c.Intent=SendPayment&c.Amount=20.00&c.Reason=Dinner&c.ReceivingPerson=John&pageName=SendPayment HTTP/1.1
Host: example.data.adobedc.net
```

Per il formato di richiesta completo, gli endpoint e i tipi di risposta, consulta la [documentazione sull&#39;API di inserimento dati](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/request).

## Esempio di modello di misurazione

La tabella seguente mostra come le azioni comuni in un’app musicale vengono associate alle variabili di Analytics. Imposta queste come variabili di dati di contesto in ogni richiesta API di inserimento dati, quindi mappale su eVar ed eventi con regole di elaborazione.

| Azione della persona | Intento/evento | Dati contestuali da impostare |
| --- | --- | --- |
| Installare l’app | Installa | `a.InstallEvent=1`, `a.InstallDate`, `a.AppID`, `OSType` |
| Avviare l’app | Launch | `a.LaunchEvent=1`, `a.AppID`, `Intent=Play` |
| Chiedi di cambiare la canzone | ChangeSong | `a.AppID`, `Intent=ChangeSong` |
| Riproduci una canzone specifica | ChangeSong | `a.AppID`, `Intent=ChangeSong`, `SongID` |
| Modificare la playlist | ChangePlaylist | `a.AppID`, `Intent=ChangePlaylist`, `Playlist` |
| Input non valido | (errore) | `a.Error=1`, `ErrorName` |
