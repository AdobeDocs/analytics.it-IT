---
title: Eventi pagina
description: Numero di azioni di tracciamento dei collegamenti attivate.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%

---

# Eventi pagina

La metrica &quot;Eventi pagina&quot; mostra il numero di volte in cui è stata effettuata una chiamata di tracciamento dei collegamenti. Questa metrica è utile per comprendere quali pagine hanno il contenuto più coinvolgente. La misurazione di questa metrica è particolarmente utile quando un visitatore può eseguire un’azione sulla pagina senza passare a una nuova pagina.

## Calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) in una suite di rapporti. Sono inclusi tutti i tipi di collegamento (collegamenti personalizzati, collegamenti per il download e collegamenti di uscita). Non include le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)).

## Confronto con metriche simili

* **Eventi di pagina e [Visualizzazioni pagina](page-views.md)**: Gli eventi di pagina contano il numero di chiamate di tracciamento dei collegamenti (`tl()`) ed esclude le chiamate di tracciamento della visualizzazione della pagina (`t()`). Le visualizzazioni di pagina sono opposte; conta il numero di chiamate di tracciamento della visualizzazione della pagina ed esclude i collegamenti.
