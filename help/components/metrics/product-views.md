---
title: Visualizzazioni di prodotti
description: Il numero di visualizzazioni nelle pagine dei prodotti.
feature: Metrics
exl-id: 6217391d-8b42-4fdf-b05e-b9b117598ad2
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 4%

---

# Visualizzazioni di prodotti

La metrica &quot;Visualizzazioni prodotto&quot; mostra il numero di volte in cui un prodotto è stato visualizzato. Questa metrica è utile quando desideri visualizzare i tuoi prodotti più visualizzati o vedere come il totale del prodotto visualizza la tendenza nel tempo.

## Calcolo di questa metrica

Questa metrica conta il numero di hit che corrispondono a **o** dei seguenti elementi:

* Il valore `prodView` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile; o
* La [`products`](/help/implement/vars/page-vars/products.md) è impostata e non sono presenti eventi del carrello nel `events` variabile. Qualsiasi evento non personalizzato (`event1` - `event1000`) è un evento del carrello.
