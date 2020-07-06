---
title: registerPreTrackCallback
description: Create le funzioni di callback prima di inviare un hit ad Adobe.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '262'
ht-degree: 0%

---


# registerPreTrackCallback

La `registerPreTrackCallback` variabile consente all’organizzazione di collegare una funzione JavaScript dopo che l’URL di una richiesta di immagine è stato compilato ma prima che venga inviato. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un&#39;infrastruttura partner o interna.

>[!IMPORTANT]
>
>Non chiamare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all’interno della [`registerPostTrackCallback`](registerposttrackcallback.md) variabile. Le funzioni di tracciamento di questa variabile causano un numero infinito di richieste di immagini!

Ogni volta che chiamate la `registerPreTrackCallback` variabile, agganciate la funzione per l’esecuzione ogni volta che viene compilato l’URL di una richiesta di immagine. Evitare di registrare la stessa funzione più volte nello stesso caricamento di pagina.

>[!NOTE]
>
>I tempi e l&#39;ordine delle funzioni attivate tra `registerPreTrackCallback` e `registerPostTrackCallback` non sono garantiti. Evitare dipendenze tra queste due funzioni.

## Registra callback pre-traccia nel lancio  Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.registerPreTrackCallback in AppMeasurement e Avvia editor di codice personalizzato

Si `s.registerPreTrackCallback` tratta di una funzione che utilizza una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente prima dell&#39;invio di una richiesta di immagine.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Se desiderate utilizzare l&#39;URL della richiesta di immagine nel codice, fate riferimento all&#39;argomento `requestUrl` stringa all&#39;interno della funzione nidificata. È possibile analizzare la `requestUrl` variabile per l&#39;uso desiderato; la modifica di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

È possibile includere argomenti aggiuntivi nella `s.registerPreTrackCallback` funzione, utilizzabili nella funzione nidificata:

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
>L&#39;impostazione di variabili di pagina o la modifica della `requestUrl` stringa all&#39;interno di questa funzione **non** influiscono sulla richiesta di immagine inviata subito dopo la chiamata di questa funzione. Utilizzare invece la [`doPlugins()`](doplugins.md) variabile.
