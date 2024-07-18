---
title: Ordini
description: Il numero di acquisti effettuati.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 7%

---

# Ordini

La [metrica](overview.md) di &#39;Ordini&#39; mostra il numero totale di eventi di acquisto effettuati sul sito. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito a un ordine. Ad esempio, puoi visualizzare le campagne principali (utilizzando la dimensione [Codice di tracciamento](../dimensions/tracking-code.md)) o i termini di ricerca interni principali (utilizzando un [eVar](../dimensions/evar.md)) che hanno contribuito agli acquisti.

## Come è calcolata questa metrica

Questa metrica conta il numero di hit in cui `purchase` esiste nella variabile [`events`](/help/implement/vars/page-vars/events/events-overview.md).
