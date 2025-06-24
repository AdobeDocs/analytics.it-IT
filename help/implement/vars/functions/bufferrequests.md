---
title: bufferRequests
description: Migliora l’affidabilità di acquisire richieste di tracciamento dei collegamenti per i browser che scaricano immediatamente la pagina.
feature: Appmeasurement Implementation
exl-id: f103deb4-f449-4325-b1a0-23e58a3c9ba0
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 5%

---

# bufferRequests

Il metodo `bufferRequests()` consente di memorizzare nella cache le richieste di immagini nella pagina corrente invece di inviarle ad Adobe. L&#39;attivazione di questo metodo è utile negli scenari in cui un browser non supporta [`navigator.sendBeacon()`](https://developer.mozilla.org/en-US/docs/Web/API/Navigator/sendBeacon) o in cui le richieste di immagini vengono annullate in altro modo al momento del download di una pagina. Molte versioni dei browser WebKit, come Safari, mostrano in genere il comportamento di interruzione di una richiesta di immagine quando si fa clic su un collegamento. Il metodo `bufferRequests()` è disponibile in tutte le versioni di AppMeasurement v2.25.0 o versioni successive.

Quando chiami [`t()`](t-method.md) o [`tl()`](tl-method.md) in una pagina successiva nella stessa sessione del browser e `bufferRequests()` non è stato ancora chiamato in quella pagina, tutte le richieste nel buffer vengono inviate in aggiunta alla richiesta di immagine della pagina. Le richieste con buffer vengono inviate nell’ordine corretto, dove la richiesta di immagine della pagina corrente viene inviata per ultima.

>[!TIP]
>
>La marca temporale delle richieste nel buffer viene condivisa con la pagina a cui vengono inviati i dati. Se desideri maggiore precisione nel secondo esatto in cui viene registrata una richiesta nel buffer, puoi impostare la variabile di pagina [`timestamp`](../page-vars/timestamp.md) prima di inserire la richiesta nel buffer. Se utilizzi questa variabile, assicurati che [Marca temporale opzionale](/help/technotes/timestamps-optional.md) sia abilitato. In caso contrario, tutti gli hit con marca temporale andranno persi definitivamente.

## Limitazioni

Quando si chiama il metodo `bufferRequests()`, tenere presenti le seguenti limitazioni. Poiché questo metodo utilizza [`Window.sessionStorage`](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API), si applicano molte delle stesse limitazioni:

* Il collegamento di destinazione deve trovarsi nello stesso dominio e sottodominio. Le richieste con buffer non funzionano tra domini o sottodomini, anche se entrambi hanno la stessa implementazione di Adobe Analytics. Questa limitazione significa anche che non è possibile utilizzare richieste nel buffer per tenere traccia dei collegamenti di uscita.
* Il collegamento di destinazione deve utilizzare lo stesso protocollo della pagina corrente. Non è possibile inviare richieste nel buffer tra HTTP e HTTPS.
* Le richieste con buffer vengono archiviate fino a quando non si chiama `t()` o `tl()` senza prima chiamare `bufferRequests()` o fino alla chiusura del browser o della scheda. Se una sessione del browser termina prima che tu possa inviare tali dati ad Adobe, le richieste buffered non inviate vengono perse definitivamente.
* Se un browser non supporta l&#39;[API di archiviazione Web](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API) o l&#39;[API JSON](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/JSON), viene inviato un avviso alla console del browser e AppMeasurement tenta di inviare immediatamente la richiesta di immagine utilizzando il metodo `t()`.

## Richieste nel buffer nel Web SDK

Il Web SDK attualmente non offre la possibilità di eseguire il buffering delle richieste.

## Richieste bufferizzate tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.bufferRequests() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiamare il metodo `bufferRequests()` prima di chiamare `t()` o `tl()`. Quando si chiama `bufferRequests()`, le chiamate di tracciamento successive vengono scritte nell&#39;archiviazione della sessione anziché inviate ai server di raccolta dati di Adobe.

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
