---
title: offlineHitLimit
description: Determina il numero massimo di hit da mettere in coda per il tracciamento offline.
feature: Appmeasurement Implementation
exl-id: de6478b3-b95f-4edc-8427-7b915a46b3ba
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '193'
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
