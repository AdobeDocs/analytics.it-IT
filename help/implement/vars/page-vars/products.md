---
title: products
description: Invia dati sui prodotti visualizzati o nel carrello.
feature: Variables
exl-id: f26e7c93-f0f1-470e-a7e5-0e310ec666c7
source-git-commit: 19bb3da46637bf8afc4e5723e2fa28b490e09c88
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 4%

---

# products

Il `products` la variabile traccia i prodotti e le proprietà ad essi associate. Questa variabile viene generalmente impostata su pagine di singoli prodotti, pagine del carrello acquisti e pagine di conferma degli acquisti. È una variabile con più valori, il che significa che puoi inviare più prodotti nello stesso hit e che l’Adobe analizza il valore in elementi dimensionali separati.

>[!NOTE]
>
>Se questa variabile è impostata in un hit senza il [`events`](events/events-overview.md) variabile, [Visualizzazioni prodotto](/help/components/metrics/product-views.md) incrementa di 1 la metrica. Assicurati di impostare gli eventi appropriati per ogni hit con il `products` variabile.

## Prodotti che utilizzano il Web SDK

I prodotti sono [mappato per Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=it) in diversi campi XDM:

* Categoria mappata a `productListItems[].productCategories[].categoryID`. Utilizza il primo elemento nella `productCategories[]` array. `lineItemId` anche mappare correttamente, ma si consiglia di `categoryID` poiché si tratta di XDM standard. Se sono presenti entrambi i campi XDM `lineItemId` ha la precedenza.
* Il prodotto è mappato a `productListItems[].SKU` o `productListItems[].name`. Se sono presenti entrambi i campi XDM, `productListItems[].SKU` viene utilizzato.
* Quantità mappata a `productListItems[].quantity`.
* Il prezzo è mappato a `productListItems[].priceTotal`.
* Le eVar di merchandising sono mappate su `productListItems._experience.analytics.customDimensions.eVars.eVar1` a `productListItems._experience.analytics.customDimensions.eVars.eVar250`, a seconda dell’eVar da associare a un prodotto.
* Gli eventi di merchandising sono mappati su `productListItems[]._experience.analytics.event1to100.event1.value` a `productListItems._experience.analytics.event901to1000.event1000.value`, a seconda dell’evento che desideri associare a un prodotto. Se imposti un evento in uno di questi campi, questo viene automaticamente incluso nel [evento](events/events-overview.md) stringa inviata ad Adobe Analytics.

>[!NOTE]
>
>`lineItemId` deve essere aggiunto come campo personalizzato in quanto non fa ancora parte dello schema evento standard di Analytics. Adobe prevede di aggiungere in futuro un campo &quot;Categoria&quot; dedicato.

## Prodotti tramite l’estensione Adobe Analytics

Non esiste un campo dedicato nella raccolta dati di Adobe Experience Platform per impostare questa variabile; tuttavia, esistono più estensioni di terze parti per aiutarti.

1. Accedi a [Raccolta dati di Adobe Experience Platform](https://experience.adobe.com/data-collection) utilizzando le credenziali Adobe ID.
2. Fai clic sulla proprietà del tag desiderata.
3. Vai a [!UICONTROL Extensions] , quindi fai clic su [!UICONTROL Catalog] per visualizzare tutte le estensioni disponibili.
4. Cerca il termine &quot;prodotto&quot;, che rivela diverse estensioni disponibili per aiutare a impostare questa variabile.

Puoi utilizzare una di queste estensioni oppure l’editor di codice personalizzato seguendo la sintassi di AppMeasurement riportata di seguito.

## s.products in AppMeasurement e nell’editor di codice personalizzato dell’estensione Analytics

Il `s.products` variabile è una stringa che contiene più campi delimitati per prodotto. Delimitare ogni campo con un punto e virgola (`;`) nella stringa.

* **Categoria** (facoltativo): categoria di prodotto. La lunghezza massima per questo campo è 100 byte.
* **Nome del prodotto** (obbligatorio): nome del prodotto. La lunghezza massima per questo campo è 100 byte.
* **Quantità** (facoltativo): quanti di questi prodotti sono nel carrello. Questo campo si applica solo agli hit con l’evento di acquisto.
* **Prezzo** (facoltativo): il prezzo totale del prodotto espresso in cifre decimali. Se la quantità è più di uno, impostare il prezzo sul totale e non sul singolo prezzo del prodotto. Allinea la valuta di questo valore in modo che corrisponda al [`currencyCode`](../config-vars/currencycode.md) variabile. Non includere il simbolo di valuta in questo campo. Questo campo si applica solo agli hit con l’evento di acquisto.
* **Eventi** (facoltativo): eventi associati al prodotto. Delimitare più eventi con una barra verticale (`|`). Consulta [Eventi](events/events-overview.md) per ulteriori informazioni.
* **eVar** (facoltativo): eVar di merchandising associate al prodotto. Delimitare più eVar di merchandising con una barra verticale (`|`). Consulta [eVar di merchandising](evar-merchandising.md) per ulteriori informazioni.

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Questa variabile supporta più prodotti nello stesso hit. È utile per il carrello e gli acquisti che contengono più prodotti. Lunghezza massima per l&#39;intero `products` stringa è di 64 KB. Separa ogni prodotto con una virgola (`,`) nella stringa.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2;1;5.99";
```

>[!WARNING]
>
>Elimina tutti i punti e virgola, le virgole e le barre verticali dai nomi dei prodotti, dalle categorie e dai valori degli eVar di merchandising. Se il nome di un prodotto include una virgola, AppMeasurement lo analizza come inizio di un nuovo prodotto. Questa analisi errata elimina il resto della stringa di prodotto, causando dati errati nelle dimensioni e nei rapporti.

## Esempi

Il `products` è flessibile quando si omettono i campi e si includono più prodotti. Questa flessibilità può semplificare la perdita di un delimitatore, causando l’invio di dati errati all’Adobe da parte dell’implementazione.

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

Se utilizzi il `digitalData` [livello dati](../../prepare/data-layer.md), è possibile eseguire iterazioni attraverso `digitalData.product` array di oggetti:

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
