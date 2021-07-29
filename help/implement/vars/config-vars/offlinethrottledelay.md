---
title: offlineThrottleDelay
description: Stabilisce la frequenza dei risultati quando un dispositivo torna online.
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 1%

---

# offlineThrottleDelay

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare sul sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le applicazioni mobili.

Quando un dispositivo torna online, tutti gli hit memorizzati sul dispositivo vengono inviati ai server di raccolta dati di Adobe. Un numero elevato di hit in coda può potenzialmente influire sulle prestazioni sui dispositivi meno recenti. Utilizza la variabile `offlineThrottleDelay` per stabilire la frequenza con cui gli hit in coda vengono inviati ad Adobe.

## Ritardo di limitazione offline tramite tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.offlineThrottleDelay in AppMeasurement e nell&#39;editor di codice personalizzato

La variabile `s.offlineThrottleDelay` è un numero intero che rappresenta il numero di millisecondi che AppMeasurement attende tra l&#39;invio di hit in coda. Il valore predefinito è `0`, ovvero tutti gli hit in coda vengono inviati in una sola volta. Se `trackOffline` è `false`, questa variabile non esegue alcuna operazione.

```js
s.offlineThrottleDelay = 500;
```
