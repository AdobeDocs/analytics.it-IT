---
title: sa
description: Modifica la suite di rapporti in qualsiasi momento nell’implementazione.
feature: Variables
exl-id: 524857a7-c820-4985-86c7-fcf21a0809bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 12%

---

# sa

Il `sa()` consente di modificare dinamicamente una suite di rapporti in qualsiasi momento sulla pagina. Se desideri inviare dati a suite di rapporti diverse senza ricaricare la pagina, puoi utilizzare questo metodo.

## Gestione delle suite di rapporti tramite Web SDK

L’SDK per web funziona inviando dati a uno stream di dati specifico, che inoltra i dati alle suite di rapporti di Analytics desiderate. Un singolo stream di dati può inoltrare i dati a più suite di rapporti. Questa sezione si applica sia all’estensione Web SDK che all’implementazione manuale di Web SDK.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Clic **[!UICONTROL Datastreams]** a sinistra.
1. Fai clic sullo stream di dati desiderato oppure fai clic su **[!UICONTROL New Datastream]**.
1. Clic **[!UICONTROL Add Service]**, quindi seleziona **[!UICONTROL Adobe Analytics]**.
1. Immetti l’ID suite di rapporti desiderato. Se desideri inviare gli stessi dati a più suite di rapporti, fai clic su **[!UICONTROL Add Report Suite]**.
1. Una volta immesse tutte le suite di rapporti desiderate, fai clic su **[!UICONTROL Save]**.

## Impostare lo stream di dati desiderato utilizzando l’estensione Web SDK

L’estensione Web SDK fornisce un elenco a discesa Datastream per ogni ambiente. In alternativa, è possibile immettere manualmente l’ID dello stream di dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Datastreams], scegli lo stream di dati desiderato nel menu a discesa per ogni ambiente.
1. Fai clic su **[!UICONTROL Save]** (Usa modello di attribuzione non predefinito).

## Impostare lo stream di dati desiderato implementando manualmente il Web SDK

Imposta il `edgeConfigId` variabile di configurazione per l’ID dello stream di dati. L’ID dello stream di dati si trova a destra quando si visualizza uno stream di dati in Raccolta dati di Adobe Experience Platform.

```js
alloy("configure", {
  "edgeConfigId": "example-a01f-4458-8cec-ef61de241c93",
});
```

Consulta [Configurare l’SDK per web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=it) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

## Modificare la suite di rapporti tramite l’estensione Adobe Analytics

Non esiste un modo flessibile per modificare la suite di rapporti nell’interfaccia. Puoi impostare la suite di rapporti sotto [!UICONTROL Library Management] Pannello a soffietto durante la configurazione dell’estensione Adobe Analytics. Tuttavia, non puoi modificare o aggiornare la suite di rapporti utilizzando le regole. Se desideri aggiornare i valori della suite di rapporti dopo averli impostati, utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.sa() in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Chiama il `s.sa()` per modificare la suite di rapporti di destinazione. L’unico argomento è una stringa contenente un ID suite di rapporti o più ID suite di rapporti delimitati da una virgola. L’argomento ID suite di rapporti è obbligatorio. Non utilizzare spazi nell&#39;argomento stringa.

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
