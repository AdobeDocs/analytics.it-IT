---
description: La variabile "products" viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti (nonché per quantità di acquisto e prezzo di acquisto).
keywords: Implementazione di Analytics; products, variabile; visualizzazione prodotto; Evento success
seo-description: La variabile "products" viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti (nonché per quantità di acquisto e prezzo di acquisto).
seo-title: Pagina dettagliata di visualizzazione del prodotto
solution: Analytics
title: Pagina dettagliata di visualizzazione del prodotto
topic: Sviluppatore e implementazione
uuid: 464 c 9 daf-b 042-4 fb 8-8 ca 6-e 104 c 0 bcef 45
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Pagina dettagliata di visualizzazione del prodotto

La variabile "products" viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti (nonché per quantità di acquisto e prezzo di acquisto).

A success event should always be set in conjunction with the *`products`* variable.

```js
s.events="prodView"
```

>[!NOTE]
>
>While *`prodView`* is treated in implementation like an event, it does not have the same flexibility in the interface. The *`prodView`*event is an instance of the product and is only available in the *`products`* report. Adobe recommends you use a *`custom`* event in addition to the *`prodView`* event. In questo modo, puoi vedere le metriche di visualizzazione del prodotto, oltre ad altre metriche negli altri rapporti sulla conversione.

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>La sintassi della stringa products deve iniziare con un punto e virgola. Questo è un requisito di sintassi legacy. In precedenza era utilizzata per delimitare la categoria e il prodotto, ma ciò crea una limitazione all'interno dell'interfaccia, utile per cambiare la modalità di classificazione dei prodotti. Per la massima flessibilità nei rapporti, è consigliabile lasciare vuoto questo vuoto e utilizzare Classificazioni per impostare le categorie.

## Shopping Cart Page ( scOpen , scAdd , scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd" 
s.products=";SKU" 
```

## First Checkout Page {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout" 
s.products=”;SKU" 
```

## Confirmation Page {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase" 
s.products=";SKU" 
```

>[!NOTE]
>
>While using the SKU in the product string may make the *`products`* report less readable, it provides the maximum flexibility later when you want to classify your products. Potete creare categorie dall'SKU che indicano terminazione, produttore, categoria e sottocategoria.

When the *`products`* variable is set in conjunction with the *`purchase`* event, the purchase quantity and total purchase price are included in the products value as shown above.
