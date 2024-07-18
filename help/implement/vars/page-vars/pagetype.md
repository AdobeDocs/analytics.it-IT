---
title: pageType
description: Determina se la pagina corrente è un errore 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 5ef92db2f5edb5fded497dddedd56abd49d8a019
workflow-type: tm+mt
source-wordcount: '201'
ht-degree: 12%

---

# pageType

La variabile `pageType` è un flag utilizzato per designare le pagine di errore sul sito, ad esempio errori 404. Se la variabile contiene la stringa `errorPage`, verranno compilati i campi &#39;Pagine non trovate&#39; [dimensione](/help/components/dimensions/pages-not-found.md) e [metrica](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>Non impostare questa variabile su pagine che non contengono errori.

## Tipo di pagina utilizzando il Web SDK

Il canale è mappato alle seguenti variabili:

* [Oggetto XDM](/help/implement/aep-edge/xdm-var-mapping.md): `xdm.web.webPageDetails.isErrorPage` - questo campo XDM è di tipo booleano; impostarlo su `true` per contrassegnarlo come pagina di errore oppure su `false` se non si tratta di una pagina di errore.
* [Oggetto dati](/help/implement/aep-edge/data-var-mapping.md): `data.__adobe.analytics.pageType` - questo campo oggetto dati è una stringa; impostarlo su `"errorPage"` per contrassegnarlo come tale.

## Tipo di pagina utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.pageType in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.pageType` è una stringa in cui il valore `errorPage` è l&#39;unico valore valido. Imposta questa variabile su questo valore in qualsiasi pagina di errore del sito, ad esempio su 404 pagine.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilizza un eVar per raccogliere il codice di errore in modo da poter ottenere ulteriori informazioni sugli errori specifici riscontrati dai visitatori sul tuo sito.
