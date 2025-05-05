---
title: linkTrackEvents
description: Determina quali eventi includere nelle richieste di immagini per il tracciamento dei collegamenti.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '313'
ht-degree: 2%

---

# linkTrackEvents

Alcune implementazioni non desiderano includere tutte le variabili in tutte le richieste di immagini di tracciamento dei collegamenti. Utilizzare le variabili [`linkTrackVars`](linktrackvars.md) e `linkTrackEvents` per includere selettivamente dimensioni e metriche nelle chiamate di [`tl()`](../functions/tl-method.md).

Questa variabile non viene utilizzata per le chiamate di visualizzazione pagina (metodo [`t()`](../functions/t-method.md)).

## Determinare quali eventi di Analytics includere in un evento XDM utilizzando l’SDK per web

L’SDK per web non esclude alcuni campi per le chiamate di tracciamento dei collegamenti. Tuttavia, è possibile utilizzare il callback `onBeforeEventSend` per cancellare o impostare i campi desiderati prima che i dati vengano inviati ad Adobe. Per ulteriori informazioni, consulta [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=it#modifying-events-globally) nella documentazione di Web SDK.

## Eventi nelle chiamate di tracciamento dei collegamenti tramite l’estensione Adobe Analytics

Se non utilizzi un codice personalizzato, Adobe Experience Platform include automaticamente gli eventi definiti negli hit di tracciamento dei collegamenti.

>[!IMPORTANT]
>
>Se si impostano gli eventi nell&#39;editor di codice personalizzato dell&#39;estensione Analytics, è necessario includere l&#39;evento anche in `linkTrackEvents` utilizzando il codice personalizzato.

## s.linkTrackEvents in AppMeasurement e l’editor di codice personalizzato dell’estensione Analytics

La variabile `s.linkTrackEvents` è una stringa contenente un elenco delimitato da virgole di eventi da includere nelle richieste di immagini di tracciamento dei collegamenti (metodo `tl()`). Per includere le metriche negli hit di tracciamento dei collegamenti è necessario soddisfare i tre criteri seguenti:

* Impostare l&#39;evento desiderato nella variabile [`events`](../page-vars/events/events-overview.md). Esempio: `s.events = "event1";`.
* Imposta la variabile `events` in `linkTrackVars`. Esempio: `s.linkTrackVars = "events";`.
* Impostare l&#39;evento desiderato nella variabile `linkTrackEvents`. Esempio: `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

Il valore predefinito per questa variabile è una stringa vuota. Se questa variabile non è definita, tutti gli eventi sono inclusi nelle richieste di immagini per il tracciamento dei collegamenti. La Raccolta dati popola automaticamente questa variabile in base agli eventi impostati nell’interfaccia, in modo che sia sempre impostata per le implementazioni che utilizzano i tag in Adobe Experience Platform.

>[!TIP]
>
>Evitare di utilizzare l&#39;identificatore di oggetto di Analytics (`s.`) quando si specificano eventi in questa variabile. `s.linkTrackEvents = "event1";`, ad esempio, è corretto, mentre `s.linkTrackEvents = "s.event1";` non è corretto.

## Esempio

La funzione di tracciamento dei collegamenti seguente include solo `event1` (non `event2`) nella richiesta di immagine inviata all&#39;Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
