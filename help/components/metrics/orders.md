---
title: Ordini
description: Il numero di acquisti effettuati.
feature: Metrics
exl-id: b05abb6d-983f-43fe-80ad-a0ddf90de466
source-git-commit: 7d5383e1ee3bee189d3dd48bc6b899f4108f7ba8
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 2%

---

# Ordini

La metrica &quot;Ordini&quot; mostra il numero totale di eventi di acquisto effettuati sul sito. Questa metrica è fondamentale per i siti di eCommerce nella misurazione della conversione. Puoi combinare questa metrica con qualsiasi dimensione per vedere quali elementi dimensionali hanno contribuito a un ordine. Ad esempio, puoi visualizzare le campagne principali (utilizzando [Codice di tracciamento](../dimensions/tracking-code.md) ) o i termini di ricerca interni principali (utilizzando una [eVar](../dimensions/evar.md)) che hanno contribuito agli acquisti.

## Modalità di calcolo di questa metrica

Questa metrica conta il numero di hit in cui `purchase` esiste in [`events`](/help/implement/vars/page-vars/events/events-overview.md) variabile.
