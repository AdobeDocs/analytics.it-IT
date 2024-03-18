---
title: offlineHitLimit
description: Determina il numero massimo di hit da mettere in coda per il tracciamento offline.
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 12347957a7a51dc1f8dfb46d489b59a450c2745a
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 14%

---

# offlineHitLimit

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare nel sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le app mobili.

Il `offlineHitLimit` La variabile limita il numero di hit archiviati localmente dal dispositivo. Questa variabile funziona solo se [`trackOffline`](trackoffline.md) è abilitato.

## Limite di hit offline tramite Web SDK

L’SDK per web non supporta il tracciamento offline.

## Limite di hit offline tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.offlineHitLimit in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.offlineHitLimit` variabile è un numero intero che rappresenta il numero massimo di hit memorizzati da un dispositivo mentre è offline. Se questa variabile non è definita, non esiste alcun limite al numero di hit archiviati da un dispositivo in modalità offline.

```js
s.offlineHitLimit = 100;
```
