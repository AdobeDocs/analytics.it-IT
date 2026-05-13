---
title: linkTrackEvents
description: Determina quali eventi includere nelle richieste di immagini per il tracciamento dei collegamenti.
feature: Appmeasurement Implementation
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
TQID: https://experienceleague.adobe.com/7BKaDxchTRu39doWzm8f32DOemgpvj1s-4uzfjJkOEA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: df312454-73c4-43f6-a90e-18f5043f074c
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 325
ht-degree: 2%

---

# linkTrackEvents

Alcune implementazioni non desiderano includere tutte le variabili in tutte le richieste di immagini di tracciamento dei collegamenti. Utilizzare le variabili [`linkTrackVars`](linktrackvars.md) e `linkTrackEvents` per includere selettivamente dimensioni e metriche nelle chiamate di [`tl()`](../functions/tl-method.md).

Questa variabile non viene utilizzata per le chiamate di visualizzazione pagina (metodo [`t()`](../functions/t-method.md)).

## Determinare quali eventi di Analytics includere in un evento XDM utilizzando il Web SDK

Il Web SDK non esclude alcuni campi per le chiamate di tracciamento dei collegamenti. Tuttavia, è possibile utilizzare il callback `onBeforeEventSend` per cancellare o impostare i campi desiderati prima che i dati vengano inviati ad Adobe. Per ulteriori informazioni, vedere [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) nella documentazione di Web SDK.

## Eventi nelle chiamate di tracciamento dei collegamenti tramite l’estensione Adobe Analytics

Se non utilizzi un codice personalizzato, Adobe Experience Platform include automaticamente gli eventi definiti negli hit di tracciamento dei collegamenti.

>[!IMPORTANT]
>
>Se si impostano gli eventi nell&#39;editor di codice personalizzato dell&#39;estensione Analytics, è necessario includere l&#39;evento anche in `linkTrackEvents` utilizzando il codice personalizzato.

## s.linkTrackEvents in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.linkTrackEvents` è una stringa contenente un elenco delimitato da virgole di eventi da includere nelle richieste di immagini di tracciamento dei collegamenti (metodo `tl()`). Per includere le metriche negli hit di tracciamento dei collegamenti è necessario soddisfare i tre criteri seguenti:

* Impostare l&#39;evento desiderato nella variabile [`events`](../page-vars/events/events-overview.md). Ad esempio: `s.events = "event1";`.
* Imposta la variabile `events` in `linkTrackVars`. Ad esempio: `s.linkTrackVars = "events";`.
* Impostare l&#39;evento desiderato nella variabile `linkTrackEvents`. Ad esempio: `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

Il valore predefinito per questa variabile è una stringa vuota. Se questa variabile non è definita, tutti gli eventi sono inclusi nelle richieste di immagini per il tracciamento dei collegamenti. La Raccolta dati popola automaticamente questa variabile in base agli eventi impostati nell’interfaccia, in modo che sia sempre impostata per le implementazioni che utilizzano i tag in Adobe Experience Platform.

>[!TIP]
>
>Evitare di utilizzare l&#39;identificatore di oggetto di Analytics (`s.`) quando si specificano eventi in questa variabile. `s.linkTrackEvents = "event1";`, ad esempio, è corretto, mentre `s.linkTrackEvents = "s.event1";` non è corretto.

## Esempio

La funzione di tracciamento dei collegamenti seguente include solo `event1` (non `event2`) nella richiesta di immagine inviata ad Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
