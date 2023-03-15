---
title: Prodotto
description: Il nome del prodotto.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 2%

---

# Prodotto

La dimensione &quot;Prodotto&quot; riporta il nome del prodotto nell’hit. È utile per le implementazioni che utilizzano `products` e desiderano visualizzare metriche relative ai prodotti, ad esempio articoli più venduti o più visualizzati. Questa dimensione può essere intenzionalmente vuota se non hai prodotti sul sito.

## Popola questa dimensione con i dati

Questa dimensione fa riferimento alla seconda parte della stringa nella [`products`](/help/implement/vars/page-vars/products.md) variabile. Caratteri compresi tra il primo e il secondo punto e virgola (`;`) compila questa dimensione.

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. L’Adobe consiglia di stabilire una convenzione di denominazione coerente per i prodotti. [Classificazioni](../classifications/c-classifications.md) sono disponibili se desideri raggruppare i prodotti in modo diverso o fornire un nome più descrittivo. L’Adobe consiglia di utilizzare entrambe le dimensioni &quot;Prodotto&quot; e &quot;Categoria&quot;.
