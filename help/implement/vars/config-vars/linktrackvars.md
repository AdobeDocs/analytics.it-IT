---
title: linkTrackVars
description: Specifica le variabili da includere nelle richieste di immagini di tracciamento dei collegamenti.
feature: Variables
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 2%

---

# linkTrackVars

Alcune implementazioni non vogliono includere tutte le variabili in tutte le richieste di immagini di tracciamento dei collegamenti. Utilizza la `linkTrackVars` e [`linkTrackEvents`](linktrackevents.md) variabili per includere in modo selettivo dimensioni e metriche in [`tl()`](../functions/tl-method.md) chiamate.

Questa variabile non viene utilizzata per le chiamate di visualizzazione della pagina ([`t()`](../functions/t-method.md) metodo).

## Variabili nelle chiamate di tracciamento dei collegamenti che utilizzano i tag in Adobe Experience Platform

Adobe Experience Platform compila automaticamente questa variabile sul backend in base alle variabili impostate nell’interfaccia, quindi viene sempre impostata nelle implementazioni utilizzando i tag in Adobe Experience Platform.

>[!IMPORTANT]
>
>Se imposti le variabili utilizzando l’editor di codice personalizzato, devi includere la variabile in `linkTrackVars` utilizzando anche codice personalizzato.

## s.linkTrackVars in AppMeasurement e nell&#39;editor di codice personalizzato

La `s.linkTrackVars` è una stringa contenente un elenco delimitato da virgole di variabili che desideri includere nelle richieste di tracciamento dei collegamenti alle immagini (`tl()` metodo). Per includere le dimensioni negli hit di tracciamento dei collegamenti, è necessario soddisfare entrambi i seguenti criteri:

* Imposta il valore della variabile desiderata. Ad esempio, `s.eVar1 = "Example value";`.
* Imposta la variabile desiderata nel `linkTrackVars` variabile. Ad esempio, `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Il valore predefinito per questa variabile è una stringa vuota. Tuttavia, Adobe ha fornito il codice AppMeasurement nel Code Manager dove questa variabile è impostata su `"None"`. I valori validi sono qualsiasi variabile a livello di pagina che popola una dimensione.

* Se questa variabile non è definita o impostata su una stringa vuota, *tutto* Le variabili sono incluse nelle richieste di immagini di tracciamento dei collegamenti.
* Se questa variabile è impostata su `"None"`, *no* Le variabili sono incluse nelle richieste di immagini di tracciamento dei collegamenti.

>[!TIP]
>
>Evita di usare l’identificatore oggetto di Analytics (`s.`) quando si specificano le variabili in questa variabile. Ad esempio: `s.linkTrackVars = "eVar1";` è corretto, mentre `s.linkTrackVars = "s.eVar1";` non è corretto.

## Esempio

La seguente funzione di tracciamento dei collegamenti include solo `eVar1` (non `eVar2`) nella richiesta di immagine inviata all’Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
