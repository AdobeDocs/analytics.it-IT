---
title: Unità
description: Il numero totale di prodotti acquistati all'interno di tutti gli ordini.
translation-type: tm+mt
source-git-commit: 54aeaa35fea8f725c87030936fa24f415064e333
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---


# Unità

La metrica &quot;Unità&quot; mostra il numero totale di prodotti acquistati all&#39;interno di tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali valori di dimensione hanno contribuito a determinare quanti prodotti sono stati acquistati. Ad esempio, potete visualizzare le campagne principali (utilizzando la dimensione del codice [di](../dimensions/tracking-code.md) tracciamento) o i termini di ricerca interna principali (utilizzando una [eVar](../dimensions/evar.md)) che hanno contribuito ai prodotti acquistati.

## Modalità di calcolo di questa metrica

Per ogni hit in cui `purchase` esiste nella [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile, somma il campo &#39;Quantity&#39; all&#39;interno della [`products`](/help/implement/vars/page-vars/products.md) variabile.

## Confronta ordini e unità

La metrica [Ordini](orders.md) registra solo il numero di eventi di acquisto. La metrica &quot;Unità&quot; è in genere superiore a &quot;Ordini&quot; perché i clienti possono acquistare più prodotti. In questi casi, esiste un unico ordine con più unità.

Se ordini superiori alle unità, Adobe consiglia di verificare l&#39;integrità dell&#39;implementazione. È probabile che la `products` variabile non sia impostata correttamente sugli acquisti, il che è in genere un comportamento indesiderato.
