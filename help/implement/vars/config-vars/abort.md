---
title: abort
description: La variabile abort è booleana e impedisce l’invio di un hit ai server di raccolta dati di Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 1%

---

# interrompere

La `abort` è una variabile booleana che può impedire l’invio ad Adobe della successiva chiamata di tracciamento. Funzionalità simili esistono nell&#39;SDK per web che ti consentono di restituire `false` prima dell’invio di un evento XDM.

## Annullare l’invio di un evento utilizzando l’estensione SDK per web

Utilizza la [!UICONTROL On before event send callback] editor di codice e restituzione `false`.

1. Accedi a [Raccolta dati Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzo delle credenziali AdobeID.
1. Fai clic sulla proprietà tag desiderata.
1. Vai a [!UICONTROL Extensions] , quindi fai clic sul pulsante **[!UICONTROL Configure]** pulsante sotto [!UICONTROL Adobe Experience Platform Web SDK].
1. Alla voce [!UICONTROL Data Collection], fai clic sul pulsante **[!UICONTROL Edit on before event send callback code]**.
1. Nell’editor di codice, inserisci il seguente codice in qualsiasi condizione che desideri interrompere l’invio di dati a Edge:

```js
return false;
```

## Annullare l’invio manuale di un evento che implementa l’SDK per web

Utilizza la `onBeforeEventSend` callback e return `false`. Vedi [Modifica degli eventi a livello globale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/tracking-events.html#modifying-events-globally) per ulteriori informazioni, consulta la documentazione SDK per web .

```js
alloy("configure"), {
    "onBeforeEventSend": function(content) {
        return false;
    }
}
```

## Utilizzo della variabile abort nell’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.abort in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.abort` è una variabile booleana. Il valore predefinito è `false`.

* Se impostato su `true`, la successiva chiamata di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) non invia dati ad Adobe.
* Se impostato su `false` o non definita, questa variabile non esegue alcuna operazione.

```js
s.abort = true;
```

>[!NOTE]
>
>La `abort` reimposta su variabile `false` dopo ogni chiamata di tracciamento. Se devi interrompere le chiamate di tracciamento successive sulla stessa pagina, imposta `abort` a `true` di nuovo.

Ad esempio, il `abort` può essere impostata nella variabile [`doPlugins()`](../functions/doplugins.md) , l’ultima funzione da eseguire prima dell’invio ad Adobe di una richiesta di immagine. Questo esempio funziona in modo simile al `onBeforeEventSend` callback utilizzando l&#39;SDK per web.

```js
s.doPlugins = function(s) {
    s.campaign = s.Util.getQueryParam("cid");
    if ((!s.campaign) && (!s.events)) {
        s.abort = true;
    }
};
```

Puoi centralizzare la logica utilizzata per identificare l’attività che non desideri monitorare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci di visualizzazione.
