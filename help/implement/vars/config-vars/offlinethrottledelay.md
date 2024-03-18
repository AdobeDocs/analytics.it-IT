---
title: offlineThrottleDelay
description: Stabilisce la frequenza degli hit quando un dispositivo torna online.
feature: Variables
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 12%

---

# offlineThrottleDelay

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare nel sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le app mobili.

Quando un dispositivo torna online, tutti gli hit memorizzati sul dispositivo vengono inviati ai server di raccolta dati di Adobe. Un numero elevato di hit in coda può potenzialmente influire sulle prestazioni dei dispositivi meno recenti. Utilizza il `offlineThrottleDelay` per stabilire la frequenza con cui gli hit in coda vengono inviati all’Adobe.

## Ritardo della velocità offline tramite Web SDK

L’SDK per web non supporta il tracciamento offline.

## Ritardo della limitazione offline tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.offlineThrottleDelay in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.offlineThrottleDelay` la variabile è un numero intero che rappresenta il numero di millisecondi di attesa di AppMeasurement tra l’invio degli hit in coda. Il valore predefinito è `0`, il che significa che tutti gli hit in coda vengono inviati contemporaneamente. Se `trackOffline` è `false`, questa variabile non esegue alcuna operazione.

```js
s.offlineThrottleDelay = 500;
```
