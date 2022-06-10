---
title: registerPreTrackCallback
description: Crea funzioni di callback prima di inviare un hit ad Adobe.
feature: Variables
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '417'
ht-degree: 1%

---

# registerPreTrackCallback

La `registerPreTrackCallback` consente all’organizzazione di collegare una funzione JavaScript dopo che è stato compilato un URL di richiesta dell’immagine, ma prima che venga inviato. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un’infrastruttura interna.

>[!WARNING]
>
>Non chiamare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) all&#39;interno del [`registerPostTrackCallback`](registerposttrackcallback.md) variabile. Le funzioni di tracciamento in questa variabile causano un ciclo infinito di richieste di immagini!

Ogni volta che si chiama il `registerPreTrackCallback` aggancia la funzione per l&#39;esecuzione ogni volta che viene compilato un URL di richiesta immagine. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>Tempi e ordine delle funzioni attivate tra `registerPreTrackCallback` e `registerPostTrackCallback` non sono garantite. Evita le dipendenze tra queste due funzioni.

## Callback di pre-tracciamento tramite l&#39;estensione SDK per web

L&#39;SDK web non è in grado di collegare una funzione dopo la compilazione dei dati, ma prima che venga inviata ad Adobe. Tuttavia, puoi utilizzare `onBeforeEventSend` per registrare una funzione da eseguire immediatamente prima dell’invio dei dati.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Alla voce [!UICONTROL Data Collection], fai clic sul pulsante **[!UICONTROL Edit on before event send callback code]**.
1. Inserisci il codice desiderato nell&#39;editor.

## Pre-tracciamento del callback che implementa manualmente l&#39;SDK per web

L&#39;SDK web non è in grado di collegare una funzione dopo la compilazione dei dati, ma prima che venga inviata ad Adobe. Tuttavia, puoi utilizzare `onBeforeEventSend` per registrare una funzione da eseguire immediatamente prima dell’invio dei dati, simile a `doPlugins`. Vedi [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione SDK per web .

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Callback di pre-tracciamento tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.registerPreTrackCallback in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.registerPreTrackCallback` è una funzione che utilizza una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente prima dell’invio di una richiesta di immagine.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Se desideri utilizzare l’URL della richiesta di immagine nel tuo codice, fai riferimento alla `requestUrl` argomento string all&#39;interno della funzione nidificata. È possibile analizzare i `requestUrl` variabile per l’uso desiderato; la regolazione di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

È possibile includere argomenti aggiuntivi nella `s.registerPreTrackCallback` , che può essere utilizzato nella funzione nidificata:

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
>Impostazione delle variabili di pagina o modifica della variabile `requestUrl` stringa all&#39;interno di questa funzione do **not** influisce sulla richiesta di immagine inviata poco dopo questa chiamata alla funzione. Utilizza la [`doPlugins()`](doplugins.md) invece.
