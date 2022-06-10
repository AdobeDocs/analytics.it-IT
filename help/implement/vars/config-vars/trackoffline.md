---
title: trackOffline
description: Abilita o disabilita il tracciamento offline, che modifica il modo in cui AppMeasurement raccoglie i dati.
feature: Variables
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 0%

---

# trackOffline

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare sul sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le applicazioni mobili.

La `trackOffline` determina se desideri utilizzare il tracciamento offline nell&#39;implementazione.

>[!WARNING]
>
>Prima di abilitare questa variabile, devi configurare la suite di rapporti per accettare gli hit con marca temporale. Se una suite di rapporti non accetta gli hit con marca temporale e questa variabile è abilitata, i dati vengono persi e non possono essere recuperati.

Quando abilitato, AppMeasurement utilizza il seguente processo per inviare dati ad Adobe:

* Quando si compila una richiesta di immagine, viene incluso un parametro della stringa di query sulle marche temporali.
* Se il dispositivo non è in grado di raggiungere i server di raccolta dati di Adobe, l&#39;hit viene memorizzato localmente sul dispositivo.
* Durante ogni hit successivo, AppMeasurement tenta di inviare una richiesta di immagine ad Adobe.
   * Se non è in grado di raggiungere i server di raccolta dati di Adobe, l&#39;hit viene aggiunto alla coda del dispositivo.
   * Se può raggiungere i server di raccolta dati di Adobe, l&#39;hit e la coda degli hit mentre il dispositivo è offline vengono inviati.

## Tracciamento offline tramite SDK per web

L&#39;SDK per web non supporta il tracciamento offline.

## Tracciamento offline tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.trackOffline in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.trackOffline` è un valore booleano che abilita o disabilita il tracciamento offline. Il valore predefinito è `false`. Imposta questo valore su `true` per abilitare il tracciamento offline.

```js
s.trackOffline = true;
```
