---
title: linkTrackEvents
description: Determina gli eventi da includere nelle richieste di tracciamento dei collegamenti alle immagini.
feature: Variables
exl-id: 53c9e122-425c-4ec3-8a32-96e4d112f348
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 2%

---

# linkTrackEvents

Alcune implementazioni non vogliono includere tutte le variabili in tutte le richieste di immagini di tracciamento dei collegamenti. Utilizza la [`linkTrackVars`](linktrackvars.md) e `linkTrackEvents` variabili per includere in modo selettivo dimensioni e metriche in [`tl()`](../functions/tl-method.md) chiamate.

Questa variabile non viene utilizzata per le chiamate di visualizzazione della pagina ([`t()`](../functions/t-method.md) metodo).

## Determinare gli eventi di Analytics da includere in un evento XDM utilizzando l’SDK per web

L’SDK per web non esclude alcuni campi per le chiamate di tracciamento dei collegamenti. Tuttavia, puoi utilizzare la `onBeforeEventSend` callback per cancellare o impostare i campi desiderati prima dell’invio dei dati ad Adobe. Vedi [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione SDK per web .

## Eventi nelle chiamate di tracciamento dei collegamenti che utilizzano l&#39;estensione Adobe Analytics

Adobe Experience Platform include automaticamente gli eventi definiti negli hit di tracciamento dei collegamenti se non utilizzi codice personalizzato.

>[!IMPORTANT]
>
>Se imposti eventi nell’editor di codice personalizzato dell’estensione Analytics, devi includere l’evento in `linkTrackEvents` utilizzando anche codice personalizzato.

## s.linkTrackEvents in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.linkTrackEvents` è una stringa contenente un elenco delimitato da virgole di eventi che desideri includere nelle richieste di tracciamento dei collegamenti alle immagini (`tl()` metodo). Per includere le metriche negli hit di tracciamento dei collegamenti, è necessario soddisfare i tre criteri seguenti:

* Imposta l’evento desiderato nella [`events`](../page-vars/events/events-overview.md) variabile. Ad esempio, `s.events = "event1";`.
* Imposta la `events` variabile in `linkTrackVars`. Ad esempio, `s.linkTrackVars = "events";`.
* Imposta l’evento desiderato nella `linkTrackEvents` variabile. Ad esempio, `s.linkTrackEvents = "event1";`.

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

Il valore predefinito per questa variabile è una stringa vuota. Se questa variabile non è definita, tutti gli eventi sono inclusi nelle richieste di immagini di tracciamento dei collegamenti. La raccolta dati popola automaticamente questa variabile in base agli eventi impostati nell’interfaccia, in modo che sia sempre impostata per le implementazioni che utilizzano i tag in Adobe Experience Platform.

>[!TIP]
>
>Evita di usare l’identificatore oggetto di Analytics (`s.`) quando si specificano gli eventi in questa variabile. Ad esempio: `s.linkTrackEvents = "event1";` è corretto, mentre `s.linkTrackEvents = "s.event1";` non è corretto.

## Esempio

La seguente funzione di tracciamento dei collegamenti include solo `event1` (non `event2`) nella richiesta di immagine inviata all’Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
