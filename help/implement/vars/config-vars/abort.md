---
title: abort
description: La variabile abort è un valore booleano che impedisce l'invio di un hit ai server di raccolta dati Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 5ef8ba686a13f8b4ab592c0b48a9c074b0477fcf
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 13%

---

# abort

Il `abort` la variabile è un valore booleano che può impedire l’invio all’Adobe della chiamata di tracciamento successiva. Funzionalità simili sono presenti nell’SDK per web, che consente di restituire `false` prima dell’invio di un evento XDM.

## Annullare l’invio di un evento tramite l’estensione Web SDK

Utilizza il [!UICONTROL On before event send callback] editor di codice e restituzione `false`.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fare clic sulla scheda **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Sotto [!UICONTROL Data Collection], fare clic su **[!UICONTROL Edit on before event send callback code]** pulsante.
1. Nell’editor di codice, inserisci il seguente codice in qualsiasi condizione che desideri interrompere l’invio di dati a Edge:

```js
return false;
```

## Annullare l’invio di un evento implementando manualmente l’SDK web

Utilizza il `onBeforeEventSend` callback e ritorno `false`. Consulta [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione dell’SDK per web.

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Utilizzo della variabile abort nell&#39;estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.abort in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

Il `s.abort` è di tipo booleano. Il valore predefinito è `false`.

* Se impostato su `true`, la chiamata di tracciamento successiva ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) non invia alcun dato ad Adobe.
* Se impostato su `false` o non definita, questa variabile non esegue alcuna operazione.

```js
s.abort = true;
```

>[!NOTE]
>
>Il `abort` la variabile viene ripristinata in `false` dopo ogni chiamata di tracciamento. Se desideri interrompere le chiamate di tracciamento successive sulla stessa pagina, imposta `abort` a `true` di nuovo.

Il `abort` può essere impostata in [`doPlugins()`](../functions/doplugins.md) è l’ultima funzione che viene eseguita prima di una richiesta di immagine inviata all’Adobe. Questo esempio funziona in modo simile al `onBeforeEventSend` callback tramite Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Puoi centralizzare la logica utilizzata per identificare le attività che non desideri monitorare, ad esempio alcuni collegamenti personalizzati o esterni negli annunci di visualizzazione.
