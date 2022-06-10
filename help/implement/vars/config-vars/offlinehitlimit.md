---
title: offlineHitLimit
description: Determina il numero massimo di hit da mettere in coda per il tracciamento offline.
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 1%

---

# offlineHitLimit

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare sul sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le applicazioni mobili.

La `offlineHitLimit` inserisce un limite al numero di hit memorizzati localmente dal dispositivo. Questa variabile funziona solo se [`trackOffline`](trackoffline.md) è abilitato.

## Limite hit offline utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.offlineHitLimit in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La `s.offlineHitLimit` variabile è un numero intero che rappresenta il numero massimo di hit memorizzati da un dispositivo mentre è offline. Se questa variabile non è definita, non esiste alcun limite al numero di hit memorizzati da un dispositivo offline.

```js
s.offlineHitLimit = 100;
```
