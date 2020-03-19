---
title: linkTrackVars
description: Specifica quali variabili includere nelle richieste di immagini per il tracciamento dei collegamenti.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# linkTrackVars

Alcune implementazioni non desiderano includere tutte le variabili in tutte le richieste di immagini per il tracciamento dei collegamenti. Usa le `linkTrackVars` variabili e le [`linkTrackEvents`](linktrackevents.md) variabili per includere in modo selettivo dimensioni e metriche nelle [`tl()`](../functions/tl-method.md) chiamate.

Questa variabile non viene utilizzata per le chiamate di visualizzazione pagina (`t()` metodo).

## Variabili nelle chiamate di tracciamento dei collegamenti mediante Adobe Experience Platform Launch

Launch compila automaticamente questa variabile sul backend in base alle variabili impostate nell&#39;interfaccia, in modo che sia sempre impostata nelle implementazioni tramite Launch.

> [!IMPORTANT] Se impostate le variabili in Launch utilizzando l&#39;editor di codice personalizzato, è necessario includere la variabile anche nell&#39; `linkTrackVars` uso di codice personalizzato.

## s.linkTrackVars in AppMeasurement e Launch editor di codice personalizzato

La `s.linkTrackVars` variabile è una stringa contenente un elenco delimitato da virgole di variabili che si desidera includere nelle richieste di tracciamento dei collegamenti delle immagini (`tl()` metodo). Per includere le dimensioni negli hit di tracciamento dei collegamenti, è necessario soddisfare entrambi i criteri seguenti:

* Impostate il valore della variabile desiderata. Ad esempio, `s.eVar1 = "Example value";` (Indirizzo IP).
* Impostate la variabile desiderata nella `linkTrackVars` variabile. Ad esempio, `s.linkTrackEvents = "eVar1";` (Indirizzo IP).

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Il valore predefinito per questa variabile è una stringa vuota. Tuttavia, Adobe ha fornito il codice AppMeasurement in Code Manager, dove questa variabile è impostata su `"None"`. I valori validi sono qualsiasi variabile a livello di pagina che popola una dimensione.

* Se questa variabile non è definita o impostata su una stringa vuota, *tutte* le variabili vengono incluse nelle richieste di immagini per il tracciamento dei collegamenti.
* Se questa variabile è impostata su `"None"`, *nessuna* variabile viene inclusa nelle richieste di immagini per il tracciamento dei collegamenti.

> [!TIP] Evitare di utilizzare l&#39;identificatore oggetto (`s.`) di Analytics quando si specificano le variabili in questa variabile. Ad esempio, `s.linkTrackVars = "eVar1";` è corretta, mentre `s.linkTrackVars = "s.eVar1";` è errata.

## Esempio

La seguente funzione di tracciamento dei collegamenti include solo `eVar1` (non `eVar2`) nella richiesta di immagine inviata ad Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
