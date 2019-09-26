---
description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
keywords: Implementazione di Analytics
seo-description: Le variabili dinamiche consentono di copiare i valori da una variabile all’altra senza digitare più volte i valori completi nelle richieste di immagini sul sito.
solution: null
title: Variabili dinamiche
translation-type: tm+mt
source-git-commit: 60dd1b300035e5149f53870239de85fb3174a77a

---


# s.registerPreTrackCallback and s.registerPostTrackCallback

These functions take as parameters: the callback (a function), and the parameters to that function. Ad esempio:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

La callback viene richiamata con i parametri `requestUrl` e tutti quelli passati quando la callback viene registrata. This occurs either before or after the tracking call, depending on which method is used to register the callback.

L'ordine in cui vengono chiamate queste callback non è garantito. I callback registrati nella funzione pre vengono richiamati dopo la creazione dell'URL di tracciamento finale. Le callback di post vengono richiamate a una chiamata di tracciamento riuscita (se la chiamata di tracciamento non riesce, queste funzioni non vengono chiamate). Qualsiasi callback registrato con `registerPreTrackCallback` non influisce sulla chiamata di tracciamento. Inoltre, non è consigliabile chiamare uno dei metodi di tracciamento in qualsiasi callback registrato e potrebbe causare un ciclo infinito.
