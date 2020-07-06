---
title: abort
description: La variabile abort è un valore booleano che impedisce l'invio di un hit ai server di raccolta dati Adobe.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 1%

---


# abort

La `abort` variabile è un valore booleano che può impedire l’invio ad Adobe della successiva chiamata di tracciamento.

## Utilizzo della variabile abort in  Adobe Experience Platform Launch

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## Sintassi AppMeasurement ed editor di codice personalizzato in Launch

La `abort` variabile è booleana. Its default value is `false`.

* Se impostato su `true`, la successiva chiamata di tracciamento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)) non invia dati ad Adobe.
* Se impostata su `false` o non definita, questa variabile non esegue alcuna operazione.

```js
s.abort = true;
```

>[!NOTE]
>
>La `abort` variabile viene reimpostata su `false` dopo ogni chiamata di tracciamento. Se devi interrompere le chiamate di tracciamento successive sulla stessa pagina, imposta `abort` di `true` nuovo.

## Esempio

La `abort` variabile può essere impostata nella [`doPlugins()`](../functions/doplugins.md) funzione, che è l&#39;ultima funzione da eseguire prima che una richiesta di immagine venga inviata ad Adobe.

```js
s.doPlugins = function(s) {
     s.campaign = s.Util.getQueryParam("cid");
     if ((!s.campaign) && (!s.events)) {
          s.abort = true;
     }
};
```

Potete centralizzare la logica utilizzata per identificare l&#39;attività che non desiderate monitorare, ad esempio alcuni collegamenti personalizzati o collegamenti esterni negli annunci visualizzati.
