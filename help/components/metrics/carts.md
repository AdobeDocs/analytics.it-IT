---
title: Carrelli
description: Il numero di hit in cui un visitatore ha aggiunto il primo prodotto al carrello.
feature: Metrics
exl-id: 890bbaba-0140-4995-bbd2-c69aedc801e5
TQID: https://experienceleague.adobe.com/a-qT5Ly8-4mSBGbGTAzbwLIMRFZtqotMPvGFgOrM41Y
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
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
