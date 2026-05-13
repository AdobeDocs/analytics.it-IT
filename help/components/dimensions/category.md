---
title: Categoria
description: La categoria di prodotto dell’hit.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 155
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
