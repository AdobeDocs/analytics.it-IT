---
title: Istanze
description: Il numero di hit impostati da una variabile (e non persistenti).
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---

# Istanze

La metrica &quot;Istanze&quot; mostra il numero di volte in cui una dimensione è stata definita in modo esplicito in una richiesta di immagine. Alcune dimensioni, come [eVar](../dimensions/evar.md), mantiene gli elementi dimensionali oltre l’hit su cui sono impostati. Questa metrica è utile quando vuoi visualizzare il numero di volte in cui un elemento dimensione è stato impostato senza gli hit in cui tale valore è persistito.

## Modalità di calcolo di questa metrica

Di tutti gli hit in una suite di rapporti, includi solo quelli che impostano esplicitamente un elemento dimensione nella richiesta di immagine. Alcune dimensioni, come [eVar](../dimensions/evar.md), persistono oltre l&#39;hit su cui sono impostati. Metriche come [Visualizzazioni pagina](page-views.md) e [Occorrenze](occurrences.md) conteggia sia i valori iniziali che quelli permanenti. Questa metrica non conta i valori persistenti.
