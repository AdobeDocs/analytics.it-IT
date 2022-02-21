---
title: useBeacon
description: useBeacon consente di forzare AppMeasurement a utilizzare l’API sendBeacon dei browser
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# useBeacon

I browser più moderni includono il metodo nativo `navigator.sendBeacon()`. Invia in modo asincrono una piccola quantità di dati su HTTP a un server web. AppMeasurement può utilizzare il `navigator.sendBeacon()` se `useBeacon` è abilitata. È utile per i collegamenti di uscita e altre situazioni in cui desideri inviare informazioni prima che la pagina si scarichi.

Se `useBeacon` è abilitato, l&#39;hit successivo inviato ad Adobe utilizza l&#39; `navigator.sendBeacon()` metodo anziché standard `GET` richiesta immagine. Questa variabile si applica a entrambi [`s.t()`](../functions/t-method.md) e [`s.tl()`](../functions/tl-method.md) richieste di immagini. Richiede AppMeasurement 2.17.0 o versione successiva.

>[!TIP]
>
>AppMeasurement abilita automaticamente `useBeacon` per le richieste di immagini di link in uscita.

La `useBeacon` viene ignorata quando il visitatore utilizza un browser che non supporta `navigator.sendBeacon()`. L&#39;utilizzo di questa variabile richiede AppMeasurement 2.16.0 o versione successiva.

## Utilizzare i beacon con con in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.useBeacon in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.useBeacon` è una variabile booleana che determina se AppMeasurement utilizza l’ del browser `navigator.sendBeacon()` metodo . Il valore predefinito è `false`. Imposta questa variabile su `true` prima di richiamare una funzione di tracciamento se desideri utilizzare la natura asincrona di `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Dopo l’esecuzione di una chiamata di tracciamento, questa variabile viene reimpostata su `false`. Se l’implementazione invia più richieste di immagini nello stesso caricamento della pagina (ad esempio applicazioni a pagina singola), imposta questa variabile su `true` prima di ogni chiamata di tracciamento.
