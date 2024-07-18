---
title: Visualizzazioni di prodotti
description: Il numero di visualizzazioni alle pagine dei prodotti.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 11%

---

# Visualizzazioni di prodotti

La [metrica](overview.md) di &#39;Visualizzazioni prodotto&#39; mostra il numero di volte in cui è stato visualizzato un prodotto. Questa metrica è utile quando desideri visualizzare i prodotti più visualizzati o vedere la tendenza nel tempo delle visualizzazioni del totale dei prodotti.

## Come è calcolata questa metrica

Questa metrica conta il numero di hit che corrispondono a **uno** dei seguenti:

* Il valore `prodView` esiste nella variabile [`events`](/help/implement/vars/page-vars/events/events-overview.md) oppure
* La variabile [`products`](/help/implement/vars/page-vars/products.md) è impostata e la variabile `events` è vuota.
