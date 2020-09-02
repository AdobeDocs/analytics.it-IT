---
title: products
description: Invia i dati relativi ai prodotti visualizzati o contenuti nel carrello.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 0%

---


# products

La `products` variabile tiene traccia di prodotti e proprietà ad essi associati. Questa variabile viene in genere impostata su pagine di prodotti, pagine del carrello e pagine di conferma dell&#39;acquisto. Si tratta di una variabile con più valori, che consente di inviare più prodotti nello stesso hit e  Adobe analizza il valore in elementi dimensionali separati.

>[!NOTE]
>
>Se questa variabile viene impostata in un hit senza un evento del carrello della spesa nella [`events`](events/events-overview.md) variabile, la metrica Visualizzazioni [](/help/components/metrics/product-views.md) prodotto si incrementa di 1. Accertatevi di impostare l&#39;evento del carrello acquisti appropriato su ogni hit con la `products` variabile.

## Prodotti in  Adobe Experience Platform Launch

In Launch non è presente un campo dedicato per impostare questa variabile; tuttavia, esistono più estensioni di terze parti per facilitare l&#39;accesso.

1. Accedete a [launch.adobe.com](https://launch.adobe.com) utilizzando le credenziali AdobeID.
2. Fate clic sulla proprietà desiderata.
3. Vai alla [!UICONTROL Extensions] scheda, quindi fai clic [!UICONTROL Catalog] per visualizzare tutte le estensioni disponibili.
4. Cercare il termine &quot;prodotto&quot;, che rivela diverse estensioni disponibili per aiutare a impostare questa variabile.

Puoi utilizzare una di queste estensioni, oppure puoi utilizzare l&#39;editor di codice personalizzato seguendo la sintassi AppMeasurement riportata di seguito.

## s.products in AppMeasurement e Launch editor di codice personalizzato

La `s.products` variabile è una stringa che contiene più campi delimitati per prodotto. Ogni singolo prodotto può contenere fino a 100 byte in tutti i campi. Delimitare ogni campo con un punto e virgola (`;`) nella stringa.

* **Categoria** (facoltativo): La categoria di prodotto globale. L&#39;organizzazione decide come raggruppare i prodotti in categorie.
* **Nome** prodotto (obbligatorio): Nome del prodotto.
* **Quantità** (facoltativo): Quanti di questi prodotti sono nel carrello. Questo campo si applica solo agli hit con l’evento di acquisto.
* **Prezzo** (facoltativo): Il prezzo totale del prodotto come decimale. Se la quantità è maggiore di una, impostare il prezzo sul totale e non sul prezzo del singolo prodotto. Allineare la valuta di questo valore in modo che corrisponda alla [`currencyCode`](../config-vars/currencycode.md) variabile. Non includere il simbolo di valuta in questo campo. Questo campo si applica solo agli hit con l’evento di acquisto.
* **Eventi** (facoltativo): Eventi collegati al prodotto. Delimitare più eventi con una tubazione (`|`). Per ulteriori informazioni, consulta [Eventi](events/events-overview.md) .
* **eVar** (facoltativo): eVar di merchandising collegate al prodotto. Delimitare più eVar di merchandising con una tubazione (`|`). Per ulteriori informazioni, vedi eVar [merchandising](evar-merchandising.md) .

```js
// Set a single product using all available fields
s.products = "Example category;Example product;1;3.50;event1=4.99|event2=5.99;eVar1=Example merchandising value 1|eVar2=Example merchandising value 2";
```

Questa variabile supporta più prodotti nello stesso hit. È utile per il carrello acquisti e acquisti che contengono più prodotti. Mentre per ogni prodotto è previsto un limite di 100 byte, la lunghezza totale della `products` variabile è 64 K. Separate ogni prodotto con una virgola (`,`) nella stringa.

```js
// Set multiple products - useful for when a visitor views their shopping cart
s.products = "Example category 1;Example product 1;1;3.50,Example category 2;Example product 2,1,5.99";
```

>[!IMPORTANT]
>
>Elimina tutti i punti e virgola, virgole e pipe dai nomi dei prodotti, dalle categorie e dai valori  eVar di merchandising. Se il nome di un prodotto include una virgola, AppMeasurement la analizza come inizio di un nuovo prodotto. Questa analisi errata getta via il resto della stringa di prodotto, causando dati non corretti in dimensioni e rapporti.

## Esempi

La `products` variabile è flessibile quando si omettono campi e si includono più prodotti. Questa flessibilità può semplificare la mancanza di un delimitatore, il che fa sì che l&#39;implementazione invii dati errati al  Adobe.

```js
// Include only product and category. Common on individual product pages
s.products = "Example category;Example product";

// Include only product name if you do not want to use product category
s.products = ";Example product";

// One product has a category, the other does not. Note the comma and adjacent semicolon to omit category
s.products = "Example category;Example product 1,;Example product 2";

// A visitor purchases a single product; record quantity and price
s.events = "purchase";
s.products = "Example category;Example product;1;6.99";

// A visitor purchases multiple products with different quantities
s.events = "purchase";
s.products = "Example category;Example product 1;9;26.91,Example category;Example product 2;4;9.96";

// Attribute currency event1 only to product 2 and not product 1
s.events = "event1";
s.products = "Example category 1;Example product 1;1;1.99,Example category 2;Example product 2;1;2.69;event1=1.29";

// Use multiple numeric events in the product string
s.events = "event1,event2";
s.products = "Example category;Example product;1;4.20;event1=2.3|event2=5";

// Use merchandising eVars without any events. Note the adjacent semicolons to skip events
s.products = "Example category;Example product;1;6.69;;eVar1=Merchandising value";

// Use merchandising eVars without category, quantity, price, or events
s.products = ";Example product;;;;eVar1=Merchandising value";

// Multiple products using multiple different events and multiple different merchandising eVars
s.events = "event1,event2,event3,event4,purchase";
s.products = "Example category 1;Example product 1;3;12.60;event1=1.4|event2=9;eVar1=Merchandising value|eVar2=Another merchandising value,Example category 2;Example product 2;1;59.99;event3=6.99|event4=1;eVar3=Merchandising value 3|eVar4=Example value four";
```

Se si utilizza il livello `digitalData` di [dati, è possibile iterare nell&#39;array di](../../prepare/data-layer.md)`digitalData.product` oggetti:

```js
for(var i=0; i<digitalData.product.length; i++) {
    // Add individual product info to the product string
    s.products += digitalData.product[i].category.primaryCategory + ";" + digitalData.product[i].productInfo.productName;
    // If there are more products, add a comma
    if(i != digitalData.product.length-1) {
        s.products += ",";
    }
}
```
