---
title: Unità
description: Numero totale di prodotti acquistati all’interno di tutti gli ordini.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 1%

---

# Unità

La metrica &quot;Unità&quot; mostra il numero totale di prodotti acquistati all’interno di tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito a quanti prodotti sono stati acquistati. Ad esempio, puoi visualizzare le campagne principali (utilizzando [Codice di tracciamento](../dimensions/tracking-code.md) dimensione) o termini di ricerca interni superiori (utilizzando un [eVar](../dimensions/evar.md)) che ha contribuito all’acquisto dei prodotti.

## Calcolo di questa metrica

Per ogni hit dove `purchase` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) , somma il campo &quot;Quantity&quot; all&#39;interno del campo [`products`](/help/implement/vars/page-vars/products.md) variabile.

## Confrontare ordini e unità

La [Ordini](orders.md) registra solo il numero di eventi di acquisto. La metrica &quot;Unità&quot; è generalmente superiore a &quot;Ordini&quot; perché i clienti possono acquistare più di un prodotto. In questi casi, esiste un unico ordine con più unità.

Se hai ordini superiori alle unità, Adobe consiglia di verificare l’integrità dell’implementazione. È probabile che il tuo `products` variabile non è impostata correttamente sugli acquisti, il che in genere è un comportamento indesiderato.
