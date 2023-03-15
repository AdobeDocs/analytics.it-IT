---
title: trackOffline
description: Abilita o disabilita il tracciamento offline, che cambia il modo in cui AppMeasurement raccoglie i dati.
feature: Variables
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 8%

---

# trackOffline

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare nel sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le app mobili.

Il `trackOffline` variabile determina se desideri utilizzare il tracciamento offline nell’implementazione.

>[!WARNING]
>
>Devi configurare la suite di rapporti in modo da accettare hit con marca temporale prima di abilitare questa variabile. Se una suite di rapporti non accetta hit con marca temporale e questa variabile è abilitata, tali dati andranno persi e non potranno essere recuperati.

Quando è abilitato, AppMeasurement utilizza la seguente procedura per inviare dati ad Adobe:

* Durante la compilazione di una richiesta di immagine, è incluso un parametro della stringa di query con marca temporale.
* Se il dispositivo non è in grado di raggiungere i server di raccolta dati Adobe, l’hit viene memorizzato localmente sul dispositivo.
* Durante ogni hit successivo, AppMeasurement tenta di inviare una richiesta di immagine all’Adobe.
   * Se non riesce a raggiungere i server di raccolta dati di Adobe, l’hit viene aggiunto alla coda sul dispositivo.
   * Se è in grado di raggiungere i server di raccolta dati di Adobe, l’hit e la coda di hit mentre il dispositivo era offline vengono inviati.

## Tracciamento offline tramite Web SDK

L’SDK per web non supporta il tracciamento offline.

## Tracciamento offline tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.trackOffline in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.trackOffline` variable è un valore booleano che abilita o disabilita il tracciamento offline. Il valore predefinito è `false`. Imposta questo valore su `true` se desideri abilitare il tracciamento offline.

```js
s.trackOffline = true;
```
