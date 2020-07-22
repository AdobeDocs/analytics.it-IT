---
title: Istanze
description: Numero di hit impostati da una variabile (e non persistenti).
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 1%

---


# Istanze

La metrica &#39;Istanze&#39; mostra il numero di volte in cui una dimensione è stata esplicitamente definita in una richiesta di immagine. Alcune dimensioni, come [eVar](../dimensions/evar.md), persistono elementi dimensione oltre l’hit su cui sono impostati. Questa metrica è utile per visualizzare il numero di volte in cui un elemento dimensione è stato impostato senza gli hit in cui tale valore è persistente.

## Modalità di calcolo di questa metrica

Tra tutti gli hit in una suite di rapporti, includi solo gli hit che impostano esplicitamente un elemento dimensione nella richiesta di immagine. Alcune dimensioni, come [eVar](../dimensions/evar.md), persistono oltre l’hit su cui sono impostate. Metriche come visualizzazioni [di](page-views.md) pagina e [occorrenze](occurrences.md) contano sia i valori iniziali che quelli persistenti. Questa metrica non conta i valori persistenti.