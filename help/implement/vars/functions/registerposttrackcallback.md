---
title: registerPostTrackCallback
description: Crea funzioni di callback dopo l’invio di un hit ad Adobe.
translation-type: tm+mt
source-git-commit: 0d7e7dcb2cc382d83e267e51b1abeff38da270d3
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---


# registerPostTrackCallback

La `registerPostTrackCallback` variabile consente all&#39;organizzazione di collegare una funzione JavaScript immediatamente dopo che un hit è stato inviato ad Adobe. Se una chiamata di tracciamento non riesce, questa funzione non viene eseguita. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un&#39;infrastruttura interna, oppure per ripulire i valori variabili nelle applicazioni a pagina singola.

>[!IMPORTANT] Non chiamare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all’interno della `registerPostTrackCallback` variabile. Le funzioni di tracciamento di questa variabile causano un numero infinito di richieste di immagini!

Ogni volta che si chiama la `registerPostTrackCallback` variabile, si aggancia la funzione per l’esecuzione immediatamente dopo l’invio di una richiesta di immagine. Evitare di registrare la stessa funzione più volte nello stesso caricamento di pagina.

>[!NOTE] I tempi e l&#39;ordine delle funzioni attivate tra [`registerPreTrackCallback`](registerpretrackcallback.md) e `registerPostTrackCallback` non sono garantiti. Evitare dipendenze tra queste due funzioni.

## Registra post-callback nel lancio  Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.registerPostTrackCallback in AppMeasurement e Avvia editor di codice personalizzato

Si `s.registerPostTrackCallback` tratta di una funzione che utilizza una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente dopo l&#39;invio corretto di una richiesta di immagine.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Se desiderate utilizzare l&#39;URL della richiesta di immagine nel codice, fate riferimento all&#39;argomento `requestUrl` stringa all&#39;interno della funzione nidificata. È possibile analizzare la `requestUrl` variabile per l&#39;uso desiderato; la modifica di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Ulteriori argomenti possono essere inclusi nella `s.registerPostTrackCallback` funzione, che può essere utilizzata nella funzione nidificata:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Esempio di caso di utilizzo

La registrazione della [`clearVars()`](clearvars.md) funzione nel callback post-traccia può essere utile per le applicazioni a pagina singola. Ogni volta che viene inviato un hit ad Adobe, la `clearVars()` funzione viene eseguita. L’implementazione può quindi definire di nuovo le variabili senza preoccuparsi di valori che persistono in modo errato.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
