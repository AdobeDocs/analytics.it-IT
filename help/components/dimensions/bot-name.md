---
title: Nome bot
description: Il nome del bot che corrisponde alle regole bot.
exl-id: 034dce46-e83c-4053-a062-3998231f8d6b
feature: Dimensions
TQID: 'https://experienceleague.adobe.com/lJn65s1JtcJf7WobPEeouvwlk7G5qd8XtgxvGLY-zu8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
source-git-commit: 3ba8d2cce29a1965c85789c3fd0543c23533e3a8
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 10%
---
# Nome bot

La &#39;dimensione nome bot&#39; [dimension](overview.md) mostra i nomi dei bot rilevati mediante [regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md). Queste regole possono essere regole IAB predefinite o regole bot personalizzate configurate dalla tua organizzazione. È utile nei casi in cui desideri saperne di più sui bot che visitano il tuo sito o su quali bot generano più traffico.

Gli hit che corrispondono a [!UICONTROL Bot rules] vengono filtrati automaticamente da tutti i rapporti di Analytics, ad eccezione di questa dimensione, [Occorrenze bot](../metrics/bot-occurrences.md), [Visualizzazioni pagina bot](../metrics/bot-page-views.md) e [Occorrenze prodotto bot](../metrics/bot-product-occurrences.md). Puoi utilizzare questa dimensione e queste tre metriche per vedere quali dati bot vengono esclusi dal resto dei rapporti.

Poiché il reporting dei bot è separato dal resto dei dati della suite di rapporti, questa dimensione supporta solo le dimensioni e le metriche seguenti:

* [Pagina](page.md)
* [Prodotto](product.md) (solo con [occorrenze prodotto bot](../metrics/bot-product-occurrences.md))
* Dimensioni basate sul tempo (ad esempio, [Giorno](day.md), [Settimana](week.md) o [Mese](month.md))
* [Occorrenze bot](../metrics/bot-occurrences.md)
* [Visualizzazioni pagina bot](../metrics/bot-page-views.md)
* [Occorrenze prodotto bot](../metrics/bot-product-occurrences.md)

L’utilizzo di qualsiasi altra dimensione o metrica con questa dimensione non restituisce dati.

## Popolare questa dimensione con i dati

Se hai abilitato [Regole bot](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md), questa dimensione raccoglie automaticamente i dati. Se non hai ancora abilitato [!UICONTROL Bot rules], questa dimensione non viene visualizzata in Analysis Workspace.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | Nessuno (derivato dalle regole di rilevamento dei bot) |
| **Campo Web SDK / XDM** | Nessuno (derivato dalle regole di rilevamento dei bot) |
| **Parametro query** | N/D |
| **Tag XML** | N/D |
| **Limite di byte** | N/D |
| **Persistenza** | N/D |

## Elementi dimensionali

Ogni elemento dimensionale elenca il nome del bot che corrisponde ai criteri delle regole IAB o bot personalizzati.
