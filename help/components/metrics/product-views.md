---
title: Viste del prodotto
description: Il numero di visualizzazioni per le pagine di prodotto.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 0%

---


# Viste del prodotto

La metrica &quot;Visualizzazioni prodotto&quot; mostra il numero di volte in cui un prodotto è stato visualizzato. Questa metrica è utile quando desiderate visualizzare i prodotti più visualizzati o vedere la tendenza complessiva del prodotto nel tempo.

## Modalità di calcolo di questa metrica

Questa metrica conta il numero di hit che corrispondono **a uno** dei seguenti:

* Il valore `prodView` esiste nella [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile; o
* La [`products`](/help/implement/vars/page-vars/products.md) variabile è impostata e nella `events` variabile non esistono eventi del carrello. Qualsiasi evento che non è personalizzato (`event1` - `event1000`) è un evento del carrello.