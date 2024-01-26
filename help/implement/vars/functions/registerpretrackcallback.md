---
title: registerPreTrackCallback
description: Crea funzioni di callback prima di inviare un hit all’Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 7%

---

# registerPreTrackCallback

Il `registerPreTrackCallback` consente all’organizzazione di agganciare una funzione JavaScript dopo che l’URL di una richiesta di immagine è stato compilato ma prima che venga inviato. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un’infrastruttura interna.

>[!WARNING]
>
>Non effettuare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all&#39;interno del `registerPreTrackCallback` variabile. L’impostazione delle chiamate di tracciamento in questa variabile causa un ciclo infinito di richieste di immagini.

Ogni volta che chiami il `registerPreTrackCallback` è possibile eseguire tale funzione ogni volta che viene compilato un URL di richiesta di immagine. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>Tempistica e ordine delle funzioni attivate tra `registerPreTrackCallback` e `registerPostTrackCallback` non sono garantite. Evita le dipendenze tra queste due funzioni.

## Pre-tracciare il callback utilizzando l’estensione Web SDK

L’SDK per web non può eseguire l’hook di una funzione dopo la compilazione dei dati, ma prima che questi vengano inviati a Adobe. Tuttavia, puoi utilizzare `onBeforeEventSend` per registrare una funzione da eseguire immediatamente prima dell’invio dei dati.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) Interfaccia utente che utilizza le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Data Collection], fare clic su **[!UICONTROL Edit on before event send callback code]** pulsante.
1. Inserisci il codice desiderato nell’editor.

## Pre-tracciare il callback manualmente implementando Web SDK

L’SDK per web non può eseguire l’hook di una funzione dopo la compilazione dei dati, ma prima che questi vengano inviati a Adobe. Tuttavia, puoi utilizzare `onBeforeEventSend` per registrare una funzione da eseguire immediatamente prima dell’invio dei dati, in modo simile a `doPlugins`. Consulta [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

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

## s.registerPreTrackCallback in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

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
