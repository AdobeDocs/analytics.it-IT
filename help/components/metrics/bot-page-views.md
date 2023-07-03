---
title: Visualizzazioni di pagina bot
description: Il numero di visualizzazioni di pagina che corrispondono alle regole bot.
feature: Metrics
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---

# Visualizzazioni di pagina bot

La metrica &quot;Visualizzazioni pagina bot&quot; mostra il numero di hit pagina corrispondenti [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Poiché il reporting dei bot è separato dal resto dei dati della suite di rapporti, questa metrica funziona solo con le dimensioni seguenti:

* [Nome bot](../dimensions/bot-name.md)
* [Pagina](../dimensions/page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](../dimensions/day.md), [Settimana](../dimensions/week.md), o [Mese](../dimensions/month.md))

L’utilizzo di qualsiasi altra dimensione con questa metrica non restituisce dati.

## Modalità di calcolo di questa metrica

Adobe controlla ogni hit pagina per vedere se corrisponde alle regole bot configurate dalla tua organizzazione. Se un dato hit corrisponde a una regola bot, l’hit pagina viene escluso dal reporting e questa metrica aumenta di uno. Questa metrica non include gli hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).
