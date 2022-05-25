---
title: Carrelli
description: Il numero di hit in cui un visitatore ha aggiunto il suo primo prodotto a un carrello.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 932a6c1452d4710b11c1ce5551c845ef6721f137
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 1%

---

# Carrelli

La metrica &quot;Carrelli&quot; mostra il numero di hit in cui un visitatore ha aggiunto il suo primo prodotto a un carrello.

## Calcolo di questa metrica

Questa metrica conta il numero di hit in cui `scOpen` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile.

## Differenza tra &quot;Carrelli&quot;, &quot;Visualizzazioni carrello&quot; e &quot;Aggiunte al carrello&quot;

Poiché &quot;Carts&quot;, &quot;Cart views&quot; e &quot;Cart Additions&quot; sono eventi che richiedono l’implementazione, la tua organizzazione decide la differenza precisa tra queste metriche. Tuttavia, Adobe ha progettato queste metriche per la logica seguente:

* I carrelli attivano solo una volta per acquisto quando un visitatore aggiunge il suo primo prodotto al suo carrello.
* Le &quot;visualizzazioni del carrello&quot; vengono attivate ogni volta che un visitatore visualizza il carrello.
* L’attivazione delle aggiunte al carrello per ogni prodotto aggiunto al carrello.

Quando un cliente aggiunge il suo primo prodotto a un carrello, il comportamento desiderato è che si attivano sia i &quot;Carrelli&quot; che gli &quot;Aggiunti al carrello&quot;. Anche in questo caso, tali orientamenti non sono concreti; la tua organizzazione determina la logica di implementazione esatta.
