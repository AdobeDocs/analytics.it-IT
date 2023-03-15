---
title: registerPreTrackCallback
description: Crea funzioni di callback prima di inviare un hit all’Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 13%

---

# registerPreTrackCallback

Il `registerPreTrackCallback` consente all’organizzazione di agganciare una funzione JavaScript dopo che l’URL di una richiesta di immagine è stato compilato ma prima che venga inviato. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un’infrastruttura interna.

>[!WARNING]
>
>Non chiamare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all&#39;interno del [`registerPostTrackCallback`](registerposttrackcallback.md) variabile. Le funzioni di tracciamento in questa variabile causano un ciclo infinito di richieste di immagini.

Ogni volta che chiami il `registerPreTrackCallback` è possibile eseguire tale funzione ogni volta che viene compilato un URL di richiesta di immagine. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>Tempistica e ordine delle funzioni attivate tra `registerPreTrackCallback` e `registerPostTrackCallback` non sono garantite. Evita le dipendenze tra queste due funzioni.

## Pre-tracciare il callback utilizzando l’estensione Web SDK

L’SDK per web non è in grado di agganciare una funzione dopo la compilazione dei dati, ma prima che questi vengano inviati a Adobe. Tuttavia, puoi utilizzare `onBeforeEventSend` per registrare una funzione da eseguire immediatamente prima dell’invio dei dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. Alla voce [!UICONTROL Data Collection], fai clic sul pulsante **[!UICONTROL Edit on before event send callback code]**.
1. Inserisci il codice desiderato nell’editor.

## Pre-tracciare il callback manualmente implementando Web SDK

L’SDK per web non è in grado di agganciare una funzione dopo la compilazione dei dati, ma prima che questi vengano inviati a Adobe. Tuttavia, puoi utilizzare `onBeforeEventSend` per registrare una funzione da eseguire immediatamente prima dell’invio dei dati, in modo simile a `doPlugins`. Consulta [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Pre-tracciare il callback utilizzando l&#39;estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.registerPreTrackCallback in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.registerPreTrackCallback` è una funzione che utilizza una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente prima dell’invio di una richiesta di immagine.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Se desideri utilizzare l’URL della richiesta di immagine nel codice, fai riferimento a `requestUrl` argomento stringa nella funzione nidificata. Puoi analizzare `requestUrl` per l’uso desiderato; la regolazione di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

È possibile includere argomenti aggiuntivi nel `s.registerPreTrackCallback` funzione, che può essere utilizzata nella funzione nidificata:

```js
s.registerPreTrackCallback(function(requestUrl,a,b,c) {
    console.log(requestUrl); // Full image request URL
    console.log(a); // param1
    console.log(b); // param2
    console.log(c); // param3
}, "param1", "param2", "param3");
```

>[!NOTE]
>
>Impostazione delle variabili di pagina o modifica di `requestUrl` stringa all&#39;interno di questa funzione do **non** influisce sulla richiesta di immagine inviata poco dopo questa chiamata di funzione. Utilizza il [`doPlugins()`](doplugins.md) variabile.
