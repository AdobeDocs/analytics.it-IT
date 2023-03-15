---
title: useBeacon
description: useBeacon consente di forzare AppMeasurement a utilizzare l'API sendBeacon del browser
feature: Variables
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 13%

---

# useBeacon

La maggior parte dei browser moderni include il metodo nativo `navigator.sendBeacon()`. Invia in modo asincrono una piccola quantità di dati tramite HTTP a un server web. AppMeasurement può utilizzare `navigator.sendBeacon()` metodo se `useBeacon` è abilitata. È utile per i collegamenti di uscita e in altre situazioni in cui desideri inviare informazioni prima che la pagina venga scaricata.

Se `useBeacon` è attivato, l’hit successivo inviato all’Adobe utilizza il `navigator.sendBeacon()` anziché uno standard `GET` richiesta immagine. Questa variabile si applica a entrambi [`s.t()`](../functions/t-method.md) e [`s.tl()`](../functions/tl-method.md) richieste di immagini. Richiede AppMeasurement 2.17.0 o versione successiva.

>[!TIP]
>
>AppMeasurement abilita automaticamente `useBeacon` per le richieste di immagini di collegamento di uscita.

Il `useBeacon` viene ignorata quando il visitatore utilizza un browser che non supporta `navigator.sendBeacon()`. L’utilizzo di questa variabile richiede AppMeasurement 2.16.0 o versione successiva.

## Utilizzare l’API sendBeacon tramite l’estensione Web SDK

Il **[!UICONTROL Document will unload]** all&#39;interno di una configurazione di azione determina se i dati inviati ad Adobe utilizzano l&#39;API sendBeacon.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Rules] , quindi fai clic sulla regola desiderata.
1. Sotto [!UICONTROL Actions], fai clic sull’Azione desiderata o fai clic su **&#39;+&#39;** per aggiungere una nuova azione.
1. Imposta il menu a discesa Estensione su **[!UICONTROL Adobe Experience Platform Web SDK]** e [!UICONTROL Action Type] a **[!UICONTROL Send event]**
1. Fai clic sulla casella di controllo **[!UICONTROL Document will unload]** a destra.

Se questa casella è selezionata, i dati vengono inviati ad Adobe utilizzando l’API sendBeacon. Per impostazione predefinita, questa impostazione è deselezionata.

## Utilizzare l’API sendBeacon implementando manualmente l’SDK per web

Imposta `documentUnloading` a `true` quando si invia un evento. Se non viene impostato, il valore predefinito è `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Consulta [Utilizzo dell’API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

## Utilizzare Beacon con l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.useBeacon in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.useBeacon` è un valore booleano che determina se AppMeasurement utilizza il codice `navigator.sendBeacon()` metodo. Il valore predefinito è `false`. Imposta questa variabile su `true` prima di richiamare una funzione di tracciamento, se desideri utilizzare la natura asincrona di `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Dopo l’esecuzione di una chiamata di tracciamento, questa variabile viene reimpostata su `false`. Se l’implementazione invia più richieste di immagini nello stesso caricamento di pagina (ad esempio applicazioni a pagina singola), imposta questa variabile su `true` prima di ogni chiamata di tracciamento.
