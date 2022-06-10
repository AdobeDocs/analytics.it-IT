---
title: sa
description: Modifica la suite di rapporti in qualsiasi momento dell’implementazione.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# sa

La `sa()` consente di modificare dinamicamente una suite di rapporti in qualsiasi momento della pagina. Se desideri inviare dati a suite di rapporti diverse senza ricaricare la pagina, puoi utilizzare questo metodo.

## Gestione delle suite di rapporti tramite l’SDK per web

L’SDK per web funziona inviando dati a un Datastream specifico, che inoltra i dati alle suite di rapporti di Analytics desiderate. Un singolo Datastream può inoltrare i dati a più suite di rapporti. Questa sezione si applica sia all&#39;estensione SDK per web che all&#39;implementazione manuale dell&#39;SDK per web.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic su **[!UICONTROL Datastreams]** a sinistra.
1. Fare clic sul Datastream desiderato o fare clic su **[!UICONTROL New Datastream]**.
1. Fai clic su **[!UICONTROL Add Service]**, quindi seleziona **[!UICONTROL Adobe Analytics]**.
1. Immetti l’ID suite di rapporti desiderato. Se desideri inviare gli stessi dati a più suite di rapporti, fai clic su **[!UICONTROL Add Report Suite]**.
1. Una volta inserite tutte le suite di rapporti desiderate, fai clic su **[!UICONTROL Save]**.

## Imposta il Datastream desiderato utilizzando l&#39;estensione Web SDK

L&#39;estensione Web SDK fornisce un elenco a discesa Datastream per ogni ambiente. In alternativa, è possibile immettere manualmente l&#39;ID Datastream.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Datastreams], scegli il Datastream desiderato nel menu a discesa per ogni ambiente.
1. Fai clic su **[!UICONTROL Save]**.

## Imposta manualmente il Datastream desiderato implementando l&#39;SDK per web

Imposta la `edgeConfigId` variabile di configurazione dell&#39;ID Datastream. L’ID Datastream si trova a destra quando si visualizza un Datastream in Adobe Experience Platform Data Collection.

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

Vedi [Configurare l’SDK per web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) per ulteriori informazioni, consulta la documentazione SDK per web .

## Modificare la suite di rapporti utilizzando l’estensione Adobe Analytics

Non esiste un modo flessibile per modificare la suite di rapporti nell’interfaccia di . Puoi impostare la suite di rapporti in [!UICONTROL Library Management] pannello a soffietto durante la configurazione dell&#39;estensione Adobe Analytics. Tuttavia, non puoi modificare o aggiornare la suite di rapporti utilizzando le regole. Se desideri aggiornare i valori della suite di rapporti dopo averli impostati, utilizza l’editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.sa() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `s.sa()` per modificare la suite di rapporti di destinazione. L&#39;unico argomento è una stringa contenente un ID suite di rapporti o più ID suite di rapporti delimitati da una virgola. L’argomento ID suite di rapporti è obbligatorio. Non utilizzare spazi nell&#39;argomento stringa.

```js
s.sa("examplersid");
```

Ad esempio, puoi modificare la suite di rapporti se l’utente esegue un’azione specifica sul sito.

```js
// Instantiate the tracking object
var s = s_gi("examplersid");

// If the visitor plays a video, you can add a video report suite
s.sa("examplersid,videorsid");

// Then send an image request
s.t();
```
