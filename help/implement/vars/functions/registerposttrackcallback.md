---
title: registerPostTrackCallback
description: Crea funzioni di callback dopo l’invio di un hit ad Adobe.
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# registerPostTrackCallback

La variabile `registerPostTrackCallback` consente alla tua organizzazione di collegare una funzione JavaScript immediatamente dopo che un hit è stato inviato all’Adobe. Se una chiamata di tracciamento non riesce, questa funzione non viene eseguita. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un&#39;infrastruttura interna oppure per pulire i valori delle variabili nelle applicazioni a pagina singola.

>[!IMPORTANT]
>
>Non chiamare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all&#39;interno della variabile `registerPostTrackCallback`. Le funzioni di tracciamento in questa variabile causano un ciclo infinito di richieste di immagini!

Ogni volta che si chiama la variabile `registerPostTrackCallback`, si aggancia la funzione per eseguirla immediatamente dopo che una richiesta di immagine è stata inviata correttamente. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>La tempistica e l&#39;ordine delle funzioni attivate tra [`registerPreTrackCallback`](registerpretrackcallback.md) e `registerPostTrackCallback` non sono garantiti. Evita le dipendenze tra queste due funzioni.

## Registra callback di post utilizzando i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.registerPostTrackCallback in AppMeasurement e nell&#39;editor di codice personalizzato

La funzione `s.registerPostTrackCallback` assume una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente dopo il corretto invio di una richiesta di immagine.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Se desideri utilizzare l’URL della richiesta di immagine nel codice, fai riferimento all’argomento della stringa `requestUrl` all’interno della funzione nidificata. Puoi analizzare la variabile `requestUrl` per l’uso desiderato; la regolazione di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Ulteriori argomenti possono essere inclusi nella funzione `s.registerPostTrackCallback`, che può essere utilizzata nella funzione nidificata:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Esempio di caso d’uso

La registrazione della funzione [`clearVars()`](clearvars.md) nel callback post-track può essere utile per le applicazioni a pagina singola. Ogni volta che viene inviato correttamente un hit ad Adobe, la funzione `clearVars()` viene eseguita. L’implementazione può quindi definire nuovamente le variabili senza preoccuparsi di valori persistenti in modo errato.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
