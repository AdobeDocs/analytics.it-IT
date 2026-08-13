---
title: offlineThrottleDelay
description: Stabilisce la frequenza degli hit quando un dispositivo torna online.
feature: Appmeasurement Implementation
exl-id: fa484638-bb1f-4df9-9ba1-e9763fa6ad27
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/FiC4yXkRmNoY0PPO9ouC8-hX5xqWhkbcDVht5f05Yqk'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 195
ht-degree: 12%

---

# offlineThrottleDelay

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare nel sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le app mobili.

Quando un dispositivo torna online, tutti gli hit memorizzati sul dispositivo vengono inviati ai server di raccolta dati di Adobe. Un numero elevato di hit in coda può potenzialmente influire sulle prestazioni dei dispositivi meno recenti. Utilizza la variabile `offlineThrottleDelay` per stabilire la frequenza con cui gli hit in coda vengono inviati ad Adobe.

## Ritardo della velocità offline tramite Web SDK

Il Web SDK non supporta il tracciamento offline.

## Ritardo della limitazione offline tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.offlineThrottleDelay in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.offlineThrottleDelay` è un numero intero che rappresenta il numero di millisecondi di attesa di AppMeasurement tra l&#39;invio degli hit in coda. Il valore predefinito è `0`, il che significa che tutti gli hit in coda vengono inviati contemporaneamente. Se `trackOffline` è `false`, questa variabile non esegue alcuna operazione.

```js
s.offlineThrottleDelay = 500;
```
