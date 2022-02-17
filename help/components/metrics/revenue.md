---
title: Ricavi
description: Importo monetario dei prodotti acquistati all'interno di tutti gli ordini.
feature: Metrics
exl-id: a70e4d93-704b-46ac-9cec-31ea20d3dcb5
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 1%

---

# Ricavi

La metrica &quot;Entrate&quot; mostra la quantità monetaria dei prodotti acquistati all’interno di tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito ai ricavi. Ad esempio, puoi visualizzare le campagne principali (utilizzando [Codice di tracciamento](../dimensions/tracking-code.md) dimensione) o termini di ricerca interni superiori (utilizzando un [eVar](../dimensions/evar.md)).

## Calcolo di questa metrica

Per ogni hit dove `purchase` esiste in [`events`](/help/implement/vars/page-vars/events/event-purchase.md) , somma il campo &quot;Prezzo&quot; all&#39;interno del [`products`](/help/implement/vars/page-vars/products.md) variabile.

Questa metrica si basa sul [currencyCode](/help/implement/vars/config-vars/currencycode.md) se la valuta nella pagina è diversa dalla valuta nativa della suite di rapporti.
