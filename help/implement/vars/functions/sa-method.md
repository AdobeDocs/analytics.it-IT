---
title: sa
description: Modifica la suite di rapporti in qualsiasi momento nell’implementazione.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 8%

---

# sa

Il metodo `sa()` consente di modificare dinamicamente una suite di rapporti in qualsiasi momento sulla pagina. Se desideri inviare dati a suite di rapporti diverse senza ricaricare la pagina, puoi utilizzare questo metodo.

## Gestione delle suite di rapporti tramite Web SDK

L’SDK per web funziona inviando dati a uno stream di dati specifico, che inoltra i dati alle suite di rapporti di Analytics desiderate. Un singolo stream di dati può inoltrare i dati a più suite di rapporti. Questa sezione si applica sia all’estensione Web SDK che all’implementazione manuale di Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fare clic su **[!UICONTROL Datastreams]** a sinistra.
1. Fare clic sullo stream di dati desiderato oppure fare clic su **[!UICONTROL New Datastream]**.
1. Fai clic su **[!UICONTROL Add Service]**, quindi seleziona **[!UICONTROL Adobe Analytics]**.
1. Immetti l’ID suite di rapporti desiderato. Se si desidera inviare gli stessi dati a più suite di rapporti, fare clic su **[!UICONTROL Add Report Suite]**.
1. Una volta immesse tutte le suite di rapporti desiderate, fare clic su **[!UICONTROL Save]**.

## Impostare lo stream di dati desiderato utilizzando l’estensione Web SDK

L’estensione Web SDK fornisce un elenco a discesa Flusso di dati per ogni ambiente. In alternativa, è possibile immettere manualmente l’ID dello stream di dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. In [!UICONTROL Datastreams], scegli lo stream di dati desiderato nell&#39;elenco a discesa per ogni ambiente.
1. Fai clic su **[!UICONTROL Save]**.

## Impostare lo stream di dati desiderato implementando manualmente il Web SDK

Impostare la variabile di configurazione `edgeConfigId` sull&#39;ID dello stream di dati. L’ID dello stream di dati si trova a destra quando si visualizza uno stream di dati in Raccolta dati di Adobe Experience Platform.

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

Per ulteriori informazioni, consulta [Configurare Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) nella documentazione di Web SDK.

## Modificare la suite di rapporti tramite l’estensione Adobe Analytics

Non esiste un modo flessibile per modificare la suite di rapporti nell’interfaccia. È possibile impostare la suite di rapporti nel pannello a soffietto [!UICONTROL Library Management] durante la configurazione dell&#39;estensione Adobe Analytics. Tuttavia, non puoi modificare o aggiornare la suite di rapporti utilizzando le regole. Se desideri aggiornare i valori della suite di rapporti dopo averli impostati, utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.sa() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiamare il metodo `s.sa()` per modificare la suite di rapporti di destinazione. L’unico argomento è una stringa contenente un ID suite di rapporti o più ID suite di rapporti delimitati da una virgola. L’argomento ID suite di rapporti è obbligatorio. Non utilizzare spazi nell&#39;argomento stringa.

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
