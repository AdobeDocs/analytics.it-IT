---
title: Occorrenze prodotto bot
description: La metrica "Occorrenze prodotto bot" mostra il numero di sotto-hit della stringa di prodotto che corrispondono alle regole bot e sono stati esclusi dal reporting di Analytics.
feature: Metrics
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 3ba8d2cce29a1965c85789c3fd0543c23533e3a8
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 5%
---
# Occorrenze prodotto bot

La &#39;Occorrenze prodotto bot&#39; [metrica](overview.md) mostra il numero di risultati secondari corrispondenti alle [regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Poiché il reporting dei bot è separato dal resto dei dati della suite di rapporti, questa metrica funziona solo con le dimensioni seguenti:

* [Nome bot](../dimensions/bot-name.md)
* [Prodotto](../dimensions/product.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](../dimensions/day.md), [Settimana](../dimensions/week.md) o [Mese](../dimensions/month.md))

L’utilizzo di qualsiasi altra dimensione con questa metrica non restituisce dati.

## Come è calcolata questa metrica

Adobe controlla ogni hit secondario con la [stringa di prodotto](/help/implement/vars/page-vars/products.md) per vedere se corrisponde alle regole bot configurate dalla tua organizzazione. Se un determinato hit secondario corrisponde a una regola bot, l’hit secondario viene escluso dal reporting e questa metrica aumenta di uno.
