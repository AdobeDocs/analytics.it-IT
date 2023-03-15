---
title: Categoria
description: La categoria di prodotto dell’hit.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 2%

---

# Categoria

La dimensione &quot;Categoria&quot; riporta la categoria di prodotto dell’hit. È utile per le implementazioni che utilizzano `products` e desiderano visualizzare le metriche relative alla categoria di prodotto, ad esempio articoli più venduti o più visualizzati. Questa dimensione può essere intenzionalmente vuota se non hai prodotti sul sito.

## Popola questa dimensione con i dati

Questa dimensione fa riferimento alla prima parte della stringa nella [`products`](/help/implement/vars/page-vars/products.md) variabile. Tutto prima del primo punto e virgola (`;`) compila questa dimensione.

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. L’Adobe consiglia di raggruppare singoli prodotti in categorie significative, utilizzando sia la dimensione &quot;Prodotto&quot; che la dimensione &quot;Categoria&quot;.

>[!TIP]
>
>Nelle versioni precedenti di Adobe Analytics, erano state imposte alcune limitazioni alla dimensione &quot;Categoria&quot; a causa della sua architettura di elaborazione. Tali limitazioni sono state successivamente rimosse, consentendoti di utilizzare qualsiasi metrica e raggruppamento.
