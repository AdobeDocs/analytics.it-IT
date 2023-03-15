---
title: linkTrackVars
description: Specifica le variabili da includere nelle richieste di immagini per il tracciamento dei collegamenti.
feature: Variables
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# linkTrackVars

Alcune implementazioni non desiderano includere tutte le variabili in tutte le richieste di immagini di tracciamento dei collegamenti. Utilizza il `linkTrackVars` e [`linkTrackEvents`](linktrackevents.md) variabili per includere selettivamente dimensioni e metriche in [`tl()`](../functions/tl-method.md) chiamate.

Questa variabile non viene utilizzata per le chiamate di visualizzazione pagina ([`t()`](../functions/t-method.md) metodo).

## Determinare quali variabili includere in un evento XDM utilizzando l’SDK per web

L’SDK per web non esclude alcuni campi per le chiamate di tracciamento dei collegamenti. Tuttavia, è possibile utilizzare `onBeforeEventSend` callback per cancellare o impostare i campi desiderati prima che i dati vengano inviati ad Adobe. Consulta [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

## Variabili nelle chiamate di tracciamento dei collegamenti tramite l’estensione Adobe Analytics

Questa variabile viene compilata automaticamente sul backend in base alle variabili impostate nell’interfaccia, quindi viene sempre impostata nelle implementazioni tramite l’estensione Adobe Analytics.

>[!IMPORTANT]
>
>Se imposti le variabili utilizzando l’editor di codice personalizzato, devi includere le variabili in `linkTrackVars` utilizzando anche codice personalizzato.

## s.linkTrackVars in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.linkTrackVars` variabile è una stringa contenente un elenco delimitato da virgole di variabili che desideri includere nelle richieste di immagini per il tracciamento dei collegamenti (`tl()` metodo). Per includere le dimensioni negli hit di tracciamento dei collegamenti è necessario soddisfare entrambi i seguenti criteri:

* Imposta il valore della variabile desiderato. Esempio: `s.eVar1 = "Example value";`.
* Imposta la variabile desiderata in `linkTrackVars` variabile. Esempio: `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Il valore predefinito per questa variabile è una stringa vuota. Tuttavia, in Code Manager l’Adobe ha fornito il codice AppMeasurement, dove questa variabile è impostata su `"None"`. I valori validi sono variabili a livello di pagina che popolano una dimensione.

* Se questa variabile non è definita o impostata su una stringa vuota, *tutto* Le variabili sono incluse nelle richieste di immagini per il tracciamento dei collegamenti.
* Se questa variabile è impostata su `"None"`, *no* Le variabili sono incluse nelle richieste di immagini per il tracciamento dei collegamenti.

>[!TIP]
>
>Evita di utilizzare l’identificatore di oggetto di Analytics (`s.`) quando si specificano le variabili in questa variabile. Ad esempio: `s.linkTrackVars = "eVar1";` è corretto, mentre `s.linkTrackVars = "s.eVar1";` non è corretto.

## Esempio

La funzione di tracciamento dei collegamenti seguente include solo `eVar1` (non `eVar2`) nella richiesta di immagine inviata all&#39;Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
