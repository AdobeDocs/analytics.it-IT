---
title: doPlugins
description: Configura la logica immediatamente prima che un hit venga compilato e inviato ad Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# doPlugins

La `doPlugins` funge da &quot;ultima chiamata&quot; per impostare i valori nell’implementazione. Se [`usePlugins`](../config-vars/useplugins.md) viene attivato, viene eseguito automaticamente immediatamente prima che qualsiasi tipo di richiesta di immagine venga compilata e inviata ad Adobe, tra cui:

* Visualizzazione di tutte le pagine ([`t()`](t-method.md)) chiamate
* Tracciamento di tutti i collegamenti ([`tl()`](tl-method.md)) chiamate , compresi i collegamenti di download e di uscita automatici

Utilizza la `doPlugins` per chiamare il codice plug-in e impostare i valori della variabile finale poco prima che una richiesta di immagine venga compilata e inviata ad Adobe.

## Plug-in tramite tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.doPlugins in AppMeasurement e codice personalizzato

Imposta la `s.doPlugins` a una funzione contenente il codice desiderato. La funzione viene eseguita automaticamente quando effettui una chiamata di tracciamento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>Imposta una funzione su `doPlugins` una sola volta nell&#39;implementazione. Se imposti la `doPlugins` più di una volta, viene utilizzato solo il codice più recente.

## Esempi

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>Le versioni precedenti di AppMeasurement erano leggermente diverse `doPlugins()` codice. Adobe consiglia di utilizzare il formato di cui sopra come best practice.
