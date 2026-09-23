---
title: Pagina
description: Nome della pagina.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 5%
---
# Pagina

La dimensione [pagina](overview.md) elenca i nomi delle pagine del sito. Si tratta di una delle dimensioni più comuni utilizzate in Adobe Analytics, in quanto fornisce ad insight le pagine del sito con le prestazioni migliori.

Questa dimensione è correlata alle dimensioni [Sezione sito](site-section.md) e [Server](server.md). La pagina è più granulare, il server meno granulare e la sezione Sito è compresa tra le due.

## Popolare questa dimensione con i dati

Imposta la variabile [`pageName`](/help/implement/vars/page-vars/pagename.md) nelle [chiamate di visualizzazione pagina (`t()`)](/help/implement/vars/functions/t-method.md). Se la variabile `pageName` non è impostata, questa dimensione utilizza come fallback la variabile [`pageURL`](/help/implement/vars/page-vars/pageurl.md). [Le chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) eliminano sempre questa dimensione, anche se il valore `pageName` esiste.

| Proprietà | Valore |
| --- | --- |
| **Variabile AppMeasurement** | [`pageName`](/help/implement/vars/page-vars/pagename.md) |
| **Campo Web SDK / XDM** | [`web.webPageDetails.name`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **Parametro query** | [`pageName`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Tag XML** | [`<pageName>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Limite di byte** | 100 byte |
| **Persistenza** | Hit |

## Elementi dimensionali

Gli elementi di Dimension includono i nomi delle pagine del sito. L’organizzazione determina gli elementi dimensionali specifici che desideri utilizzare. Alcune organizzazioni utilizzano direttamente `document.title`, mentre altre formulano una breadcrumb personalizzata. Indipendentemente dal metodo utilizzato, assicurati che sia coerente e che venga registrato in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace utilizza l’ultima attribuzione per impostazione predefinita, con l’opzione di utilizzare qualsiasi modello di attribuzione.
