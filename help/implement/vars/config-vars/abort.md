---
title: abort
description: La variabile abort è booleana e impedisce l’invio di un hit ai server di raccolta dati di Adobe.
exl-id: e4e25a89-272b-4444-b52b-c7fe2478ff30
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '193'
ht-degree: 1%

---

# interrompere

La variabile `abort` è booleana e può impedire l’invio ad Adobe della successiva chiamata di tracciamento.

## Utilizzo della variabile abort nell’interfaccia utente di raccolta dati in Adobe Experience Platform

Nell’interfaccia utente di raccolta dati non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## Sintassi AppMeasurement ed editor di codice personalizzato nell&#39;interfaccia utente della raccolta dati

La variabile `abort` è booleana. Il valore predefinito è `false`.

* Se è impostato su `true`, la successiva chiamata di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) non invia dati ad Adobe.
* Se impostata su `false` o non definita, questa variabile non esegue alcuna operazione.

```js
s.abort = true;
```

>[!NOTE]
>
>La variabile `abort` viene reimpostata su `false` dopo ogni chiamata di tracciamento. Se devi interrompere le chiamate di tracciamento successive sulla stessa pagina, imposta nuovamente `abort` su `true`.

## Esempio

La variabile `abort` può essere impostata nella funzione [`doPlugins()`](../functions/doplugins.md) , che è l’ultima funzione da eseguire prima che una richiesta di immagine venga inviata ad Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Puoi centralizzare la logica utilizzata per identificare l’attività che non desideri monitorare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci di visualizzazione.
