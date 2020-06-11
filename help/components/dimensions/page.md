---
title: Pagina
description: Nome della pagina.
translation-type: tm+mt
source-git-commit: 87d0c7e20594e2e39f55284e8d50d425cc1cdacf
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 1%

---


# Pagina

La dimensione &quot;Pagina&quot; elenca i nomi delle pagine del sito. Si tratta di una delle dimensioni più comuni utilizzate in Adobe Analytics, in quanto fornisce informazioni su quali pagine del sito eseguono al meglio le operazioni.

Questa dimensione è correlata alla sezione [](site-section.md) Sito e alle dimensioni [Server](server.md) . La pagina è più granulare, il server è meno granulare e la sezione Sito è tra le due.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`pageName` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la `pageName` variabile. Se la `pageName` variabile non è definita, torna all&#39;utilizzo dell&#39;URL della pagina.

## Valori dimensione

I valori delle dimensioni includono i nomi delle pagine del sito. L&#39;organizzazione determina i valori di dimensione specifici che si desidera utilizzare. Alcune organizzazioni utilizzano direttamente `document.title`, mentre altre formulano una breadcrumb personalizzata. Qualunque sia il metodo utilizzato, accertati che sia coerente e che lo registri in un documento [di progettazione della](/help/implement/prepare/solution-design.md)soluzione.

>[!NOTE] In Reporting e analisi, le metriche di conversione utilizzano l&#39;attribuzione lineare per questa dimensione. Ad esempio, le entrate sono suddivise tra tutte le pagine visualizzate in una visita prima di un `purchase` evento. Per impostazione predefinita, Analysis Workspace utilizza l’ultima attribuzione, con l’opzione che consente di utilizzare qualsiasi modello di attribuzione.
