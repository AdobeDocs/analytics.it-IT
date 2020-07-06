---
title: trackOffline
description: Abilita o disabilita il tracciamento offline, che modifica il modo in cui AppMeasurement raccoglie i dati.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---


# trackOffline

Il tracciamento offline è un metodo facoltativo per raccogliere dati in Adobe  Analytics. Se un visitatore si disconnette da Internet ma continua a sfogliare il sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le applicazioni mobili.

La `trackOffline` variabile determina se utilizzare il tracciamento offline nell&#39;implementazione.

>[!IMPORTANT]
>
>Prima di attivare questa variabile, devi configurare la suite di rapporti per accettare gli hit con marca temporale. Se una suite di rapporti non accetta gli hit con marca temporale e questa variabile è abilitata, i dati vanno persi e non possono essere recuperati.

Quando abilitata, AppMeasurement utilizza il seguente processo per inviare dati ad Adobe:

* Quando si compila una richiesta di immagine, viene incluso un parametro di stringa query per le marche temporali.
* Se il dispositivo non riesce a raggiungere i server di raccolta dati Adobe, l’hit viene memorizzato localmente sul dispositivo.
* Durante ogni hit successivo, AppMeasurement tenta di inviare una richiesta di immagine ad Adobe.
   * Se non riesce a raggiungere i server di raccolta dati Adobe, l’hit viene aggiunto alla coda del dispositivo.
   * Se può raggiungere i server di raccolta dati Adobe, l’hit e la coda degli hit mentre il dispositivo è offline vengono inviati.

## Tenere traccia offline in  lancio Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.trackOffline nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.trackOffline` variabile è un valore booleano che abilita o disabilita il tracciamento offline. Its default value is `false`. Impostate questo valore su `true` se desiderate abilitare il tracciamento offline.

```js
s.trackOffline = true;
```
