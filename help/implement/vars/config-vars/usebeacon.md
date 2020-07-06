---
title: useBeacon
description: useBeacon consente di forzare AppMeasurement a utilizzare l'API sendBeacon dei browser
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---


# useBeacon

La maggior parte dei browser moderni include il metodo nativo `navigator.sendBeacon()`. Invia in modo asincrono una piccola quantità di dati su HTTP a un server Web. AppMeasurement può utilizzare il `navigator.sendBeacon()` metodo se la `useBeacon` variabile è abilitata. È utile per i collegamenti di uscita e altre situazioni in cui si desidera inviare informazioni prima che la pagina venga scaricata.

Se `useBeacon` è abilitata, l&#39;hit successivo inviato ad Adobe utilizza il metodo del browser `navigator.sendBeacon()` invece di una richiesta di `GET` immagine standard. Questa variabile si applica sia alle richieste [`s.t()`](../functions/t-method.md) che alle richieste di [`s.tl()`](../functions/tl-method.md) immagini. Richiede AppMeasurement 2.17.0 o versione successiva.

>[!TIP]
>
>AppMeasurement abilita automaticamente `useBeacon` le richieste di immagini di collegamento in uscita.

La `useBeacon` variabile viene ignorata quando il visitatore utilizza un browser che non supporta `navigator.sendBeacon()`. L&#39;utilizzo di questa variabile richiede AppMeasurement 2.16.0 o versione successiva.

## Usa beacon  lancio Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.useBeacon nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.useBeacon` variabile è un valore booleano che determina se AppMeasurement utilizza il `navigator.sendBeacon()` metodo del browser. Its default value is `false`. Impostate questa variabile su `true` prima di chiamare una funzione di tracciamento se desiderate utilizzare la natura asincrona di `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Dopo l’esecuzione di una chiamata di tracciamento, questa variabile viene reimpostata su `false`. Se l’implementazione invia più richieste di immagini nello stesso caricamento di pagina (ad esempio, applicazioni a pagina singola), imposta questa variabile `true` prima di ogni chiamata di tracciamento.
