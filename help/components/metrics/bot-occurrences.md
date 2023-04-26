---
title: Occorrenze dei bot
description: Il numero di hit che corrispondono a regole bot.
exl-id: 3b6cbe94-98db-4ba4-aab2-ce59cdbc420a
hide: true
hidefromtoc: true
source-git-commit: 017559d2b909deb4bf87fb5fe41db8250f2ca2ac
workflow-type: tm+mt
source-wordcount: '129'
ht-degree: 0%

---

# Occorrenze dei bot

La metrica &quot;Occorrenze bot&quot; mostra il numero di hit che corrispondono [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

Poiché il reporting di bot è separato dal resto dei dati della suite di rapporti, questa metrica funziona solo con le seguenti dimensioni:

* [Nome bot](../dimensions/bot-name.md)
* [Pagina](../dimensions/page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](../dimensions/day.md), [Settimana](../dimensions/week.md)oppure [Mese](../dimensions/month.md))

L’utilizzo di qualsiasi altra dimensione con questa metrica non restituisce dati.

## Calcolo di questa metrica

Adobe controlla ogni hit per vedere se corrisponde alle regole bot configurate dalla tua organizzazione. Se un hit corrisponde a una regola bot, l’hit viene escluso dal rapporto e questa metrica aumenta di uno. Questa metrica include entrambe le visualizzazioni di pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)), considerando che [Visualizzazioni pagina in primo piano](bot-page-views.md) non includere gli hit di tracciamento dei collegamenti.
