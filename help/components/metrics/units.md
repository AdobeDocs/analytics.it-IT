---
title: Unità
description: Numero totale di prodotti acquistati in tutti gli ordini.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
source-git-commit: a1fbd3f483d3a236fe5dc3246f5e90c1b3f51ba9
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 4%

---

# Unità

La metrica [unità](overview.md) mostra il numero totale di prodotti acquistati in tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito al numero di prodotti acquistati. Ad esempio, puoi visualizzare le campagne principali (utilizzando la dimensione [Codice di tracciamento](../dimensions/tracking-code.md)) o i termini di ricerca interni principali (utilizzando un [eVar](../dimensions/evar.md)) che hanno contribuito ai prodotti acquistati.

## Come è calcolata questa metrica

Per ogni hit in cui esiste `purchase` nella variabile [`events`](/help/implement/vars/page-vars/events/events-overview.md), somma il campo &quot;Quantity&quot; all&#39;interno della variabile [`products`](/help/implement/vars/page-vars/products.md).

## Confrontare ordini e unità

La metrica [Ordini](orders.md) registra solo il numero di eventi di acquisto. La metrica &quot;Unità&quot; è generalmente superiore a &quot;Ordini&quot; perché i clienti possono acquistare più di un prodotto. In questi casi, esiste un singolo ordine con più unità.

Se gli ordini sono superiori alle unità, Adobe consiglia di verificare l’integrità dell’implementazione. È probabile che la variabile `products` non sia impostata correttamente sugli acquisti, il che è in genere un comportamento indesiderato.
