---
title: Visualizzazioni pagina in primo piano
description: Il numero di visualizzazioni di pagina che corrispondono alle regole di bot.
exl-id: 9b1efcb1-10ca-40fb-8f20-e6da105366d9
hide: true
hidefromtoc: true
source-git-commit: 017559d2b909deb4bf87fb5fe41db8250f2ca2ac
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
