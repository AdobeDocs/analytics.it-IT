---
title: useBeacon
description: useBeacon consente di forzare AppMeasurement a utilizzare l’API sendBeacon dei browser
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# useBeacon

La maggior parte dei browser moderni includono il metodo nativo `navigator.sendBeacon()`. Invia in modo asincrono una piccola quantità di dati su HTTP a un server web. AppMeasurement può utilizzare il metodo `navigator.sendBeacon()` se la variabile `useBeacon` è abilitata. È utile per i collegamenti di uscita e altre situazioni in cui desideri inviare informazioni prima che la pagina si scarichi.

Se `useBeacon` è abilitato, l&#39;hit successivo inviato ad Adobe utilizza il metodo `navigator.sendBeacon()` del browser invece di una richiesta di immagine `GET` standard. Questa variabile si applica alle richieste di immagini [`s.t()`](../functions/t-method.md) e [`s.tl()`](../functions/tl-method.md). Richiede AppMeasurement 2.17.0 o versione successiva.

>[!TIP]
>
>AppMeasurement abilita automaticamente `useBeacon` per le richieste di immagini di link di uscita.

La variabile `useBeacon` viene ignorata quando il visitatore utilizza un browser che non supporta `navigator.sendBeacon()`. L&#39;utilizzo di questa variabile richiede AppMeasurement 2.16.0 o versione successiva.

## Utilizzare i beacon con con in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.useBeacon in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.useBeacon` è booleana che determina se AppMeasurement utilizza il metodo `navigator.sendBeacon()` del browser. Il valore predefinito è `false`. Imposta questa variabile su `true` prima di richiamare una funzione di tracciamento se desideri utilizzare la natura asincrona di `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Dopo l’esecuzione di una chiamata di tracciamento, questa variabile viene reimpostata su `false`. Se l’implementazione invia più richieste di immagini nello stesso caricamento della pagina (ad esempio applicazioni a pagina singola), imposta questa variabile su `true` prima di ogni chiamata di tracciamento.
