---
title: Nome bot
description: Il nome del bot che corrisponde alle regole bot.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 214
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
