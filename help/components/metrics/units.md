---
title: Unità
description: Numero totale di prodotti acquistati in tutti gli ordini.
feature: Metrics
exl-id: c7293445-0760-4237-83ae-812224ca6f4b
TQID: https://experienceleague.adobe.com/0v4pF0Iv0IzU9K4CQiTy1-IIYgMCaO37E6QTmAAEPXc
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
source-wordcount: 173
ht-degree: 4%

---

# Unità

La metrica [unità](overview.md) mostra il numero totale di prodotti acquistati in tutti gli ordini. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito al numero di prodotti acquistati. Ad esempio, puoi visualizzare le campagne principali (utilizzando la dimensione [Codice di tracciamento](../dimensions/tracking-code.md)) o i termini di ricerca interni principali (utilizzando un [eVar](../dimensions/evar.md)) che hanno contribuito ai prodotti acquistati.

## Come è calcolata questa metrica

Per ogni hit in cui esiste `purchase` nella variabile [`events`](/help/implement/vars/page-vars/events/events-overview.md), somma il campo &quot;Quantity&quot; all&#39;interno della variabile [`products`](/help/implement/vars/page-vars/products.md).

## Confrontare ordini e unità

La metrica [Ordini](orders.md) registra solo il numero di eventi di acquisto. La metrica &quot;Unità&quot; è generalmente superiore a &quot;Ordini&quot; perché i clienti possono acquistare più di un prodotto. In questi casi, esiste un singolo ordine con più unità.

Se gli ordini sono superiori alle unità, Adobe consiglia di verificare l’integrità dell’implementazione. È probabile che la variabile `products` non sia impostata correttamente sugli acquisti, il che è in genere un comportamento indesiderato.
