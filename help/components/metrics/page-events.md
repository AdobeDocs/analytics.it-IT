---
title: Eventi pagina
description: Il numero di azioni di tracciamento dei collegamenti attivate.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 205d86b13046bd17e321734904bf57435ef6e106
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 6%

---

# Eventi pagina

Gli &quot;eventi di pagina&quot; [metrica](overview.md) mostra il numero di volte in cui è stata effettuata una chiamata di tracciamento dei collegamenti. Questa metrica è utile quando vuoi capire quali pagine hanno il contenuto più coinvolgente. La misurazione per questa metrica è più utile quando un visitatore può eseguire un’azione sulla pagina senza passare a una nuova pagina.

In un percorso tipico di un sito eCommerce, ad esempio, un visitatore può avere diverse interazioni su una singola pagina. Queste interazioni sono configurate come tracciamento dei collegamenti in un’implementazione tipica di Analytics ([`tl()`](/help/implement/vars/functions/tl-method.md)), mentre una visualizzazione di pagina ([`t()`](/help/implement/vars/functions/t-method.md)) è riservata per il caricamento della pagina iniziale. Questo metodo di implementazione fornisce un tracciamento degli eventi arricchito che fornisce informazioni sulle interazioni che si verificano prima che un visitatore continui il suo percorso.

## Come è calcolata questa metrica

Questa metrica conta tutte le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) in una suite di rapporti. In questa metrica sono inclusi tutti i tipi di collegamento, in particolare [Collegamenti personalizzati](../dimensions/custom-link.md), [Collegamenti di download](../dimensions/download-link.md), e [Collegamenti di uscita](../dimensions/exit-link.md). Non include le chiamate di visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)).

## Confronto con metriche simili

* **Eventi di pagina e [Visualizzazioni pagina](page-views.md)**: gli eventi di pagina contano il numero di chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) ed escludono le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)). Le visualizzazioni di pagina sono l’opposto; conta il numero di chiamate di tracciamento delle visualizzazioni di pagina ed esclude i collegamenti.
