---
title: registerPostTrackCallback
description: Crea funzioni di callback dopo l’invio di un hit ad Adobe.
feature: Variables
exl-id: b2124b89-2bab-4cca-878c-18d62377a8f3
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---

# registerPostTrackCallback

La `registerPostTrackCallback` consente alla tua organizzazione di collegare una funzione JavaScript immediatamente dopo che un hit è stato inviato correttamente ad Adobe. Se una chiamata di tracciamento non riesce, questa funzione non viene eseguita. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un&#39;infrastruttura interna oppure per pulire i valori delle variabili nelle applicazioni a pagina singola.

>[!WARNING]
>
>Non chiamare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all&#39;interno del `registerPostTrackCallback` variabile. Le funzioni di tracciamento in questa variabile causano un ciclo infinito di richieste di immagini!

Ogni volta che si chiama il `registerPostTrackCallback` aggancia la funzione per l’esecuzione immediatamente dopo il corretto invio di una richiesta di immagine. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>Tempi e ordine delle funzioni attivate tra [`registerPreTrackCallback`](registerpretrackcallback.md) e `registerPostTrackCallback` non sono garantite. Evita le dipendenze tra queste due funzioni.

## Registra callback di post utilizzando i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.registerPostTrackCallback in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.registerPostTrackCallback` è una funzione che utilizza una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente dopo il corretto invio di una richiesta di immagine.

```js
s.registerPostTrackCallback(function(){/* Desired code */});
```

Se desideri utilizzare l’URL della richiesta di immagine nel tuo codice, fai riferimento alla `requestUrl` argomento string all&#39;interno della funzione nidificata. È possibile analizzare i `requestUrl` variabile per l’uso desiderato; la regolazione di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPostTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Ulteriori argomenti possono essere inclusi nella `s.registerPostTrackCallback` , che può essere utilizzato nella funzione nidificata:

```js
s.registerPostTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

## Esempio di caso d’uso

Registrazione del [`clearVars()`](clearvars.md) la funzione nel callback di tracciamento può essere utile per le applicazioni a pagina singola. Ogni volta che invii correttamente un hit ad Adobe, la `clearVars()` viene eseguita la funzione . L’implementazione può quindi definire di nuovo le variabili senza preoccuparsi di valori persistenti in modo errato.

```js
s.registerPostTrackCallback(function(){s.clearVars();});
```
