---
title: products
description: Invia dati sui prodotti visualizzati o nel carrello.
feature: Variables
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
role: Admin, Developer
source-git-commit: 7c8ffe8f4ccf0577136e4d7ee96340224897d2a4
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 3%

---

# products

La variabile `products` tiene traccia dei prodotti e delle proprietà ad essi associate. Questa variabile viene generalmente impostata su pagine di singoli prodotti, pagine del carrello acquisti e pagine di conferma degli acquisti. È una variabile con più valori, il che significa che puoi inviare più prodotti nello stesso hit e che l’Adobe analizza il valore in elementi dimensionali separati.

>[!NOTE]
>
>Se questa variabile è impostata in un hit senza la variabile [`events`](events/events-overview.md), la metrica [Visualizzazioni prodotto](/help/components/metrics/product-views.md) viene incrementata di 1. Assicurarsi di impostare gli eventi appropriati per ogni hit con la variabile `products`.

## Prodotti che utilizzano il Web SDK

Se si utilizza l&#39;[**oggetto XDM**](/help/implement/aep-edge/xdm-var-mapping.md), i prodotti sono mappati alle seguenti variabili:

* Categoria mappata a `xdm.productListItems[].productCategories[].categoryID`. Utilizza il primo elemento nell&#39;array `productCategories[]`. Anche `lineItemId` è mappato correttamente, ma l&#39;Adobe consiglia `categoryID` poiché è un XDM standard. Se sono presenti entrambi i campi XDM, `lineItemId` ha la precedenza.
* Prodotto mappato a `xdm.productListItems[].SKU` o `xdm.productListItems[].name`. Se sono presenti entrambi i campi XDM, viene utilizzato `xdm.productListItems[].SKU`.
* Quantità mappata a `xdm.productListItems[].quantity`.
* Prezzo mappato a `xdm.productListItems[].priceTotal`.
* Le eVar di merchandising sono mappate su `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar1` a `xdm.productListItems._experience.analytics.customDimensions.eVars.eVar250`, a seconda dell&#39;eVar che desideri associare a un prodotto.
* Gli eventi di merchandising sono mappati su `xdm.productListItems[]._experience.analytics.event1to100.event1.value` a `xdm.productListItems._experience.analytics.event901to1000.event1000.value`, a seconda dell&#39;evento che si desidera associare a un prodotto. Se imposti un evento in uno di questi campi, questo viene automaticamente incluso nella stringa [event](events/events-overview.md) inviata ad Adobe Analytics.

```json
{
  "xdm": {
    "productListItems": [{
      "productCategories": [{
        "categoryID": "Men's"
      }],
      "name": "Hiking boot",
      "quantity": 1,
      "priceTotal": 49.99
    },
    {
      "productCategories": [{
        "categoryID": "Camping"
      }],
      "name": "Hunting blind",
      "quantity": 3,
      "priceTotal": 699.69
    }]
  }
}
```

Se si utilizza l&#39;[**oggetto dati**](/help/implement/aep-edge/data-var-mapping.md), la variabile prodotti utilizza `data.__adobe.analytics.products` seguendo la sintassi di AppMeasurement. Se imposti questo campo, tutti i prodotti impostati nell’oggetto XDM vengono sovrascritti e non inviati ad Adobe Analytics.

```json
{
  "data": {
    "__adobe": {
      "analytics": {
        "products": "Archery;Fletched arrow;12;159.99"
      }
    }
  }
}
```

## Prodotti tramite l’estensione Adobe Analytics

Non esiste un campo dedicato nella raccolta dati di Adobe Experience Platform per impostare questa variabile; tuttavia, esistono più estensioni di terze parti per aiutarti.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai alla scheda [!UICONTROL Extensions], quindi fai clic su [!UICONTROL Catalog] per visualizzare tutte le estensioni disponibili.
4. Cerca il termine &quot;prodotto&quot;, che rivela diverse estensioni disponibili per aiutare a impostare questa variabile.

Puoi utilizzare una di queste estensioni oppure l’editor di codice personalizzato seguendo la sintassi di AppMeasurement riportata di seguito.

## s.products in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

La variabile `s.products` è una stringa che contiene più campi delimitati per prodotto. Delimitare ogni campo con un punto e virgola (`;`) nella stringa.

* **Categoria** (facoltativo): la categoria del prodotto. La lunghezza massima per questo campo è 100 byte.
* **Nome prodotto** (obbligatorio): nome del prodotto. La lunghezza massima per questo campo è 100 byte.
* **Quantità** (facoltativo): quanti di questi prodotti sono nel carrello. Questo campo si applica solo agli hit con l’evento di acquisto.
* **Prezzo** (facoltativo): il prezzo totale del prodotto espresso in decimali. Se la quantità è più di uno, impostare il prezzo sul totale e non sul singolo prezzo del prodotto. Allineare la valuta di questo valore in modo che corrisponda alla variabile [`currencyCode`](../config-vars/currencycode.md). Non includere il simbolo di valuta in questo campo. Questo campo si applica solo agli hit con l’evento di acquisto.
* **Eventi** (facoltativo): eventi associati al prodotto. Delimitare più eventi con una barra verticale (`|`). Vedi [eventi](events/events-overview.md) per ulteriori informazioni.
* **eVar** (facoltativo): eVar di merchandising associate al prodotto. Delimitare più eVar di merchandising con una barra verticale (`|`). Per ulteriori informazioni, consulta [eVar per merchandising](evar-merchandising.md).

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Questa variabile supporta più prodotti nello stesso hit. È utile per il carrello e gli acquisti che contengono più prodotti. La lunghezza massima per l&#39;intera stringa `products` è di 64 KB. Separa ogni prodotto con una virgola (`,`) nella stringa.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>Elimina tutti i punti e virgola, le virgole e le barre verticali dai nomi dei prodotti, dalle categorie e dai valori degli eVar di merchandising. Se il nome di un prodotto include una virgola, AppMeasurement lo analizza come inizio di un nuovo prodotto. Questa analisi errata elimina il resto della stringa di prodotto, causando dati errati nelle dimensioni e nei rapporti.

## Esempi

La variabile `products` è flessibile quando si omettono campi e si includono più prodotti. Questa flessibilità può semplificare la perdita di un delimitatore, causando l’invio di dati errati all’Adobe da parte dell’implementazione.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = ";Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = ";Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = ";Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = ";Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = ";Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

Se utilizzi il `digitalData` [livello dati](../../prepare/data-layer.md), puoi eseguire un&#39;iterazione attraverso l&#39;array di oggetti `digitalData.product`:

```js
for(var i = 0; i < digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length - 1) {
        s.products += ",";
    }
}
```
