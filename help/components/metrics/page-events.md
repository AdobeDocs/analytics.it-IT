---
title: Eventi pagina
description: Il numero di azioni di tracciamento dei collegamenti attivate.
feature: Metrics
exl-id: 1afe86e3-65b3-4e4e-b436-ed7cb5da9641
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 9%

---

# Eventi pagina

Gli &quot;eventi di pagina&quot; [metrica](overview.md) mostra il numero di volte in cui è stata effettuata una chiamata di tracciamento dei collegamenti. Questa metrica è utile quando vuoi capire quali pagine hanno il contenuto più coinvolgente. La misurazione per questa metrica è più utile quando un visitatore può eseguire un’azione sulla pagina senza passare a una nuova pagina.

## Come è calcolata questa metrica

Questa metrica conta tutti [Chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) in una suite di rapporti. Sono inclusi tutti i tipi di collegamento (collegamenti personalizzati, collegamenti di download e collegamenti di uscita). Non include [Chiamate di tracciamento della visualizzazione pagina (`t()`)](/help/implement/vars/functions/t-method.md).

## Confronto con metriche simili

* **Eventi di pagina e [Visualizzazioni pagina](page-views.md)**: gli eventi di pagina contano il numero di chiamate di tracciamento dei collegamenti (`tl()`) ed escludono le chiamate di tracciamento della visualizzazione pagina (`t()`). Le visualizzazioni di pagina sono l’opposto; conta il numero di chiamate di tracciamento delle visualizzazioni di pagina ed esclude i collegamenti.
