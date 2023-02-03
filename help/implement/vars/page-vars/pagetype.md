---
title: pageType
description: Determina se la pagina corrente è un errore 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
source-git-commit: 8a6c639af7427a9975ccd061d059696d4611dff3
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 15%

---

# pageType

La `pageType` è un flag utilizzato per designare le pagine di errore sul sito, ad esempio 404 errori. Se questa variabile contiene la stringa `errorPage`, compila le pagine non trovate [dimension](/help/components/dimensions/pages-not-found.md) e [metrica](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>Non impostare questa variabile su pagine non basate su errori.

## Tipo di pagina mediante l’SDK per web

Tipo di pagina [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `web.webPageDetails.isErrorPage`. Questo campo XDM è booleano; impostarlo su `true` per contrassegnarlo come pagina di errore, oppure `false` se non si tratta di una pagina di errore. Adobe traduce automaticamente il valore booleano nel valore stringa `errorPage` quando viene inviato a una suite di rapporti di Analytics.

## Tipo di pagina utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.pageType in AppMeasurement e nell&#39;editor di codice personalizzato dell&#39;estensione Analytics

La `s.pageType` variabile è una stringa in cui il valore `errorPage` è l&#39;unico valore valido. Imposta questa variabile su questo valore in qualsiasi pagina di errore sul tuo sito, ad esempio su 404 pagine.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilizza un eVar per raccogliere il codice di errore e ottenere ulteriori informazioni sugli errori specifici riscontrati dai visitatori sul sito.
