---
title: Categoria
description: La categoria di prodotto dell’hit.
feature: Dimensions
exl-id: 3517b417-1a44-4d3e-ac16-93fdc5f36404
TQID: 'https://experienceleague.adobe.com/3G1qDbtVnRj8At-FU1fNaI8KLboMQvo8NKktinrTbs8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 6%
---
# Categoria

La &#39;Categoria&#39; [dimensione](overview.md) riporta la categoria di prodotto dell&#39;hit. È utile per le implementazioni che utilizzano la variabile `products` e desiderano visualizzare metriche relative alla categoria del prodotto, ad esempio articoli più venduti o più visualizzati. Questa dimensione può essere intenzionalmente vuota se non hai prodotti sul sito.

## Popolare questa dimensione con i dati

Questa dimensione fa riferimento alla categoria di prodotto nella variabile [`products`](/help/implement/vars/page-vars/products.md), ovvero tutto ciò che precede il primo punto e virgola (`;`).

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`products`](/help/implement/vars/page-vars/products.md) |
| **Campo Web SDK / XDM** | [`productListItems[].productCategories[].categoryID`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/commerce-details) |
| **Parametro query** | [`products`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<products>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 100 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Poiché questa variabile è basata su una stringa personalizzata nell’implementazione, l’organizzazione determina quali sono gli elementi dimensionali. Adobe consiglia di raggruppare i singoli prodotti in categorie significative, utilizzando le dimensioni &quot;Prodotto&quot; e &quot;Categoria&quot;.

>[!TIP]
>
>Nelle versioni precedenti di Adobe Analytics, erano state imposte alcune limitazioni alla dimensione &quot;Categoria&quot; a causa della sua architettura di elaborazione. Tali limitazioni sono state successivamente rimosse, consentendoti di utilizzare qualsiasi metrica e raggruppamento.
