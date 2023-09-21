---
title: Nome bot
description: Il nome del bot che corrisponde alle regole bot.
exl-id: 668c1dce-c603-477a-9df7-dacb649bbf63
feature: Dimensions
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 5%

---

# Nome bot

Il &#39;nome bot&#39; [dimensione](overview.md) mostra i nomi dei bot rilevati utilizzando [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md). Queste regole possono essere regole IAB predefinite o regole bot personalizzate configurate dalla tua organizzazione. È utile nei casi in cui desideri saperne di più sui bot che visitano il tuo sito o su quali bot generano più traffico.

Hit corrispondenti [!UICONTROL Bot rules] vengono filtrati automaticamente da tutti i rapporti di Analytics, ad eccezione di questa dimensione, [Occorrenze bot](../metrics/bot-occurrences.md), e [Visualizzazioni di pagina bot](../metrics/bot-page-views.md). Puoi utilizzare questa dimensione e queste due metriche per vedere quali dati bot vengono esclusi dal resto dei rapporti.

Poiché il reporting dei bot è separato dal resto dei dati della suite di rapporti, questa dimensione supporta solo le dimensioni e le metriche seguenti:

* [Pagina](page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](day.md), [Settimana](week.md), o [Mese](month.md))
* [Occorrenze bot](../metrics/bot-occurrences.md)
* [Visualizzazioni pagina bot](../metrics/bot-page-views.md)

L’utilizzo di qualsiasi altra dimensione o metrica con questa dimensione non restituisce dati.

## Popola questa dimensione con i dati

Se hai abilitato [Regole bot](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md), questa dimensione raccoglie automaticamente i dati. Se non hai ancora abilitato [!UICONTROL Bot rules], questa dimensione non viene visualizzata in Analysis Workspace.

## Elementi dimensionali

Ogni elemento dimensionale elenca il nome del bot che corrisponde ai criteri delle regole IAB o bot personalizzati.
