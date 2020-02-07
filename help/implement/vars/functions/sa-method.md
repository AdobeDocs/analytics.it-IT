---
title: sa
description: Modifica la suite di rapporti in qualsiasi momento nell'implementazione.
translation-type: tm+mt
source-git-commit: f179292abae9cf7986d61da89a86e3e88111943e

---


# sa

Questo `sa` metodo consente di modificare in modo dinamico una suite di rapporti in qualsiasi momento della pagina. Se desiderate inviare dati a suite di rapporti diverse senza ricaricare la pagina, potete utilizzare questo metodo.

## Utilizzare il metodo sa in Adobe Experience Platform Launch

Non esiste un modo flessibile per cambiare la suite di rapporti nell&#39;interfaccia. Puoi impostare la suite di rapporti sotto il [!UICONTROL Library Management] pannello di controllo quando configuri l&#39;estensione Adobe Analytics. Tuttavia, non puoi modificare o aggiornare la suite di rapporti utilizzando le regole. Se vuoi aggiornare i valori della suite di rapporti dopo che sono stati impostati, usa l&#39;editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.sa() nell&#39;editor di codice personalizzato AppMeasurement e Launch

Chiama il `s.sa()` metodo per cambiare la suite di rapporti di destinazione. L&#39;unico argomento è una stringa contenente un ID suite di rapporti o più ID suite di rapporti delimitati da una virgola. L&#39;argomento ID suite di rapporti è obbligatorio. Non utilizzare spazi nell&#39;argomento stringa.

```js
s.sa("examplersid");
```

## Esempio

Puoi cambiare la suite di rapporti se l&#39;utente esegue un&#39;azione specifica sul tuo sito.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
