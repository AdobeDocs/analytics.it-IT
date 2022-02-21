---
title: registerPreTrackCallback
description: Crea funzioni di callback prima di inviare un hit ad Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# registerPreTrackCallback

La `registerPreTrackCallback` consente all’organizzazione di collegare una funzione JavaScript dopo che è stato compilato un URL di richiesta dell’immagine, ma prima che venga inviato. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un’infrastruttura interna.

>[!IMPORTANT]
>
>Non chiamare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all&#39;interno del [`registerPostTrackCallback`](registerposttrackcallback.md) variabile. Le funzioni di tracciamento in questa variabile causano un ciclo infinito di richieste di immagini!

Ogni volta che si chiama il `registerPreTrackCallback` aggancia la funzione per l&#39;esecuzione ogni volta che viene compilato un URL di richiesta immagine. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>Tempi e ordine delle funzioni attivate tra `registerPreTrackCallback` e `registerPostTrackCallback` non sono garantite. Evita le dipendenze tra queste due funzioni.

## Registra pre-callback utilizzando i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.registerPreTrackCallback in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.registerPreTrackCallback` è una funzione che utilizza una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente prima dell’invio di una richiesta di immagine.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Se desideri utilizzare l’URL della richiesta di immagine nel tuo codice, fai riferimento alla `requestUrl` argomento string all&#39;interno della funzione nidificata. È possibile analizzare i `requestUrl` variabile per l’uso desiderato; la regolazione di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

È possibile includere argomenti aggiuntivi nella `s.registerPreTrackCallback` , che può essere utilizzato nella funzione nidificata:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>Impostazione delle variabili di pagina o modifica della variabile `requestUrl` stringa all&#39;interno di questa funzione do **not** influisce sulla richiesta di immagine inviata poco dopo questa chiamata alla funzione. Utilizza la [`doPlugins()`](doplugins.md) invece.
