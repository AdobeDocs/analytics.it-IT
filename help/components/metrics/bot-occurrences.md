---
title: Occorrenze bot
description: Il numero di hit che corrispondono alle regole bot.
feature: Metrics
exl-id: 94cbbee4-8455-48b1-b804-534ed8fccdc9
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '129'
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
