---
title: Istanze
description: Il numero di hit impostati (e non mantenuti) da una variabile.
feature: Metrics
exl-id: 9d1a66b5-46f9-4834-87a1-5f63e386e61d
TQID: https://experienceleague.adobe.com/a6Ycw6CVzeSKuOCHezQtLNIZZo6vbkVneVWO0C2QfxQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 263
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
