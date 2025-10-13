---
title: Carrelli
description: Il numero di hit in cui un visitatore ha aggiunto il primo prodotto al carrello.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 4%

---

# Carrelli

La [metrica](overview.md) &quot;Carrelli&quot; mostra il numero di hit in cui un visitatore ha aggiunto il suo primo prodotto al carrello.

## Come è calcolata questa metrica

Questa metrica conta il numero di hit in cui `scOpen` esiste nella variabile [`events`](/help/implement/vars/page-vars/events/events-overview.md).

## Differenza tra &quot;Carrelli&quot;, &quot;Visualizzazioni carrello&quot; e &quot;Aggiunte carrello&quot;

Poiché &quot;Carrelli&quot;, &quot;Visualizzazioni carrello&quot; e &quot;Aggiunte carrello&quot; sono eventi che richiedono l’implementazione, la tua organizzazione determina la differenza precisa tra queste metriche. Tuttavia, Adobe ha progettato queste metriche per la seguente logica:

* &quot;Carrelli&quot; viene attivato solo una volta per acquisto quando un visitatore aggiunge il primo prodotto al carrello.
* Le visualizzazioni del carrello si attivano ogni volta che un visitatore visualizza il carrello.
* Trigger &quot;Aggiunte al carrello&quot; per ogni prodotto aggiunto al carrello.

Quando un cliente aggiunge il primo prodotto a un carrello, il comportamento previsto è l’attivazione di &quot;Carrelli&quot; e &quot;Aggiunte carrello&quot;. Anche in questo caso, queste linee guida non sono concrete; la tua organizzazione determina l’esatta logica di implementazione.
