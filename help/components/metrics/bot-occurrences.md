---
title: Occorrenze bot
description: Il numero di hit che corrispondono alle regole bot.
feature: Metrics
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 9%

---

# Occorrenze bot

&quot;Occorrenze bot&quot; [metrica](overview.md) mostra il numero di hit corrispondenti [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Poiché il reporting dei bot è separato dal resto dei dati della suite di rapporti, questa metrica funziona solo con le dimensioni seguenti:

* [Nome bot](../dimensions/bot-name.md)
* [Pagina](../dimensions/page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](../dimensions/day.md), [Settimana](../dimensions/week.md), o [Mese](../dimensions/month.md))

L’utilizzo di qualsiasi altra dimensione con questa metrica non restituisce dati.

## Come è calcolata questa metrica

Adobe controlla ogni hit per vedere se corrisponde alle regole bot configurate dalla tua organizzazione. Se un dato hit corrisponde a una regola bot, l’hit viene escluso dal reporting e questa metrica aumenta di uno. Questa metrica include entrambe le visualizzazioni di pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)), considerando quanto segue [Visualizzazioni di pagina bot](bot-page-views.md) non includere gli hit di tracciamento dei collegamenti.
