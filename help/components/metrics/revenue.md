---
title: Ricavi
description: Importo monetario dei prodotti acquistati in tutti gli ordini.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 6%

---

# Ricavi

Il &#39;Ricavo&#39; [metrica](overview.md) mostra l&#39;importo monetario dei prodotti acquistati in tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito ai ricavi. Ad esempio, puoi visualizzare le campagne principali (utilizzando [Codice di tracciamento](../dimensions/tracking-code.md) ) o i termini di ricerca interni principali (utilizzando una [eVar](../dimensions/evar.md)).

## Come è calcolata questa metrica

Per ogni hit in cui `purchase` esiste in [`events`](/help/implement/vars/page-vars/events/event-purchase.md) , somma il campo &quot;Prezzo&quot; all&#39;interno del [`products`](/help/implement/vars/page-vars/products.md) variabile.

Questa metrica si basa sulla [currencyCode](/help/implement/vars/config-vars/currencycode.md) variabile se la valuta sulla pagina è diversa dalla valuta nativa della suite di rapporti.
