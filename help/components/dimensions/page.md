---
title: Pagina
description: Nome della pagina.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
TQID: https://experienceleague.adobe.com/npKfFB-zOPzNGJJ6YZvtz0oA3NDWuQiHYBraH09lc58
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 188
ht-degree: 4%

---

# Pagina

La dimensione [pagina](overview.md) elenca i nomi delle pagine del sito. Si tratta di una delle dimensioni più comuni utilizzate in Adobe Analytics, in quanto fornisce ad insight le pagine del sito con le prestazioni migliori.

Questa dimensione è correlata alle dimensioni [Sezione sito](site-section.md) e [Server](server.md). La pagina è più granulare, il server meno granulare e la sezione Sito è compresa tra le due.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa di query [`pageName`](/help/implement/validate/query-parameters.md) in [chiamate di visualizzazione pagina (`t()`)](/help/implement/vars/functions/t-method.md). [Le chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) eliminano sempre questa dimensione, anche se la stringa di query `pageName` esiste.

AppMeasurement raccoglie questi dati utilizzando la variabile [`pageName`](/help/implement/vars/page-vars/pagename.md). Se la variabile `pageName` non è impostata, questa dimensione utilizza come fallback la variabile [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Elementi dimensionali

Gli elementi di Dimension includono i nomi delle pagine del sito. L’organizzazione determina gli elementi dimensionali specifici che desideri utilizzare. Alcune organizzazioni utilizzano direttamente `document.title`, mentre altre formulano una breadcrumb personalizzata. Indipendentemente dal metodo utilizzato, assicurati che sia coerente e che venga registrato in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>Analysis Workspace utilizza l’ultima attribuzione per impostazione predefinita, con l’opzione di utilizzare qualsiasi modello di attribuzione.
