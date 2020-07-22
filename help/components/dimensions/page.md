---
title: Pagina
description: Nome della pagina.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 1%

---


# Pagina

La dimensione &quot;Pagina&quot; elenca i nomi delle pagine del sito. Si tratta di una delle dimensioni più comuni utilizzate in Adobe  Analytics, in quanto fornisce informazioni su quali pagine del sito eseguono al meglio le prestazioni.

Questa dimensione è correlata alla sezione [](site-section.md) Sito e alle dimensioni [Server](server.md) . La pagina è più granulare, il server è meno granulare e la sezione Sito è tra le due.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`pageName` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la `pageName` variabile. Se la `pageName` variabile non è definita, torna all&#39;utilizzo dell&#39;URL della pagina.

## Elementi dimensione

Gli elementi dimensione includono i nomi delle pagine del sito. L&#39;organizzazione determina quali elementi dimensionali specifici si desidera utilizzare. Alcune organizzazioni utilizzano direttamente `document.title`, mentre altre formulano una breadcrumb personalizzata. Qualunque sia il metodo utilizzato, accertati che sia coerente e che lo registri in un documento [di progettazione della](/help/implement/prepare/solution-design.md)soluzione.

>[!NOTE]
>
>In Reporting e  Analytics, le metriche di conversione utilizzano l&#39;attribuzione lineare per questa dimensione. Ad esempio, le entrate sono suddivise tra tutte le pagine visualizzate in una visita prima di un `purchase` evento.  Analysis Workspace utilizza l&#39;ultima attribuzione per impostazione predefinita, con l&#39;opzione per utilizzare qualsiasi modello di attribuzione.
