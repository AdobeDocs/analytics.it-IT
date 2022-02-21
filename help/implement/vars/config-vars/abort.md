---
title: abort
description: La variabile abort è booleana e impedisce l’invio di un hit ai server di raccolta dati di Adobe.
feature: Variables
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# interrompere

La `abort` è una variabile booleana che può impedire l’invio ad Adobe della successiva chiamata di tracciamento.

## Utilizzo della variabile abort nell’interfaccia utente di raccolta dati in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## Sintassi AppMeasurement ed editor di codice personalizzato nell&#39;interfaccia utente della raccolta dati

La `abort` è una variabile booleana. Il valore predefinito è `false`.

* Se impostato su `true`, la successiva chiamata di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) non invia dati ad Adobe.
* Se impostato su `false` o non definita, questa variabile non esegue alcuna operazione.

```js
s.abort = true;
```

>[!NOTE]
>
>La `abort` reimposta su variabile `false` dopo ogni chiamata di tracciamento. Se devi interrompere le chiamate di tracciamento successive sulla stessa pagina, imposta `abort` a `true` di nuovo.

## Esempio

La `abort` può essere impostata nella variabile [`doPlugins()`](../functions/doplugins.md) , l’ultima funzione da eseguire prima dell’invio ad Adobe di una richiesta di immagine.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Puoi centralizzare la logica utilizzata per identificare l’attività che non desideri monitorare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci di visualizzazione.
