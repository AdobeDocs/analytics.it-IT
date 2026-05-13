---
title: Occorrenze bot
description: Il numero di hit che corrispondono alle regole bot.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
TQID: https://experienceleague.adobe.com/LH7eQC-Z6Y3nku1QzI9Yn0N3MRwGA--5R-93lfadT1c
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 130
ht-degree: 9%

---

# Occorrenze bot

La &#39;Occorrenze bot&#39; [metrica](overview.md) mostra il numero di hit che corrispondono alle [regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Poiché il reporting dei bot è separato dal resto dei dati della suite di rapporti, questa metrica funziona solo con le dimensioni seguenti:

* [Nome bot](../dimensions/bot-name.md)
* [Pagina](../dimensions/page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](../dimensions/day.md), [Settimana](../dimensions/week.md) o [Mese](../dimensions/month.md))

L’utilizzo di qualsiasi altra dimensione con questa metrica non restituisce dati.

## Come è calcolata questa metrica

Adobe controlla ogni hit per vedere se corrisponde alle regole bot configurate dalla tua organizzazione. Se un dato hit corrisponde a una regola bot, l’hit viene escluso dal reporting e questa metrica aumenta di uno. Questa metrica include sia le visualizzazioni di pagina ([`t()`](/help/implement/vars/functions/t-method.md)) che gli hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)), mentre [le visualizzazioni di pagina bot](bot-page-views.md) non includono gli hit di tracciamento dei collegamenti.
