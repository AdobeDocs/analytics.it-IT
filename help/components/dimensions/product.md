---
title: Prodotto
description: Nome del prodotto.
translation-type: tm+mt
source-git-commit: 6778dd290424651dc959224daa0eef8ebd8196e5
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 1%

---


# Prodotto

La dimensione &quot;Prodotto&quot; indica il nome del prodotto nell’hit. È utile per le implementazioni che utilizzano la `products` variabile e che desiderano visualizzare le metriche sui prodotti, come i più venduti o la maggior parte visualizzati. Questa dimensione può intenzionalmente essere vuota se non avete prodotti sul sito.

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento alla seconda parte della stringa nella [`products`](/help/implement/vars/page-vars/products.md) variabile. I caratteri tra il primo e il secondo punto e virgola (`;`) popolano questa dimensione.

## Elementi Dimension

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina gli elementi dimensione.  Adobe consiglia di stabilire una convenzione di denominazione coerente per i prodotti. [Le classificazioni](../classifications/c-classifications.md) sono disponibili se desiderate raggruppare i prodotti in modo diverso o fornire un nome più descrittivo.  Adobe consiglia di utilizzare sia le dimensioni &#39;Prodotto&#39; che &#39;Categoria&#39;.
