---
title: Carrelli
description: Il numero di hit in cui un visitatore ha aggiunto il suo primo prodotto a un carrello.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 1%

---

# Carrelli

La metrica &quot;Carrelli&quot; mostra il numero di hit in cui un visitatore ha aggiunto il suo primo prodotto a un carrello.

## Calcolo di questa metrica

Questa metrica conta il numero di hit in cui `scOpen` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile.

## Differenza tra &quot;Carte&quot; e &quot;Visualizzazioni carrello&quot;

Poiché le &quot;visualizzazioni carrello&quot; e &quot;visualizzazioni carrello&quot; sono eventi che richiedono l’implementazione, la tua organizzazione decide la differenza precisa tra queste due metriche. Tuttavia, Adobe ha progettato queste metriche per i seguenti elementi:

* I carrelli attivano solo una volta per acquisto quando un visitatore aggiunge il suo primo prodotto al suo carrello.
* L’attivazione delle aggiunte al carrello per ogni prodotto aggiunto al carrello.

Per il primo prodotto, si attivano sia &#39;Carts&#39; che &#39;Cart Additions&#39;. Anche in questo caso, tali orientamenti non sono concreti; la tua organizzazione determina la logica di implementazione esatta.
