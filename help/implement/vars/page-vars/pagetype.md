---
title: pageType
description: Determina se la pagina corrente è un errore 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 1%

---

# pageType

La `pageType` è un flag utilizzato per designare le pagine di errore sul sito, ad esempio 404 errori. Se questa variabile contiene la stringa `errorPage`, compila la dimensione &quot;Pagine non trovate&quot;.

>[!IMPORTANT]
>
>Non impostare questa variabile su pagine non basate su errori.

## Tipo di pagina utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement.

## s.pageType in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.pageType` variabile è una stringa in cui il valore `errorPage` è l&#39;unico valore valido. Imposta questa variabile su questo valore in qualsiasi pagina di errore sul tuo sito, ad esempio su 404 pagine.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilizza un eVar per raccogliere il codice di errore e ottenere ulteriori informazioni sugli errori specifici riscontrati dai visitatori sul sito.
