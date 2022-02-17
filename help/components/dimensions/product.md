---
title: Prodotto
description: Nome del prodotto.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---

# Prodotto

La dimensione &quot;Prodotto&quot; indica il nome del prodotto nell’hit. È utile per le implementazioni che utilizzano il `products` e desidera visualizzare le metriche relative ai prodotti, ad esempio gli articoli più venduti o più visualizzati. Questa dimensione può intenzionalmente essere vuota se non hai prodotti sul sito.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento alla seconda parte della stringa nel [`products`](/help/implement/vars/page-vars/products.md) variabile. Caratteri tra il primo e il secondo punto e virgola (`;`) popola questa dimensione.

## Elementi Dimension

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina gli elementi dimensionali desiderati. Adobe consiglia di stabilire una convenzione di denominazione coerente per i prodotti. [Classificazioni](../classifications/c-classifications.md) sono disponibili se desideri raggruppare i prodotti in modo diverso o fornire un nome più descrittivo. L’Adobe consiglia di utilizzare le dimensioni &quot;Prodotto&quot; e &quot;Categoria&quot;.
