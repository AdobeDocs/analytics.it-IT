---
title: Visualizzazioni di prodotti
description: Il numero di visualizzazioni alle pagine dei prodotti.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: eb13c3e828bc6d4c547f4529ee7a15182bbbf046
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 5%

---

# Visualizzazioni di prodotti

La metrica &quot;Visualizzazioni prodotto&quot; mostra quante volte è stato visualizzato un prodotto. Questa metrica è utile quando desideri visualizzare i prodotti più visualizzati o vedere la tendenza nel tempo delle visualizzazioni del totale dei prodotti.

## Modalità di calcolo di questa metrica

Questa metrica conta il numero di hit corrispondenti **o** dei seguenti elementi:

* Il valore `prodView` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile; o
* Il [`products`](/help/implement/vars/page-vars/products.md) è impostata, e il `events` la variabile è vuota.
