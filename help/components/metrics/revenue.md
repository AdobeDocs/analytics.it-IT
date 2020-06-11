---
title: Ricavi
description: L'ammontare monetario dei prodotti acquistati all'interno di tutti gli ordini.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---


# Ricavi

La metrica &quot;Revenue&quot; (Entrate) mostra la quantità monetaria di prodotti acquistati all&#39;interno di tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali valori di dimensione hanno contribuito alle entrate. Ad esempio, potete visualizzare le campagne principali (utilizzando la dimensione del codice [di](../dimensions/tracking-code.md) tracciamento) o i termini di ricerca interni principali (utilizzando una [eVar](../dimensions/evar.md)).

## Modalità di calcolo di questa metrica

Per ogni hit in cui `purchase` esiste nella [`events`](/help/implement/vars/page-vars/events/event-purchase.md) variabile, somma il campo &#39;Prezzo&#39; all&#39;interno della [`products`](/help/implement/vars/page-vars/products.md) variabile.

Questa metrica si basa sulla variabile [currencyCode](/help/implement/vars/config-vars/currencycode.md) se la valuta sulla pagina è diversa dalla valuta nativa della suite di rapporti.
