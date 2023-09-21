---
title: Pagina
description: Nome della pagina.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 1%

---

# Pagina

La &#39;Pagina&#39; [dimensione](overview.md) elenca i nomi delle pagine del sito. Si tratta di una delle dimensioni più comuni utilizzate in Adobe Analytics, in quanto fornisce informazioni approfondite sulle pagine del sito che offrono le prestazioni migliori.

Questa dimensione è correlata al [Sezione del sito](site-section.md) e [Server](server.md) dimensioni. La pagina è più granulare, il server meno granulare e la sezione Sito è compresa tra le due.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`pageName` stringa di query](/help/implement/validate/query-parameters.md) in [Chiamate di visualizzazione pagina (`t()`)](/help/implement/vars/functions/t-method.md). [Chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) elimina sempre questa dimensione, anche se `pageName` stringa di query esistente.

L’AppMeasurement raccoglie questi dati utilizzando [`pageName`](/help/implement/vars/page-vars/pagename.md) variabile. Se il `pageName` variabile non è definita, torna a utilizzare il [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabile.

## Elementi dimensionali

Gli elementi di Dimension includono i nomi delle pagine del sito. L’organizzazione determina gli elementi dimensionali specifici che desideri utilizzare. Alcune organizzazioni utilizzano direttamente `document.title`, mentre altri formulano una breadcrumb personalizzata. Indipendentemente dal metodo utilizzato, assicurarsi che sia coerente e che venga registrato in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>In Reports &amp; Analytics, le metriche di conversione utilizzano l’attribuzione lineare per questa dimensione. Ad esempio, i ricavi vengono suddivisi tra tutte le pagine visualizzate in una visita prima di un `purchase` evento. Analysis Workspace utilizza l’ultima attribuzione per impostazione predefinita, con l’opzione di utilizzare qualsiasi modello di attribuzione.
