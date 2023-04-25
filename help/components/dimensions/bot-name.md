---
title: Nome bot
description: Il nome del bot che corrisponde alle regole del bot.
source-git-commit: d7d9bbf9bf43509eb756408f772be870c3854aa5
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 1%

---

# Nome bot

La dimensione &quot;Nome bot&quot; mostra i nomi dei bot rilevati utilizzando [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Queste regole possono essere regole IAB predefinite o regole bot personalizzate configurate dalla tua organizzazione. È utile nei casi in cui desideri saperne di più su quali bot visitano il tuo sito o quali bot generano il maggior traffico.

Hit corrispondenti [!UICONTROL Bot rules] sono filtrate automaticamente da tutte le attività di reporting di Analytics, ad eccezione di questa dimensione, [Occorrenze dei bot](../metrics/bot-occurrences.md)e [Visualizzazioni pagina in primo piano](../metrics/bot-page-views.md). Puoi utilizzare questa dimensione e queste due metriche per vedere quali dati di bot sono esclusi dal resto dei rapporti.

Poiché il reporting di bot è separato dal resto dei dati della suite di rapporti, con questa dimensione sono supportate solo le dimensioni e le metriche seguenti:

* [Pagina](page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](day.md), [Settimana](week.md)oppure [Mese](month.md))
* [Occorrenze dei bot](../metrics/bot-occurrences.md)
* [Visualizzazioni pagina in primo piano](../metrics/bot-page-views.md)

L’utilizzo di qualsiasi altra dimensione o metrica con questa dimensione non restituisce dati.

## Popolare questa dimensione con i dati

Se hai abilitato [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), questa dimensione raccoglie automaticamente i dati. Se non è ancora abilitato [!UICONTROL Bot rules], questa dimensione non viene visualizzata in Analysis Workspace.

## Elementi dimensionali

Ogni elemento dimensione elenca il nome del bot che corrisponde ai criteri della regola bot IAB o personalizzati.
