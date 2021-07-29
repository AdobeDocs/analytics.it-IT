---
title: doPlugins
description: Configura la logica immediatamente prima che un hit venga compilato e inviato ad Adobe.
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 1%

---

# doPlugins

La variabile `doPlugins` funge da &quot;ultima chiamata&quot; per impostare i valori nell’implementazione. Se [`usePlugins`](../config-vars/useplugins.md) è abilitato, viene eseguito automaticamente poco prima che qualsiasi tipo di richiesta di immagine venga compilata e inviata ad Adobe, tra cui:

* Tutte le chiamate di visualizzazione pagina ([`t()`](t-method.md))
* Tutte le chiamate di tracciamento dei collegamenti ([`tl()`](tl-method.md)), inclusi i collegamenti di download automatici e i collegamenti di uscita

Utilizza la variabile `doPlugins` per chiamare il codice plug-in e impostare i valori della variabile finale poco prima che una richiesta di immagine venga compilata e inviata ad Adobe.

## Plug-in tramite tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.doPlugins in AppMeasurement e codice personalizzato

Imposta la variabile `s.doPlugins` su una funzione contenente il codice desiderato. La funzione viene eseguita automaticamente quando effettui una chiamata di tracciamento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>Imposta una funzione sulla variabile `doPlugins` una sola volta nell&#39;implementazione. Se imposti la variabile `doPlugins` più di una volta, viene utilizzato solo il codice più recente.

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
>Le versioni precedenti di AppMeasurement avevano un codice leggermente diverso `doPlugins()`. Adobe consiglia di utilizzare il formato di cui sopra come best practice.
