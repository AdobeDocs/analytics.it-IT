---
title: Visualizzazioni pagina in primo piano
description: Il numero di visualizzazioni di pagina che corrispondono alle regole di bot.
source-git-commit: 61a0292bf2f8ff22b414c2e91da476c1da69d163
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---

# Visualizzazioni pagina in primo piano

La metrica &quot;Visualizzazioni pagina bot&quot; mostra il numero di hit pagina che corrispondono [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Poiché il reporting di bot è separato dal resto dei dati della suite di rapporti, questa metrica funziona solo con le seguenti dimensioni:

* [Nome bot](../dimensions/bot-name.md)
* [Pagina](../dimensions/page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](../dimensions/day.md), [Settimana](../dimensions/week.md)oppure [Mese](../dimensions/month.md))

L’utilizzo di qualsiasi altra dimensione con questa metrica non restituisce dati.

## Calcolo di questa metrica

Adobe controlla ogni hit di pagina per vedere se corrisponde alle regole bot configurate dalla tua organizzazione. Se un determinato hit corrisponde a una regola bot, l’hit di pagina viene escluso dal rapporto e questa metrica aumenta di uno. Questa metrica non include gli hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).
