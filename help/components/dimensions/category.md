---
title: Categoria
description: La categoria di prodotto dell’hit.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '155'
ht-degree: 1%

---


# Categoria

La dimensione &quot;Categoria&quot; indica la categoria di prodotto dell’hit. È utile per le implementazioni che utilizzano la `products` variabile e che desiderano visualizzare le metriche intorno alla categoria di prodotti, come i più venduti o la maggior parte visualizzati. Questa dimensione può intenzionalmente essere vuota se non avete prodotti sul sito.

## Compilare questa dimensione con i dati

Questa dimensione fa riferimento alla prima parte della stringa nella [`products`](/help/implement/vars/page-vars/products.md) variabile. Tutto ciò che precede il primo punto e virgola (`;`) compila questa dimensione.

## Valori dimensione

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina i valori della dimensione. Adobe consiglia di raggruppare i singoli prodotti in categorie significative, utilizzando sia le dimensioni &#39;Prodotto&#39; che &#39;Categoria&#39;.

>[!TIP]
>
>Nelle versioni precedenti di Adobe  Analytics, alcune limitazioni alla dimensione &quot;Categoria&quot; erano state imposte a causa della sua architettura di elaborazione. Tali limitazioni sono state successivamente rimosse, consentendo di utilizzare qualsiasi metrica e qualsiasi suddivisione.
