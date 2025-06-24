---
title: abort
description: La variabile abort è booleana e impedisce l'invio di un hit ai server di raccolta dati di Adobe.
feature: Appmeasurement Implementation
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '308'
ht-degree: 13%

---

# abort

La variabile `abort` è un valore booleano che può impedire l&#39;invio ad Adobe della chiamata di tracciamento successiva. Funzionalità simili esistono nel Web SDK che consentono di restituire `false` prima dell&#39;invio di un evento XDM.

## Annullare l’invio di un evento tramite l’estensione Web SDK

Utilizza l&#39;editor di codice [!UICONTROL On before event send callback] e restituisce `false`.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
1. Fai clic sulla proprietà del tag desiderata.
1. Passa alla scheda [!UICONTROL Extensions], quindi fai clic sul pulsante **[!UICONTROL Configure]** in [!UICONTROL Adobe Experience Platform Web SDK].
1. In [!UICONTROL Data Collection] fare clic sul pulsante **[!UICONTROL Edit on before event send callback code]**.
1. Nell’editor di codice, inserisci il seguente codice in qualsiasi condizione che desideri interrompere l’invio di dati ad Edge:

```js
return false;
```

## Annullare l’invio di un evento implementando manualmente il Web SDK

Utilizza il callback `onBeforeEventSend` e restituisce `false`. Per ulteriori informazioni, vedere [Modifica globale degli eventi](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) nella documentazione di Web SDK.

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

La variabile `s.abort` è di tipo booleano. Il valore predefinito è `false`.

* Se è impostato su `true`, la chiamata di tracciamento successiva ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) non invia dati ad Adobe.
* Se è impostata su `false` o non è definita, questa variabile non esegue alcuna operazione.

```js
s.abort = true;
```

>[!NOTE]
>
>La variabile `abort` viene reimpostata su `false` dopo ogni chiamata di tracciamento. Se si desidera interrompere le chiamate di tracciamento successive sulla stessa pagina, impostare di nuovo `abort` su `true`.

La variabile `abort` può essere impostata nella funzione [`doPlugins()`](../functions/doplugins.md), che è l&#39;ultima funzione eseguita prima che venga inviata una richiesta di immagine ad Adobe. Questo esempio funziona in modo simile al callback `onBeforeEventSend` utilizzando Web SDK.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Puoi centralizzare la logica utilizzata per identificare le attività che non desideri monitorare, ad esempio alcuni collegamenti personalizzati o esterni negli annunci di visualizzazione.
