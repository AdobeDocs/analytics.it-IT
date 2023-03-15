---
title: Eventi pagina
description: Il numero di azioni di tracciamento dei collegamenti attivate.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 2%

---

# Eventi pagina

La metrica &quot;Eventi di pagina&quot; mostra quante volte è stata effettuata una chiamata di tracciamento dei collegamenti. Questa metrica è utile quando vuoi capire quali pagine hanno il contenuto più coinvolgente. La misurazione per questa metrica è più utile quando un visitatore può eseguire un’azione sulla pagina senza passare a una nuova pagina.

## Modalità di calcolo di questa metrica

Questa metrica conta tutte le chiamate di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)) in una suite di rapporti. Sono inclusi tutti i tipi di collegamento (collegamenti personalizzati, collegamenti di download e collegamenti di uscita). Non include le chiamate di tracciamento della visualizzazione pagina ([`t()`](/help/implement/vars/functions/t-method.md)).

## Confronta con metriche simili

* **Eventi di pagina e [Visualizzazioni pagina](page-views.md)**: gli eventi di pagina contano il numero di chiamate di tracciamento dei collegamenti (`tl()`) ed esclude le chiamate di tracciamento della visualizzazione pagina (`t()`). Visualizzazioni di pagina è l’opposto; conta il numero di chiamate di tracciamento delle visualizzazioni di pagina ed esclude i collegamenti.
