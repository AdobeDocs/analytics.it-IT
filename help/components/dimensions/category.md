---
title: Categoria
description: La categoria di prodotto dell’hit.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 5%

---

# Categoria

La &#39;Categoria&#39; [dimensione](overview.md) riporta la categoria di prodotto dell&#39;hit. È utile per le implementazioni che utilizzano la variabile `products` e desiderano visualizzare metriche relative alla categoria del prodotto, ad esempio articoli più venduti o più visualizzati. Questa dimensione può essere intenzionalmente vuota se non hai prodotti sul sito.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento alla prima parte della stringa nella variabile [`products`](/help/implement/vars/page-vars/products.md). Tutto ciò che precede il primo punto e virgola (`;`) compila questa dimensione.

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di raggruppare i singoli prodotti in categorie significative, utilizzando le dimensioni &quot;Prodotto&quot; e &quot;Categoria&quot;.

>[!TIP]
>
>Nelle versioni precedenti di Adobe Analytics, erano state imposte alcune limitazioni alla dimensione &quot;Categoria&quot; a causa della sua architettura di elaborazione. Tali limitazioni sono state successivamente rimosse, consentendoti di utilizzare qualsiasi metrica e raggruppamento.
