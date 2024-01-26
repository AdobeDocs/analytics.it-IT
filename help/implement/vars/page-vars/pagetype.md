---
title: pageType
description: Determina se la pagina corrente è un errore 404.
feature: Variables
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 12%

---

# pageType

Il `pageType` variabile è un flag utilizzato per designare le pagine di errore sul sito, ad esempio errori 404. Se questa variabile contiene la stringa `errorPage`, popola le pagine non trovate [dimensione](/help/components/dimensions/pages-not-found.md) e [metrica](/help/components/metrics/pages-not-found.md).

>[!IMPORTANT]
>
>Non impostare questa variabile su pagine che non contengono errori.

## Tipo di pagina utilizzando il Web SDK

Il tipo di pagina è [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) nel campo XDM `web.webPageDetails.isErrorPage`. Questo campo XDM è booleano; impostalo su `true` per contrassegnarla come pagina di errore, oppure `false` se non è una pagina di errore. L’Adobe traduce automaticamente il valore booleano nel valore stringa `errorPage` quando viene inviato a una suite di rapporti di Analytics.

## Tipo di pagina utilizzando l’estensione Adobe Analytics

Nell’estensione Adobe Analytics non è presente un campo dedicato per utilizzare questa variabile. Utilizza l’editor di codice personalizzato seguendo la sintassi di AppMeasurement.

## s.pageType in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.pageType` variabile è una stringa in cui il valore `errorPage` è il suo unico valore valido. Imposta questa variabile su questo valore in qualsiasi pagina di errore del sito, ad esempio su 404 pagine.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilizza un eVar per raccogliere il codice di errore in modo da poter ottenere ulteriori informazioni sugli errori specifici riscontrati dai visitatori sul tuo sito.
