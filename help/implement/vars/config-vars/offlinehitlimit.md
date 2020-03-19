---
title: offlineHitLimit
description: Determinare il numero massimo di hit da mettere in coda per il tracciamento offline.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# offlineHitLimit

Il tracciamento offline è un metodo facoltativo per raccogliere dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a sfogliare il sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le applicazioni mobili.

La `offlineHitLimit` variabile inserisce un limite al numero di hit memorizzati localmente dal dispositivo. Questa variabile funziona solo se [`trackOffline`](trackoffline.md) è abilitata.

## Limite hit offline in Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.offlineHitLimit in AppMeasurement e Launch editor di codice personalizzato

La `s.offlineHitLimit` variabile è un numero intero che rappresenta il numero massimo di hit che un dispositivo memorizza mentre è offline. Se questa variabile non è definita, non esiste alcun limite al numero di hit memorizzati da un dispositivo mentre è offline.

```js
s.offlineHitLimit = 100;
```
