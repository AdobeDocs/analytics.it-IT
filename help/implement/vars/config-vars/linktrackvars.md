---
title: linkTrackVars
description: Specifica le variabili da includere nelle richieste di immagini per il tracciamento dei collegamenti.
feature: Appmeasurement Implementation
exl-id: b884f6e9-45d9-49f0-ac74-ea6f4f01020a
role: Admin, Developer
TQID: https://experienceleague.adobe.com/B3So-VtGCz2klaFJT2a1zA3-AzSPaM9R-0jafXNsrVE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 344
ht-degree: 2%

---

# linkTrackVars

Alcune implementazioni non desiderano includere tutte le variabili in tutte le richieste di immagini di tracciamento dei collegamenti. Utilizzare le variabili `linkTrackVars` e [`linkTrackEvents`](linktrackevents.md) per includere selettivamente dimensioni e metriche nelle chiamate di [`tl()`](../functions/tl-method.md).

Questa variabile non viene utilizzata per le chiamate di visualizzazione pagina (metodo [`t()`](../functions/t-method.md)).

## Determinare le variabili da includere in un evento XDM utilizzando il Web SDK

Il Web SDK non esclude alcuni campi per le chiamate di tracciamento dei collegamenti. Tuttavia, è possibile utilizzare il callback `onBeforeEventSend` per cancellare o impostare i campi desiderati prima che i dati vengano inviati ad Adobe. Per ulteriori informazioni, vedere [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=it#modifying-events-globally) nella documentazione di Web SDK.

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
