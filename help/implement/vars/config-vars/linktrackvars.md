---
title: linkTrackVars
description: Specifica le variabili da includere nelle richieste di immagini per il tracciamento dei collegamenti.
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 2%

---

# linkTrackVars

Alcune implementazioni non desiderano includere tutte le variabili in tutte le richieste di immagini di tracciamento dei collegamenti. Utilizzare le variabili `linkTrackVars` e [`linkTrackEvents`](linktrackevents.md) per includere selettivamente dimensioni e metriche nelle chiamate di [`tl()`](../functions/tl-method.md).

Questa variabile non viene utilizzata per le chiamate di visualizzazione pagina (metodo [`t()`](../functions/t-method.md)).

## Determinare le variabili da includere in un evento XDM utilizzando il Web SDK

Il Web SDK non esclude alcuni campi per le chiamate di tracciamento dei collegamenti. Tuttavia, è possibile utilizzare il callback `onBeforeEventSend` per cancellare o impostare i campi desiderati prima che i dati vengano inviati ad Adobe. Per ulteriori informazioni, vedere [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) nella documentazione di Web SDK.

## Variabili nelle chiamate di tracciamento dei collegamenti tramite l’estensione Adobe Analytics

Questa variabile viene compilata automaticamente sul backend in base alle variabili impostate nell’interfaccia, quindi viene sempre impostata nelle implementazioni tramite l’estensione Adobe Analytics.

>[!IMPORTANT]
>
>Se si impostano le variabili utilizzando l&#39;editor di codice personalizzato, è necessario includere le variabili in `linkTrackVars` utilizzando anche il codice personalizzato.

## s.linkTrackVars in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.linkTrackVars` è una stringa contenente un elenco delimitato da virgole di variabili da includere nelle richieste di immagini di tracciamento dei collegamenti (metodo `tl()`). Per includere le dimensioni negli hit di tracciamento dei collegamenti è necessario soddisfare entrambi i seguenti criteri:

* Imposta il valore della variabile desiderato. Ad esempio: `s.eVar1 = "Example value";`.
* Impostare la variabile desiderata nella variabile `linkTrackVars`. Ad esempio: `s.linkTrackVars = "eVar1";`.

```js
s.linkTrackVars = "eVar1,eVar2,events,channel,products";
```

Il valore predefinito per questa variabile è una stringa vuota. Tuttavia, Adobe ha fornito il codice AppMeasurement in Code Manager dove questa variabile è impostata su `"None"`. I valori validi sono variabili a livello di pagina che popolano una dimensione.

* Se questa variabile non è definita o impostata su una stringa vuota, *tutte* le variabili sono incluse nelle richieste di immagini per il tracciamento dei collegamenti.
* Se questa variabile è impostata su `"None"`, *no* variabili sono incluse nelle richieste di immagini per il tracciamento dei collegamenti.

>[!TIP]
>
>Evitare di utilizzare l&#39;identificatore di oggetto di Analytics (`s.`) quando si specificano variabili in questa variabile. `s.linkTrackVars = "eVar1";`, ad esempio, è corretto, mentre `s.linkTrackVars = "s.eVar1";` non è corretto.

## Esempio

La funzione di tracciamento dei collegamenti seguente include solo `eVar1` (non `eVar2`) nella richiesta di immagine inviata ad Adobe:

```js
s.eVar1 = "Example value 1";
s.eVar2 = "Example value 2";
s.linkTrackVars = "eVar1";
s.tl(this,"o","Example Custom Link");
```
