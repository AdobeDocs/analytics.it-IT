---
title: doPlugins
description: Configura la logica immediatamente prima che un hit venga compilato e inviato ad Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
source-git-commit: 41154580c272514e504c5478215bb67795488de3
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 19%

---

# doPlugins

La `doPlugins` funge da &quot;ultima chiamata&quot; per impostare i valori nell’implementazione. È il luogo ideale per effettuare chiamate a [Metodi del plug-in](../plugins/impl-plugins.md) e imposta le variabili desiderate prima di inviare una richiesta di immagine. Se [`usePlugins`](../config-vars/useplugins.md) viene attivato, viene eseguito automaticamente immediatamente prima che qualsiasi tipo di richiesta di immagine venga compilata e inviata ad Adobe, tra cui:

* Visualizzazione di tutte le pagine ([`t()`](t-method.md)) chiamate
* Tracciamento di tutti i collegamenti ([`tl()`](tl-method.md)) chiamate , compresi i collegamenti di download e di uscita automatici

Utilizza la `doPlugins` per chiamare il codice plug-in e impostare i valori della variabile finale poco prima che una richiesta di immagine venga compilata e inviata ad Adobe.

## Usa su prima dell&#39;invio di un codice di callback utilizzando l&#39;estensione Web SDK

Invece di `doPlugins`, l&#39;SDK per web utilizza `onBeforeEventSend` con funzionalità simili.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. Alla voce [!UICONTROL Data Collection], fai clic sul pulsante **[!UICONTROL Edit on before event send callback code]**.
1. Inserisci il codice desiderato nell&#39;editor.

## Utilizzo `onBeforeEventSend` implementazione manuale dell’SDK per web

Invece di `doPlugins`, l&#39;SDK per web utilizza `onBeforeEventSend` con funzionalità simili. Vedi [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione SDK per web .

```js
// Set the trackingCode XDM field to "New value"
alloy("configure", {
  "onBeforeEventSend": function(content) {
    content.xdm.marketing.trackingCode = "New value";
  }
})
```

## Plug-in tramite l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.doPlugins in AppMeasurement e codice personalizzato

Imposta la `s.doPlugins` a una funzione contenente il codice desiderato. La funzione viene eseguita automaticamente quando effettui una chiamata di tracciamento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>Imposta una funzione su `doPlugins` una sola volta nell&#39;implementazione. Se imposti la `doPlugins` più di una volta, viene utilizzato solo il codice più recente.

## Esempi

```js
// Set eVar1 to the web page's title
s.doPlugins = function() {
  s.eVar1 = window.document.title;
};

// Use the getPreviousValue plug-in (requires plug-in code outside the function)
s.doPlugins = function() {
  s.eVar1 = s.getPreviousValue(s.pageName,'gpv_pn');
}
```

>[!NOTE]
>
>Le versioni precedenti di AppMeasurement erano leggermente diverse `doPlugins()` codice. Adobe consiglia di utilizzare il formato di cui sopra come best practice.
