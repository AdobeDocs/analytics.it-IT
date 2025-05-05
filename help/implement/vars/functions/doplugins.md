---
title: doPlugins
description: Configura la logica immediatamente prima che un hit venga compilato e inviato all’Adobe.
feature: Variables
exl-id: c5113be3-04b3-4dd2-8481-ba13149750ca
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 15%

---

# doPlugins

La variabile `doPlugins` funge da &quot;ultima chiamata&quot; per impostare i valori nell&#39;implementazione. È il luogo ideale per effettuare chiamate ai [metodi plug-in](../plugins/impl-plugins.md) e impostare le variabili desiderate prima di inviare una richiesta di immagine. Se [`usePlugins`](../config-vars/useplugins.md) è abilitato, viene eseguito automaticamente immediatamente prima che qualsiasi tipo di richiesta di immagine venga compilata e inviata all&#39;Adobe, inclusi:

* Tutte le chiamate di visualizzazione pagina ([`t()`](t-method.md))
* Tutte le chiamate di tracciamento dei collegamenti ([`tl()`](tl-method.md)), inclusi i collegamenti di download automatici e di uscita

Utilizza la variabile `doPlugins` per richiamare il codice del plug-in e impostare i valori finali della variabile subito prima che una richiesta di immagine venga compilata e inviata all&#39;Adobe.

## Utilizzare il codice di callback On Before Event Send utilizzando l&#39;estensione Web SDK

Anziché `doPlugins`, Web SDK utilizza `onBeforeEventSend` con funzionalità simili.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. In [!UICONTROL Data Collection] fare clic sul pulsante **[!UICONTROL Edit on before event send callback code]**.
1. Inserisci il codice desiderato nell’editor.

## Utilizza `onBeforeEventSend` implementando manualmente Web SDK

Anziché `doPlugins`, Web SDK utilizza `onBeforeEventSend` con funzionalità simili. Per ulteriori informazioni, consulta [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html?lang=it#modifying-events-globally) nella documentazione di Web SDK.

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

## s.doPlugins nell’AppMeasurement e nel codice personalizzato

Impostare la variabile `s.doPlugins` su una funzione contenente il codice desiderato. La funzione viene eseguita automaticamente quando si effettua una chiamata di tracciamento.

```js
s.doPlugins = function() {/* Desired code */};
```

>[!IMPORTANT]
>
>Impostare una funzione sulla variabile `doPlugins` una sola volta nell&#39;implementazione. Se si imposta la variabile `doPlugins` più di una volta, verrà utilizzato solo il codice più recente.

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
>Le versioni precedenti dell&#39;AppMeasurement avevano un codice `doPlugins()` leggermente diverso. L’Adobe consiglia di utilizzare il formato di cui sopra come best practice.
