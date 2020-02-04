---
title: linkTrackEvents
description: Determinare gli eventi da includere nelle richieste di tracciamento dei collegamenti per le immagini.
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# linkTrackEvents

Alcune implementazioni non desiderano includere tutte le variabili in tutte le richieste di immagini per il tracciamento dei collegamenti. Usa le `linkTrackVars` variabili e le `linkTrackEvents` variabili per includere in modo selettivo dimensioni e metriche nelle `tl()` chiamate.

Questa variabile non viene utilizzata per le chiamate di visualizzazione pagina (`t()` funzione).

## Eventi nelle chiamate di tracciamento dei collegamenti tramite Adobe Experience Platform Launch

Launch rileva automaticamente gli eventi definiti nell’interfaccia e li include negli hit di tracciamento dei collegamenti.

> [!IMPORTANT] Se si impostano gli eventi in Launch utilizzando l&#39;editor di codice personalizzato, è necessario includere l&#39;evento anche nell&#39; `linkTrackEvents` uso del codice personalizzato.

## s.linkTrackEvents in AppMeasurement e Launch editor di codice personalizzato

La `s.linkTrackEvents` variabile è una stringa contenente un elenco delimitato da virgole di eventi che si desidera includere nelle richieste di tracciamento dei collegamenti alle immagini (`tl()` funzione). Per includere le metriche negli hit di tracciamento dei collegamenti, devono essere soddisfatti i tre criteri seguenti:

* Impostate l’evento desiderato nella `events` variabile. Ad esempio, `s.events = "event1";` (Indirizzo IP).
* Set the `events` variable in `linkTrackVars`. Ad esempio, `s.linkTrackVars = "events";` (Indirizzo IP).
* Impostate l’evento desiderato nella `linkTrackEvents` variabile. Ad esempio, `s.linkTrackEvents = "event1";` (Indirizzo IP).

```js
s.linkTrackEvents = "event1,event2,event3,purchase";
```

Il valore predefinito per questa variabile è una stringa vuota. Se questa variabile non è definita, tutti gli eventi vengono inclusi nelle richieste di immagini per il tracciamento dei collegamenti. Si noti che Launch compila automaticamente questa variabile in base agli eventi impostati nell&#39;interfaccia, pertanto è sempre impostata nelle implementazioni tramite Launch.

> [!TIP] Evitare di utilizzare l&#39;identificatore oggetto (`s.`) di Analytics quando si specificano gli eventi in questa variabile. Ad esempio, `s.linkTrackEvents = "event1";` è corretta, mentre `s.linkTrackEvents = "s.event1";` è errata.

## Esempio

La seguente funzione di tracciamento dei collegamenti include solo `event1` (non `event2`) nella richiesta di immagine inviata ad Adobe:

```js
s.events = "event1,event2";
s.linkTrackVars = "events";
s.linkTrackEvents = "event1";
s.tl(this,"o","Example Custom Link");
```
