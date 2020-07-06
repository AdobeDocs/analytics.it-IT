---
title: pageType
description: Determinare se la pagina corrente è un errore 404.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 1%

---


# pageType

La `pageType` variabile è un flag utilizzato per indicare le pagine di errore sul sito, ad esempio 404 errori. Se questa variabile contiene la stringa `errorPage`, compila la dimensione &quot;Pagine non trovate&quot;.

>[!IMPORTANT]
>
>Non impostate questa variabile sulle pagine senza errori.

## Tipo di pagina  lancio Adobe Experience Platform

In Launch non è disponibile un campo dedicato per l’utilizzo di questa variabile. Utilizzate l&#39;editor di codice personalizzato, seguendo la sintassi AppMeasurement.

## s.pageType nell&#39;editor di codice personalizzato AppMeasurement e Launch

La `s.pageType` variabile è una stringa in cui il valore `errorPage` è l&#39;unico valore valido. Impostate questa variabile su questo valore in qualsiasi pagina di errore del sito, ad esempio su 404 pagine.

```js
s.pageType = "errorPage";
```

>[!TIP]
>
>Utilizzate un&#39;eVar per raccogliere il codice di errore in modo da ottenere ulteriori informazioni sugli errori specifici riscontrati dai visitatori sul sito.
