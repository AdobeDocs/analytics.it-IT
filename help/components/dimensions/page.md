---
title: Pagina
description: Nome della pagina.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '188'
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
