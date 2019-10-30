---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# s.registerPreTrackCallback e s.registerPostTrackCallback

Queste funzioni assumono come parametri: il callback (una funzione) e i parametri di tale funzione. Ad esempio:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

La callback viene richiamata con i parametri `requestUrl` e tutti quelli passati quando la callback viene registrata. Ciò si verifica prima o dopo la chiamata di tracciamento, a seconda del metodo utilizzato per registrare il callback.

L'ordine in cui vengono chiamate queste callback non è garantito. I callback registrati nella funzione pre vengono richiamati dopo la creazione dell'URL di tracciamento finale. Le callback di post vengono richiamate a una chiamata di tracciamento riuscita (se la chiamata di tracciamento non riesce, queste funzioni non vengono chiamate). Qualsiasi callback registrato con `registerPreTrackCallback` non influisce sulla chiamata di tracciamento. Inoltre, non è consigliabile chiamare uno dei metodi di tracciamento in qualsiasi callback registrato e potrebbe causare un ciclo infinito.
