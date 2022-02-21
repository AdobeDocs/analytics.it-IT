---
title: offlineHitLimit
description: Determina il numero massimo di hit da mettere in coda per il tracciamento offline.
feature: Variables
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '158'
ht-degree: 1%

---

# offlineHitLimit

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare sul sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le applicazioni mobili.

La `offlineHitLimit` inserisce un limite al numero di hit memorizzati localmente dal dispositivo. Questa variabile funziona solo se [`trackOffline`](trackoffline.md) è abilitato.

## Limite hit offline utilizzando i tag in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.offlineHitLimit in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.offlineHitLimit` variabile è un numero intero che rappresenta il numero massimo di hit memorizzati da un dispositivo mentre è offline. Se questa variabile non è definita, non esiste alcun limite al numero di hit memorizzati da un dispositivo offline.

```js
s.offlineHitLimit = 100;
```
