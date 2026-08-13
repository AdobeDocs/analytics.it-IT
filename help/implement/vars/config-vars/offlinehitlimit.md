---
title: offlineHitLimit
description: Determina il numero massimo di hit da mettere in coda per il tracciamento offline.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/YaAPaPRLQ7YYxARVRBuxB1J25qeS8JTPbIO1Bj725YM'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 194
ht-degree: 12%

---

# offlineHitLimit

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare nel sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le app mobili.

La variabile `offlineHitLimit` limita il numero di hit archiviati localmente dal dispositivo. Questa variabile funziona solo se [`trackOffline`](trackoffline.md) è abilitato.

## Limite di hit offline tramite Web SDK

Il Web SDK non supporta il tracciamento offline.

## Limite di hit offline tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.offlineHitLimit in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.offlineHitLimit` è un numero intero che rappresenta il numero massimo di hit memorizzati da un dispositivo mentre è offline. Se la variabile non è definita, verrà utilizzato per impostazione predefinita `10`. È possibile impostarlo su qualsiasi valore intero. Quando imposti valori elevati, tieni presente i limiti di archiviazione locale nel browser di un visitatore. Questo limite è in genere di 5-10 MB.

```js
s.offlineHitLimit = 100;
```
