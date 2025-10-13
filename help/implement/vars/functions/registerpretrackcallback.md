---
title: registerPreTrackCallback
description: Crea funzioni di callback prima di inviare un hit ad Adobe.
feature: Appmeasurement Implementation
exl-id: 11c960d7-ded4-441a-822f-463d3a137d2d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 7%

---

# registerPreTrackCallback

La variabile `registerPreTrackCallback` consente all&#39;organizzazione di eseguire l&#39;hook di una funzione JavaScript dopo la compilazione di un URL di richiesta di immagine, ma prima dell&#39;invio. Puoi utilizzare questa variabile per inviare i dati raccolti da AppMeasurement a un partner o a un’infrastruttura interna.

>[!WARNING]
>
>Non effettuare chiamate di tracciamento come [`t()`](t-method.md) o [`tl()`](tl-method.md) nella variabile `registerPreTrackCallback`. L’impostazione delle chiamate di tracciamento in questa variabile causa un ciclo infinito di richieste di immagini.

Ogni volta che si chiama la variabile `registerPreTrackCallback`, la funzione viene eseguita ogni volta che viene compilato un URL di richiesta di immagine. Evita di registrare la stessa funzione più volte nello stesso caricamento della pagina.

>[!NOTE]
>
>La tempistica e l&#39;ordine delle funzioni attivate tra `registerPreTrackCallback` e `registerPostTrackCallback` non sono garantiti. Evita le dipendenze tra queste due funzioni.

## Pre-tracciare il callback utilizzando l&#39;estensione Web SDK

Il Web SDK non può eseguire l&#39;hook di una funzione dopo la compilazione dei dati, ma prima che questi vengano inviati ad Adobe. Tuttavia, è possibile utilizzare `onBeforeEventSend` per registrare una funzione da eseguire immediatamente prima dell&#39;invio dei dati.

1. Accedi all&#39;interfaccia utente di [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. In [!UICONTROL Data Collection] fare clic sul pulsante **[!UICONTROL Edit on before event send callback code]**.
1. Inserisci il codice desiderato nell’editor.

## Pre-tracciare il callback manualmente implementando Web SDK

Il Web SDK non può eseguire l&#39;hook di una funzione dopo la compilazione dei dati, ma prima che questi vengano inviati ad Adobe. Tuttavia, è possibile utilizzare `onBeforeEventSend` per registrare una funzione da eseguire immediatamente prima dell&#39;invio dei dati, in modo analogo a `doPlugins`. Per ulteriori informazioni, vedere [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=it#modifying-events-globally) nella documentazione di Web SDK.

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

`s.registerPreTrackCallback` è una funzione che accetta una funzione come unico argomento. La funzione nidificata viene eseguita immediatamente prima dell’invio di una richiesta di immagine.

```js
s.registerPreTrackCallback(function(){/* Desired code */});
```

Se desideri utilizzare l&#39;URL della richiesta di immagine nel codice, fai riferimento all&#39;argomento stringa `requestUrl` nella funzione nidificata. È possibile analizzare la variabile `requestUrl` per l&#39;uso desiderato; la regolazione di questa variabile non influisce sulla raccolta dei dati.

```js
s.registerPreTrackCallback(function(requestUrl){
  console.log(requestUrl); // Outputs the full image request URL
});
```

Nella funzione `s.registerPreTrackCallback` è possibile includere argomenti aggiuntivi che possono essere utilizzati nella funzione nidificata:

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
>L&#39;impostazione delle variabili di pagina o la modifica della stringa `requestUrl` all&#39;interno di questa funzione **non** influisce sulla richiesta di immagine inviata poco dopo la chiamata di questa funzione. Utilizza invece la variabile [`doPlugins()`](doplugins.md).
