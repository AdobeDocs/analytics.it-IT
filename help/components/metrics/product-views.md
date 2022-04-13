---
title: Visualizzazioni di prodotti
description: Il numero di visualizzazioni nelle pagine dei prodotti.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: eb13c3e828bc6d4c547f4529ee7a15182bbbf046
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 5%

---

# Visualizzazioni di prodotti

La metrica &quot;Visualizzazioni prodotto&quot; mostra il numero di volte in cui un prodotto è stato visualizzato. Questa metrica è utile quando desideri visualizzare i tuoi prodotti più visualizzati o vedere come il totale del prodotto visualizza la tendenza nel tempo.

## Calcolo di questa metrica

Questa metrica conta il numero di hit che corrispondono a **o** dei seguenti elementi:

* Il valore `prodView` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile; o
* La [`products`](/help/implement/vars/page-vars/products.md) è impostata e la variabile `events` è vuota.
