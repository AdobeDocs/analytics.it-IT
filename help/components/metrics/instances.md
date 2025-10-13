---
title: Istanze
description: Il numero di hit impostati (e non mantenuti) da una variabile.
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
source-git-commit: 813d209980ad02c412970a698c282c1358921ed6
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 15%

---

# Istanze

La [metrica](overview.md) &#39;Istanze&#39; mostra il numero di volte in cui una dimensione è stata definita in modo esplicito in una richiesta di immagine. Alcune dimensioni, ad esempio [eVar](../dimensions/evar.md), mantengono gli elementi dimensionali oltre l&#39;hit su cui sono impostati. Questa metrica è utile quando vuoi visualizzare il numero di volte in cui un elemento dimensione è stato impostato senza gli hit in cui tale valore è persistito.

## Come è calcolata questa metrica

Di tutti gli hit in una suite di rapporti, includi solo quelli che impostano esplicitamente un elemento dimensione nella richiesta di immagine. Alcune dimensioni, come le [eVar](../dimensions/evar.md) persistono oltre l’hit su cui sono impostate. Le metriche come [Visualizzazioni pagina](page-views.md) e [Occorrenze](occurrences.md) contano sia i valori iniziali che quelli persistenti. Questa metrica non conta i valori persistenti.

Ad esempio, un visitatore arriva sul tuo sito e utilizza la ricerca interna. Tieni traccia della ricerca interna in eVar1. Dopo aver utilizzato una sola volta la ricerca interna, visita altre cinque pagine prima di uscire.

Quando visualizzi un rapporto in Workspace, visualizzi un’istanza di eVar1 e sei occorrenze. Un’istanza conta nella pagina dei risultati della ricerca, mentre la metrica Occorrenze conta il valore iniziale e i successivi valori persistenti.

## Confronto con metriche simili

* **Istanze rispetto a [Occorrenze](occurrences.md)**: le istanze non includono gli hit in cui un elemento dimensione persiste. Occorrenze: vengono conteggiati gli hit in cui è stato impostato o mantenuto un elemento di dimensione.
* **Istanze rispetto a [Visualizzazioni pagina](page-views.md)**: le istanze includono tutti i tipi di hit, incluse le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)), le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) e i dati di riepilogo [Origini dati](/help/import/data-sources/overview.md). La metrica delle visualizzazioni pagina include solo le chiamate di tracciamento della visualizzazione della pagina, escluse le chiamate di tracciamento dei collegamenti e le origini dati di riepilogo.
