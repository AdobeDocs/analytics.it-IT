---
title: Eventi pagina
description: Il numero di azioni di tracciamento dei collegamenti attivate.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
TQID: https://experienceleague.adobe.com/tOEidVQjv4ynokjH53SEdKeOHiqwZn02WZDalUESsAs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f1f1a2d4-0976-4881-b091-c2bb8de7ffacid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 210
ht-degree: 6%

---

# Eventi pagina

La [metrica](overview.md) di &#39;Eventi pagina&#39; mostra il numero di volte in cui è stata effettuata una chiamata di tracciamento dei collegamenti. Questa metrica è utile quando vuoi capire quali pagine hanno il contenuto più coinvolgente. La misurazione per questa metrica è più utile quando un visitatore può eseguire un’azione sulla pagina senza passare a una nuova pagina.

In un percorso tipico di un sito eCommerce, ad esempio, un visitatore può avere diverse interazioni su una singola pagina. In un&#39;implementazione tipica di Analytics queste interazioni sono configurate come chiamata di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)), mentre una chiamata di visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)) è riservata per il caricamento della pagina iniziale. Questo metodo di implementazione fornisce un tracciamento degli eventi arricchito che fornisce ad insight informazioni sulle interazioni che si verificano prima che un visitatore continui il suo percorso.

## Come è calcolata questa metrica

Questa metrica conta tutte le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) in una suite di rapporti. In questa metrica sono inclusi tutti i tipi di collegamento, in particolare [Collegamenti personalizzati](../dimensions/custom-link.md), [Collegamenti di download](../dimensions/download-link.md) e [Collegamenti di uscita](../dimensions/exit-link.md). Non include chiamate di visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)).

## Confronto con metriche simili

* **Eventi di pagina rispetto a [Visualizzazioni pagina](page-views.md)**: gli eventi di pagina contano il numero di chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) ed escludono le chiamate di tracciamento delle visualizzazioni pagina ([`t()`](/help/implement/vars/functions/t-method.md)). Le visualizzazioni di pagina sono l’opposto; conta il numero di chiamate di tracciamento delle visualizzazioni di pagina ed esclude i collegamenti.
