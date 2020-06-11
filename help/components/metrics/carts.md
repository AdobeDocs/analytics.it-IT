---
title: Carrelli
description: Il numero di hit in cui un visitatore ha aggiunto il primo prodotto a un carrello.
translation-type: tm+mt
source-git-commit: 554ced510600a4d5866e89806b058b5d2d9a3edf
workflow-type: tm+mt
source-wordcount: '157'
ht-degree: 0%

---


# Carrelli

La metrica &quot;Rimozione carrello&quot; mostra il numero di volte in cui un visitatore ha rimosso un elemento dal proprio carrello. Questa metrica è utile per comprendere la parte dell&#39;imbuto di conversione in cui i clienti non sono più interessati a un prodotto.

## Modalità di calcolo di questa metrica

Questa metrica conteggia il numero di hit `scOpen` esistenti nella [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile.

## Differenza tra &#39;Carts&#39; e &#39;Cart Views&#39;

Poiché &quot;Carte&quot; e &quot;Viste carrello&quot; sono eventi che richiedono l’implementazione, la vostra organizzazione decide la differenza esatta tra queste due metriche. Tuttavia, Adobe ha progettato queste metriche per i seguenti elementi:

* &#39;Carts&#39; viene attivato una sola volta per ogni acquisto quando un visitatore aggiunge il suo primo prodotto al suo carrello.
* Attivazioni di &#39;Aggiunte carrello&#39; per ogni prodotto aggiunto al carrello.

Per il primo prodotto, vengono attivati sia &#39;Carts&#39; che &#39;Cart Additions&#39;. Anche in questo caso, tali orientamenti non sono concreti; la vostra organizzazione determina la logica di implementazione esatta.
