---
title: Istanze
description: Il numero di hit impostati (e non mantenuti) da una variabile.
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 3%

---

# Istanze

Le &#39;Istanze&#39; [metrica](overview.md) mostra il numero di volte in cui una dimensione è stata definita in modo esplicito in una richiesta di immagine. Alcune dimensioni, come [eVar](../dimensions/evar.md), mantiene gli elementi dimensionali oltre l’hit su cui sono impostati. Questa metrica è utile quando vuoi visualizzare il numero di volte in cui un elemento dimensione è stato impostato senza gli hit in cui tale valore è persistito.

## Come è calcolata questa metrica

Di tutti gli hit in una suite di rapporti, includi solo quelli che impostano esplicitamente un elemento dimensione nella richiesta di immagine. Alcune dimensioni, come [eVar](../dimensions/evar.md), persistono oltre l&#39;hit su cui sono impostati. Metriche come [Visualizzazioni pagina](page-views.md) e [Occorrenze](occurrences.md) conteggia sia i valori iniziali che quelli permanenti. Questa metrica non conta i valori persistenti.

Ad esempio, un visitatore arriva sul tuo sito e utilizza la ricerca interna. Puoi tenere traccia della ricerca interna in eVar1. Dopo aver utilizzato una sola volta la ricerca interna, visita altre cinque pagine prima di uscire.

Se visualizzi un rapporto in Workspace, visualizzerai un’istanza eVar1 e sei occorrenze. L’istanza si è attivata nella pagina dei risultati della ricerca, mentre le occorrenze conteggiavano il valore iniziale e i valori persistenti.
