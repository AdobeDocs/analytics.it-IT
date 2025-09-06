---
title: Nome bot
description: Il nome del bot che corrisponde alle regole bot.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '213'
ht-degree: 7%

---

# Nome bot

La &#39;dimensione nome bot&#39; [dimension](overview.md) mostra i nomi dei bot rilevati mediante [regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md). Queste regole possono essere regole IAB predefinite o regole bot personalizzate configurate dalla tua organizzazione. È utile nei casi in cui desideri saperne di più sui bot che visitano il tuo sito o su quali bot generano più traffico.

Gli hit che corrispondono a [!UICONTROL Bot rules] vengono filtrati automaticamente da tutti i rapporti di Analytics, con l&#39;eccezione di [Occorrenze bot](../metrics/bot-occurrences.md) e [Visualizzazioni pagina bot](../metrics/bot-page-views.md). Puoi utilizzare questa dimensione e queste due metriche per vedere quali dati bot vengono esclusi dal resto dei rapporti.

Poiché il reporting dei bot è separato dal resto dei dati della suite di rapporti, questa dimensione supporta solo le dimensioni e le metriche seguenti:

* [Pagina](page.md)
* Dimensioni basate sul tempo (ad esempio, [Giorno](day.md), [Settimana](week.md) o [Mese](month.md))
* [Occorrenze bot](../metrics/bot-occurrences.md)
* [Visualizzazioni pagina bot](../metrics/bot-page-views.md)

L’utilizzo di qualsiasi altra dimensione o metrica con questa dimensione non restituisce dati.

## Popolare questa dimensione con i dati

Se hai abilitato [Regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), questa dimensione raccoglie automaticamente i dati. Se non hai ancora abilitato [!UICONTROL Bot rules], questa dimensione non viene visualizzata in Analysis Workspace.

## Elementi dimensionali

Ogni elemento dimensionale elenca il nome del bot che corrisponde ai criteri delle regole IAB o bot personalizzati.
