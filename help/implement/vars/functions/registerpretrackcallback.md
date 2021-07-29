---
title: registerPreTrackCallback
description: Crea funzioni di callback prima di inviare un hit ad Adobe.
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '265'
ht-degree: 0%

---

# registerPreTrackCallback

La variabile `registerPreTrackCallback` consente alla tua organizzazione di collegare una funzione JavaScript dopo che un URL di richiesta di immagine è stato compilato ma prima che venga inviato. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un’infrastruttura interna.

>[!IMPORTANT]
>
>Non chiamare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all&#39;interno della variabile [`registerPostTrackCallback`](registerposttrackcallback.md). Le funzioni di tracciamento in questa variabile causano un ciclo infinito di richieste di immagini!

Ogni volta che si chiama la variabile `registerPreTrackCallback`, si aggancia tale funzione per eseguire ogni volta che viene compilato un URL di richiesta di immagine. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>La tempistica e l&#39;ordine delle funzioni attivate tra `registerPreTrackCallback` e `registerPostTrackCallback` non sono garantiti. Evita le dipendenze tra queste due funzioni.

## Registra pre-callback utilizzando i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.registerPreTrackCallback in AppMeasurement e nell&#39;editor di codice personalizzato

La funzione `s.registerPreTrackCallback` assume una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente prima dell’invio di una richiesta di immagine.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Se desideri utilizzare l’URL della richiesta di immagine nel codice, fai riferimento all’argomento della stringa `requestUrl` all’interno della funzione nidificata. Puoi analizzare la variabile `requestUrl` per l’uso desiderato; la regolazione di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

È possibile includere argomenti aggiuntivi nella funzione `s.registerPreTrackCallback`, che possono essere utilizzati nella funzione nidificata:

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
>L&#39;impostazione delle variabili di pagina o la modifica della stringa `requestUrl` all&#39;interno di questa funzione hanno un impatto su **non** la richiesta di immagine inviata poco dopo questa chiamata di funzione. Utilizza invece la variabile [`doPlugins()`](doplugins.md) .
