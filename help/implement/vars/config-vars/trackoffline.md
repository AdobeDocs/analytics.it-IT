---
title: trackOffline
description: Abilita o disabilita il tracciamento offline, che cambia il modo in cui AppMeasurement raccoglie i dati.
feature: Appmeasurement Implementation
exl-id: 23a17ddc-01e6-42b6-81b0-c60f15a07231
role: Admin, Developer
TQID: https://experienceleague.adobe.com/xAeUI6N625MJfnAWWO53NkBe4IKxI-i703vHHoxpuzg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 283
ht-degree: 8%

---

# trackOffline

Il tracciamento offline è un modo facoltativo per raccogliere i dati in Adobe Analytics. Se un visitatore si disconnette da Internet ma continua a navigare nel sito, gli hit vengono memorizzati in una coda offline fino a quando il dispositivo non si riconnette a Internet. Il tracciamento offline viene utilizzato principalmente per le app mobili.

La variabile `trackOffline` determina se utilizzare il tracciamento offline nell&#39;implementazione.

>[!WARNING]
>
>Devi configurare la suite di rapporti in modo da accettare hit con marca temporale prima di abilitare questa variabile. Se una suite di rapporti non accetta hit con marca temporale e questa variabile è abilitata, tali dati andranno persi e non potranno essere recuperati.

Quando è abilitata, AppMeasurement utilizza il seguente processo per inviare dati ad Adobe:

* Durante la compilazione di una richiesta di immagine, è incluso un parametro della stringa di query con marca temporale.
* Se il dispositivo non è in grado di raggiungere i server di raccolta dati di Adobe, l’hit viene memorizzato localmente sul dispositivo.
* Durante ogni hit successivo, AppMeasurement tenta di inviare una richiesta di immagine ad Adobe.
   * Se non riesce a raggiungere i server di raccolta dati di Adobe, l’hit viene aggiunto alla coda sul dispositivo.
   * Se è in grado di raggiungere i server di raccolta dati di Adobe, l’hit e la coda di hit mentre il dispositivo era offline vengono inviati.

## Tracciamento offline tramite Web SDK

Il Web SDK non supporta il tracciamento offline.

## Tracciamento offline tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.trackOffline in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.trackOffline` è un valore booleano che abilita o disabilita il tracciamento offline. Il valore predefinito è `false`. Impostare questo valore su `true` se si desidera abilitare il tracciamento offline.

```js
s.trackOffline = true;
```
