---
title: sa
description: Modifica la suite di rapporti in qualsiasi momento dell’implementazione.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 1%

---

# sa

La `sa()` consente di modificare dinamicamente una suite di rapporti in qualsiasi momento della pagina. Se desideri inviare dati a suite di rapporti diverse senza ricaricare la pagina, puoi utilizzare questo metodo.

## Utilizzare il metodo sa utilizzando i tag in Adobe Experience Platform

Non esiste un modo flessibile per modificare la suite di rapporti nell’interfaccia di . Puoi impostare la suite di rapporti in [!UICONTROL Library Management] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics. Tuttavia, non puoi modificare o aggiornare la suite di rapporti utilizzando le regole. Se desideri aggiornare i valori della suite di rapporti dopo averli impostati, utilizza l’editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.sa() in AppMeasurement e nell&#39;editor di codice personalizzato

Chiama il `s.sa()` per modificare la suite di rapporti di destinazione. L&#39;unico argomento è una stringa contenente un ID suite di rapporti o più ID suite di rapporti delimitati da una virgola. L’argomento ID suite di rapporti è obbligatorio. Non utilizzare spazi nell&#39;argomento stringa.

```js
s.sa("examplersid");
```

## Esempio

Puoi modificare la suite di rapporti se l’utente esegue un’azione specifica sul sito.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
