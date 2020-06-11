---
title: Eventi delle pagine
description: Numero di azioni di tracciamento dei collegamenti attivate.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Eventi delle pagine

La metrica &#39;Eventi pagina&#39; mostra il numero di volte in cui è stata effettuata una chiamata di tracciamento dei collegamenti. Questa metrica è utile per capire quali pagine contengono il contenuto più coinvolgente. La misurazione di questa metrica è particolarmente utile quando un visitatore può eseguire un’azione sulla pagina senza passare a una nuova pagina.

## Modalità di calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) in una suite di rapporti. Sono inclusi tutti i tipi di collegamento (collegamenti personalizzati, collegamenti per il download e collegamenti di uscita). Non include le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)).

## Confronto con metriche simili

* **Eventi di pagina e visualizzazioni[di](page-views.md)**pagina: Gli eventi di pagina contano il numero di chiamate di tracciamento dei collegamenti (`tl()`) ed escludono le chiamate di tracciamento delle visualizzazioni di pagina (`t()`). Le visualizzazioni pagina sono opposte; conteggia il numero di chiamate di tracciamento delle visualizzazioni di pagina ed esclude i collegamenti.
