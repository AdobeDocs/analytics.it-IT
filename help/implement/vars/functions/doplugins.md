---
title: doPlugins
description: Configura la logica immediatamente prima che un hit venga compilato e inviato ad Adobe.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---


# doPlugins

La `doPlugins` variabile funge da &#39;ultima chiamata&#39; per impostare i valori nell&#39;implementazione. Se [`usePlugins`](../config-vars/useplugins.md) è attivato, viene eseguito automaticamente subito prima che qualsiasi tipo di richiesta di immagine venga compilato e inviato ad Adobe, compresi:

* Tutte le chiamate della visualizzazione pagina ([`t()`](t-method.md)Visualizzazione pagina)
* Tutte le chiamate per il tracciamento dei collegamenti ([`tl()`](tl-method.md)), inclusi i collegamenti di download e di uscita automatici

Utilizzate la `doPlugins` variabile per chiamare il codice plug-in e impostare i valori della variabile finale appena prima che una richiesta di immagine venga compilata e inviata ad Adobe.

## Plug-in  lancio Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.doPlugins in AppMeasurement e Launch codice personalizzato

Impostare la `s.doPlugins` variabile su una funzione contenente il codice desiderato. La funzione viene eseguita automaticamente quando si effettua una chiamata di tracciamento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!NOTE]
>
>Impostate una funzione sulla `doPlugins` variabile una sola volta nell&#39;implementazione. Se impostate la `doPlugins` variabile più di una volta, viene utilizzato solo il codice più recente.

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
>Le versioni precedenti di AppMeasurement presentavano un `doPlugins()` codice leggermente diverso. Adobe consiglia di utilizzare il formato indicato sopra come procedura ottimale.
