---
description: La variabile "products" viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti (nonché della quantità di acquisto e del prezzo di acquisto).
keywords: Implementazione di Analytics;variabile di prodotti;visualizzazione di prodotto;evento di successo
seo-description: La variabile "products" viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti (nonché della quantità di acquisto e del prezzo di acquisto).
seo-title: Pagina dettagliata di visualizzazione del prodotto
solution: Analytics
title: Pagina dettagliata di visualizzazione del prodotto
topic: Sviluppatore e implementazione
uuid: 464c9daf-b042-4fb8-8ca6-e104c0bcef45
translation-type: tm+mt
source-git-commit: 656fb909447ed079fa42a909a9c197296c9e2723

---


# Pagina dettagliata di visualizzazione del prodotto

La variabile "products" viene utilizzata per tenere traccia dei prodotti e delle categorie di prodotti (nonché della quantità di acquisto e del prezzo di acquisto).

Un evento success deve sempre essere impostato insieme alla *`products`* variabile.

```js
s.events="prodView"
```

>[!NOTE]
>
>Sebbene *`prodView`* sia trattato nell'implementazione come un evento, non ha la stessa flessibilità nell'interfaccia. L'evento *`prodView`*è un'istanza del prodotto ed è disponibile solo nel *`products`* rapporto. Adobe consiglia di utilizzare un *`custom`* evento oltre all' *`prodView`* evento. In questo modo, puoi visualizzare le metriche della visualizzazione prodotto insieme ad altre metriche in altri rapporti di conversione.

```js
s.products=";diamond earrings (54321)"
```

>[!NOTE]
>
>La sintassi della stringa products deve iniziare con un punto e virgola. Si tratta di un requisito di sintassi legacy. È stato utilizzato in precedenza per delimitare la categoria e il prodotto, ma questo crea una limitazione all'interno dell'interfaccia se si desidera modificare il modo in cui si classificano i prodotti. Per la massima flessibilità nei rapporti, è meglio lasciare vuoto questo campo e utilizzare Classificazioni per impostare le categorie.

## Pagina carrello acquisti ( scOpen , scAdd , scRemove ) {#section_469B64F4150149DFB6B2C731279C0BC7}

```js
s.events="scOpen,scAdd" 
s.products=";SKU" 
```

## Prima pagina di estrazione {#section_E15607A9AECB44F79631926C853CF64E}

```js
s.events="scCheckout" 
s.products=";SKU" 
```

## Pagina di conferma {#section_E006943CD5FD42358086581CA44B9660}

```js
s.events="purchase" 
s.products=";SKU" 
```

>[!NOTE]
>
>Anche se l'utilizzo dello SKU nella stringa di prodotto potrebbe rendere il *`products`* rapporto meno leggibile, in seguito verrà offerta la flessibilità massima per la classificazione dei prodotti. Potete creare categorie dallo SKU che indicano finitura, produttore, categoria e sottocategoria.

Quando la *`products`* variabile viene impostata insieme all' *`purchase`* evento, la quantità di acquisto e il prezzo di acquisto totale sono inclusi nel valore dei prodotti come mostrato sopra.
