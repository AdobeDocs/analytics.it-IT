---
title: Unità
description: Numero totale di prodotti acquistati in tutti gli ordini.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 4%

---

# Unità

Le &#39;Unità&#39; [metrica](overview.md) mostra il numero totale di prodotti acquistati in tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito al numero di prodotti acquistati. Ad esempio, puoi visualizzare le campagne principali (utilizzando [Codice di tracciamento](../dimensions/tracking-code.md) ) o i termini di ricerca interni principali (utilizzando una [eVar](../dimensions/evar.md)) che hanno contribuito ai prodotti acquistati.

## Come è calcolata questa metrica

Per ogni hit in cui `purchase` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) , somma il campo &quot;Quantity&quot; all&#39;interno del [`products`](/help/implement/vars/page-vars/products.md) variabile.

## Confrontare ordini e unità

Il [Ordini](orders.md) La metrica registra solo il numero di eventi di acquisto. La metrica &quot;Unità&quot; è generalmente superiore a &quot;Ordini&quot; perché i clienti possono acquistare più di un prodotto. In questi casi, esiste un singolo ordine con più unità.

Se gli ordini sono superiori alle unità, Adobe consiglia di verificare l’integrità dell’implementazione. È probabile che il tuo `products` la variabile non è impostata correttamente sugli acquisti, il che è in genere un comportamento indesiderato.
