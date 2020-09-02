---
title: Pagina
description: Nome della pagina.
translation-type: tm+mt
source-git-commit: ec6d8e6a3cef3a5fd38d91775c83ab95de47fd55
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---


# Pagina

La dimensione &quot;Pagina&quot; elenca i nomi delle pagine del sito. Si tratta di una delle dimensioni più comuni utilizzate in  Adobe Analytics, in quanto fornisce informazioni sulle pagine del sito che eseguono al meglio le prestazioni.

Questa dimensione è correlata alla sezione [](site-section.md) Sito e alle dimensioni [Server](server.md) . La pagina è più granulare, il server è meno granulare e la sezione Sito è tra le due.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`pageName` di](/help/implement/validate/query-parameters.md) query nelle chiamate di visualizzazione [Pagina (`t()`)](/help/implement/vars/functions/t-method.md). [Le chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) eliminano sempre questa dimensione, anche se la stringa di `pageName` query esiste.

AppMeasurement raccoglie questi dati utilizzando la [`pageName`](/help/implement/vars/page-vars/pagename.md) variabile. Se la `pageName` variabile non è definita, torna a essere utilizzata dalla [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabile.

## Elementi Dimension

Gli elementi di Dimension includono i nomi delle pagine del sito. L&#39;organizzazione determina quali elementi dimensionali specifici si desidera utilizzare. Alcune organizzazioni utilizzano direttamente `document.title`, mentre altre formulano una breadcrumb personalizzata. Qualunque sia il metodo utilizzato, accertati che sia coerente e che lo registri in un documento [di progettazione della](/help/implement/prepare/solution-design.md)soluzione.

>[!NOTE]
>
>In Reporting e analisi, le metriche di conversione utilizzano l&#39;attribuzione lineare per questa dimensione. Ad esempio, le entrate sono suddivise tra tutte le pagine visualizzate in una visita prima di un `purchase` evento.  Analysis Workspace utilizza l&#39;ultima attribuzione per impostazione predefinita, con l&#39;opzione per utilizzare qualsiasi modello di attribuzione.
