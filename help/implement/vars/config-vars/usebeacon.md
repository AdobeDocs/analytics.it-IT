---
title: useBeacon
description: useBeacon consente di forzare AppMeasurement a utilizzare l’API sendBeacon dei browser
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 6de20d2fbbab6ded6c92f0c6f3536671f4b2ae46
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 13%

---

# useBeacon

I browser più moderni includono il metodo nativo `navigator.sendBeacon()`. Invia in modo asincrono una piccola quantità di dati su HTTP a un server web. AppMeasurement può utilizzare il `navigator.sendBeacon()` se `useBeacon` è abilitata. È utile per i collegamenti di uscita e altre situazioni in cui desideri inviare informazioni prima che la pagina si scarichi.

Se `useBeacon` è abilitato, l&#39;hit successivo inviato ad Adobe utilizza l&#39; `navigator.sendBeacon()` metodo anziché standard `GET` richiesta immagine. Questa variabile si applica a entrambi [`s.t()`](../functions/t-method.md) e [`s.tl()`](../functions/tl-method.md) richieste di immagini. Richiede AppMeasurement 2.17.0 o versione successiva.

>[!TIP]
>
>AppMeasurement abilita automaticamente `useBeacon` per le richieste di immagini di link in uscita.

La `useBeacon` viene ignorata quando il visitatore utilizza un browser che non supporta `navigator.sendBeacon()`. L&#39;utilizzo di questa variabile richiede AppMeasurement 2.16.0 o versione successiva.

## Utilizzare l&#39;API sendBeacon utilizzando l&#39;estensione Web SDK

La **[!UICONTROL Document will unload]** in una configurazione azione, la casella di controllo determina se i dati inviati ad Adobe utilizzano l’API sendBeacon.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata.
1. Sotto [!UICONTROL Actions], fai clic sull’azione desiderata o sul pulsante **&#39;+&#39;** per aggiungere una nuova azione.
1. Imposta la [!UICONTROL Extension] elenco a discesa in **[!UICONTROL Adobe Experience Platform Web SDK]** e [!UICONTROL Action Type] a **[!UICONTROL Send event]**
1. Fai clic sulla casella di controllo **[!UICONTROL Document will unload]** a destra.

Se questa casella è selezionata, i dati vengono inviati ad Adobe utilizzando l’API sendBeacon. Per impostazione predefinita, questa impostazione è deselezionata.

## Utilizza l’API sendBeacon manualmente l’implementazione dell’SDK per web

Imposta `documentUnloading` a `true` quando si invia un evento. Se non è impostato, il valore predefinito è `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Vedi [Utilizzo dell’API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) per ulteriori informazioni, consulta la documentazione SDK per web .

## Utilizzare il beacon con con con l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.useBeacon in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.useBeacon` è una variabile booleana che determina se AppMeasurement utilizza l’ del browser `navigator.sendBeacon()` metodo . Il valore predefinito è `false`. Imposta questa variabile su `true` prima di richiamare una funzione di tracciamento se desideri utilizzare la natura asincrona di `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Dopo l’esecuzione di una chiamata di tracciamento, questa variabile viene reimpostata su `false`. Se l’implementazione invia più richieste di immagini nello stesso caricamento della pagina (ad esempio applicazioni a pagina singola), imposta questa variabile su `true` prima di ogni chiamata di tracciamento.
