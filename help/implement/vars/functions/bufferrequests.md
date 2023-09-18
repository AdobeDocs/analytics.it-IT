---
title: bufferRequests
description: Migliora l’affidabilità di acquisire richieste di tracciamento dei collegamenti per i browser che scaricano immediatamente la pagina.
feature: Variables
source-git-commit: d97e559e203182368bcbb62f51ef2c3e3bd025d3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 5%

---

# bufferRequests

Il `bufferRequests()` consente di memorizzare nella cache le richieste di immagini sulla pagina corrente invece di inviarle ad Adobe. L’attivazione di questo metodo è utile negli scenari in cui un browser non supporta [`navigator.sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon) o in caso contrario annulla le richieste di immagini quando viene scaricata una pagina. Molte versioni dei browser WebKit, come Safari, mostrano in genere il comportamento di interruzione di una richiesta di immagine quando si fa clic su un collegamento. Il `bufferRequests()` Il metodo è disponibile in tutte le versioni di AppMeasurement v2.25.0 o successive.

Quando chiami [`t()`](t-method.md) o [`tl()`](tl-method.md) in una pagina successiva nella stessa sessione del browser e `bufferRequests()` non è ancora stato chiamato su quella pagina, tutte le richieste nel buffer vengono inviate in aggiunta alla richiesta di immagine della pagina. Le richieste con buffer vengono inviate nell’ordine corretto, dove la richiesta di immagine della pagina corrente viene inviata per ultima.

>[!TIP]
>
>La marca temporale delle richieste nel buffer viene condivisa con la pagina a cui vengono inviati i dati. Se desideri maggiore precisione nel secondo esatto in cui viene registrata una richiesta inserita nel buffer, puoi impostare [`timestamp`](../page-vars/timestamp.md) variabile di pagina prima del buffering della richiesta. Se utilizzi questa variabile, assicurati che [Marca temporale opzionale](/help/technotes/timestamps-optional.md) è abilitato - in caso contrario, tutti gli hit con marca temporale andranno persi definitivamente!

## Limitazioni

Quando si chiama `bufferRequests()` tenete presenti le seguenti limitazioni. Poiché questo metodo utilizza [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), si applicano molte delle stesse limitazioni:

* Il collegamento di destinazione deve trovarsi nello stesso dominio e sottodominio. Le richieste con buffer non funzionano tra domini o sottodomini, anche se entrambi hanno la stessa implementazione di Adobe Analytics. Questa limitazione significa anche che non è possibile utilizzare richieste nel buffer per tenere traccia dei collegamenti di uscita.
* Il collegamento di destinazione deve utilizzare lo stesso protocollo della pagina corrente. Non è possibile inviare richieste nel buffer tra HTTP e HTTPS.
* Le richieste nel buffer vengono memorizzate fino alla chiamata `t()` o `tl()` senza chiamare `bufferRequests()` oppure fino alla chiusura del browser o della scheda. Se una sessione del browser termina prima che tu possa inviare tali dati ad Adobe, le richieste buffered non inviate vengono perse definitivamente.
* Se un browser non supporta [API di archiviazione web](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) o [API JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), un avviso viene inviato alla console del browser e un AppMeasurement tenta di inviare immediatamente la richiesta di immagine utilizzando `t()` metodo.

## Richieste nel buffer nell’SDK per web

L’SDK per web attualmente non offre la possibilità di eseguire il buffer delle richieste.

## Richieste bufferizzate tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.bufferRequests() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `bufferRequests()` metodo prima della chiamata `t()` o `tl()`. Quando `bufferRequests()` viene chiamato, le chiamate di tracciamento successive vengono scritte nell’archiviazione della sessione invece di essere inviate ai server di raccolta dati Adobe.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// Flag the request to be buffered
s.bufferRequests();

// The t() or tl() method then writes the data to session storage instead of sending it to Adobe
s.tl(true,"o","Example link click");

// On a subsequent page, the tracking call sends both the above link tracking call and the page view call
s.t();
```

<!-- TODO: insert a link to this page in AppMeasurement release notes, and also add content to Analytics release notes -->