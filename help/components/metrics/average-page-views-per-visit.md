---
title: Visualizzazioni di pagina medie per visita
description: Il numero medio di volte in cui un dato elemento dimensione è apparso in una visita.
feature: Metrics
exl-id: fef6e803-e819-4f0f-8cb0-c565328a8bea
TQID: https://experienceleague.adobe.com/sospsPhk77O5qOLcMLmu7gB7rvlxbp8rGqB39LCnQ5g
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 216
ht-degree: 6%

---

# Visualizzazioni di pagina medie per visita

La dimensione &quot;Visualizzazioni di pagina medie per visita&quot; mostra quante visualizzazioni di pagina si sono verificate in media rispetto alla dimensione desiderata. Per le dimensioni basate sul tempo, puoi vedere le tendenze nel tempo del numero medio di visualizzazioni di pagina all’interno di una visita. Questa [metrica](overview.md) è utile per comprendere con quale frequenza vengono visualizzati gli elementi dimensionali in una visita.

>[!TIP]
>
>Utilizza questa metrica insieme a un&#39;altra metrica (ad esempio [Visite](visits.md)) per ottenere informazioni migliori. Se utilizzi questa metrica da sola, otterrai elementi dimensionali contenenti visualizzazioni di pagina anomale per visita, che in genere non sono preziose.

## Come è calcolata questa metrica

Questa metrica viene calcolata utilizzando la formula [`Page views`](page-views.md)` divided by `[`Visits`](visits.md).

## Percentuali superiori al 100%

Questa metrica contiene spesso percentuali superiori al 100%. Il denominatore è la media di visualizzazioni di pagina per visita dell’intera dimensione e il numeratore è la media di visualizzazioni di pagina per visita dell’elemento dimensione. Se la media di visualizzazioni di pagina per visita dell’intera dimensione è inferiore alla media di visualizzazioni di pagina per visita di un dato elemento dimensione, vedrai percentuali superiori al 100%. L’ordinamento dei rapporti classificati in base a questa metrica mostra anomalie nella media delle visualizzazioni di pagina per visita, valori che in genere non sono preziosi. Adobe consiglia di ordinare i rapporti in base a un&#39;altra metrica, ad esempio [Visite](visits.md).
