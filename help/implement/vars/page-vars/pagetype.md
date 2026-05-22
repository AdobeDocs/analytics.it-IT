---
title: pageType
description: Determina se la pagina corrente è un errore 404.
feature: Appmeasurement Implementation
exl-id: e61ef82d-b583-4230-b904-5ea3584910be
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/SD-hwWJmZby-y99FIZHrnevSBsVqD6T5gwovn5tJfxo'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 202
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
