---
title: offlineThrottleDelay
description: Stabilisce la frequenza degli hit quando un dispositivo torna online.
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# offlineThrottleDelay

Il tracciamento offline è un metodo facoltativo per raccogliere dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a sfogliare il sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le applicazioni mobili.

Quando un dispositivo torna online, tutti gli hit memorizzati sul dispositivo vengono inviati ai server di raccolta dati Adobe. Un elevato numero di hit in coda può potenzialmente influire sulle prestazioni sui dispositivi meno recenti. Utilizzate la `offlineThrottleDelay` variabile per stabilire la frequenza con cui gli hit in coda vengono inviati ad Adobe.

## Ritardo di limitazione offline in Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.offlineThrottleDelay in AppMeasurement e Avvia editor di codice personalizzato

La `s.offlineThrottleDelay` variabile è un numero intero che rappresenta il numero di millisecondi di attesa di AppMeasurement tra gli hit in coda inviati. Il valore predefinito è `0`, ovvero tutti gli hit in coda vengono inviati contemporaneamente. Se `trackOffline` è `false`, questa variabile non esegue alcuna operazione.

```js
s.offlineThrottleDelay = 500;
```
