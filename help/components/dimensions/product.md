---
title: Prodotto
description: Il nome del prodotto.
feature: Dimensions
exl-id: 2649c200-4b0a-49a9-8592-9b9af72b91cf
source-git-commit: a40f30bbe8fdbf98862c4c9a05341fb63962cdd1
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 6%

---

# Prodotto

La [dimensione](overview.md) &quot;Prodotto&quot; riporta il nome del prodotto nell&#39;hit. È utile per le implementazioni che utilizzano la variabile `products` e desiderano visualizzare metriche relative ai prodotti, ad esempio articoli più venduti o più visualizzati. Questa dimensione può essere intenzionalmente vuota se non hai prodotti sul sito.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento alla seconda parte della stringa nella variabile [`products`](/help/implement/vars/page-vars/products.md). La dimensione viene compilata con caratteri compresi tra il primo e il secondo punto e virgola (`;`).

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di stabilire una convenzione di denominazione coerente per i prodotti. [Le classificazioni](../classifications/classifications-overview.md) sono disponibili se desideri raggruppare i prodotti in modo diverso o fornire un nome più descrittivo. Adobe consiglia di utilizzare entrambe le dimensioni &quot;Prodotto&quot; e &quot;Categoria&quot;.
