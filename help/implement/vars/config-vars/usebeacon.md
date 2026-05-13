---
title: useBeacon
description: useBeacon consente di forzare AppMeasurement a utilizzare l’API sendBeacon dei browser
feature: Appmeasurement Implementation
exl-id: a3c4174a-711d-4a35-9f36-9b1049c7db54
role: Admin, Developer
TQID: https://experienceleague.adobe.com/-drQZhKcoWzWfwcbFKms2xV2eunuNYIjkm4AWTmD-Pg
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 388
ht-degree: 13%

---

# useBeacon

La maggior parte dei browser moderni include il metodo nativo `navigator.sendBeacon()`. Invia in modo asincrono una piccola quantità di dati tramite HTTP a un server web. AppMeasurement può utilizzare il metodo `navigator.sendBeacon()` se la variabile `useBeacon` è abilitata. È utile per i collegamenti di uscita e in altre situazioni in cui desideri inviare informazioni prima che la pagina venga scaricata.

Se `useBeacon` è abilitato, l&#39;hit successivo inviato ad Adobe utilizza il metodo `navigator.sendBeacon()` del browser invece di una richiesta di immagine `GET` standard. Questa variabile si applica sia alle richieste di immagini [`s.t()`](../functions/t-method.md) che a quelle [`s.tl()`](../functions/tl-method.md). Richiede AppMeasurement 2.17.0 o versione successiva.

>[!TIP]
>
>AppMeasurement abilita automaticamente `useBeacon` per le richieste di immagini di collegamento di uscita.

La variabile `useBeacon` viene ignorata quando il visitatore utilizza un browser che non supporta `navigator.sendBeacon()`. L’utilizzo di questa variabile richiede AppMeasurement 2.16.0 o versione successiva.

## Utilizzare l’API sendBeacon tramite l’estensione Web SDK

La casella di controllo **[!UICONTROL Document will unload]** all&#39;interno di una configurazione di azione determina se i dati inviati ad Adobe utilizzano l&#39;API sendBeacon.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai alla scheda [!UICONTROL Rules], quindi fai clic sulla regola desiderata.
1. In [!UICONTROL Actions], fare clic sull&#39;azione desiderata o sull&#39;icona **&#39;+&#39;** per aggiungere una nuova azione.
1. Imposta l&#39;elenco a discesa [!UICONTROL Extension] su **[!UICONTROL Adobe Experience Platform Web SDK]** e l&#39;elenco a discesa [!UICONTROL Action Type] su **[!UICONTROL Send event]**
1. Fare clic sulla casella di controllo **[!UICONTROL Document will unload]** a destra.

Se questa casella è selezionata, i dati vengono inviati ad Adobe utilizzando l’API sendBeacon. Per impostazione predefinita, questa impostazione è deselezionata.

## Utilizzare l’API sendBeacon per implementare manualmente il Web SDK

Imposta `documentUnloading` su `true` quando si invia un evento. Se non è impostato, il valore predefinito è `false`.

```json
alloy("sendEvent", {
  "documentUnloading": true,
  "xdm": {}
});
```

Per ulteriori informazioni, vedere [Utilizzo dell&#39;API sendBeacon](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#using-the-sendbeacon-api) nella documentazione di Web SDK.

## Utilizzare Beacon con l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.useBeacon in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.useBeacon` è un valore booleano che determina se AppMeasurement utilizza il metodo `navigator.sendBeacon()` del browser. Il valore predefinito è `false`. Impostare questa variabile su `true` prima di chiamare una funzione di tracciamento se si desidera utilizzare la natura asincrona di `navigator.sendBeacon()`.

```js
s.useBeacon = true;
```

>[!NOTE]
>
>Dopo l&#39;esecuzione di una chiamata di tracciamento, questa variabile viene reimpostata su `false`. Se l&#39;implementazione invia più richieste di immagini nello stesso caricamento di pagina (ad esempio applicazioni a pagina singola), imposta questa variabile su `true` prima di ogni chiamata di tracciamento.
