---
title: Visualizzazioni pagina bot
description: Il numero di visualizzazioni di pagina che corrispondono alle regole bot.
feature: Metrics
exl-id: d6699880-3faa-4df9-ad49-c7998f6ce45b
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 11%

---

# Visualizzazioni pagina bot

La metrica [metric](overview.md) delle visualizzazioni di pagina bot mostra il numero di hit di pagina corrispondenti alle [regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md).

Poiché il reporting dei bot è separato dal resto dei dati della suite di rapporti, questa metrica funziona solo con le dimensioni seguenti:

* [Nome bot](../dimensions/bot-name.md)
* [Pagina](../dimensions/page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](../dimensions/day.md), [Settimana](../dimensions/week.md) o [Mese](../dimensions/month.md))

L’utilizzo di qualsiasi altra dimensione con questa metrica non restituisce dati.

## Come è calcolata questa metrica

Adobe controlla ogni hit pagina per vedere se corrisponde alle regole bot configurate dalla tua organizzazione. Se un dato hit corrisponde a una regola bot, l’hit pagina viene escluso dal reporting e questa metrica aumenta di uno. Questa metrica non include gli hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).
