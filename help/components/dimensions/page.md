---
title: Pagina
description: Nome della pagina.
feature: Dimensions
exl-id: 579963c8-8460-425f-b716-3b30d7a259af
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 0%

---

# Pagina

La dimensione &quot;Pagina&quot; elenca i nomi delle pagine del sito. Si tratta di una delle dimensioni più comuni utilizzate in Adobe Analytics, in quanto fornisce informazioni sulle pagine del sito che eseguono al meglio le prestazioni.

Questa dimensione è correlata al [Sezione del sito](site-section.md) e [Server](server.md) dimensioni. La pagina è più granulare, il server è meno granulare e la sezione Sito è tra le due.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dal [`pageName` stringa di interrogazione](/help/implement/validate/query-parameters.md) in [Chiamate per la visualizzazione della pagina (`t()`)](/help/implement/vars/functions/t-method.md). [Chiamate di tracciamento dei collegamenti (`tl()`)](/help/implement/vars/functions/tl-method.md) elimina sempre questa dimensione, anche se `pageName` stringa query esistente.

AppMeasurement raccoglie questi dati utilizzando la variabile [`pageName`](/help/implement/vars/page-vars/pagename.md) variabile. Se la `pageName` non è definita, ma torna a utilizzare la variabile [`pageURL`](/help/implement/vars/page-vars/pageurl.md) variabile.

## Elementi Dimension

Gli elementi di Dimension includono i nomi delle pagine del sito. L’organizzazione determina gli elementi dimensionali specifici da utilizzare. Alcune organizzazioni utilizzano direttamente `document.title`, mentre altri formulano una breadcrumb personalizzata. Qualunque sia il metodo utilizzato, assicurati che sia coerente e che lo registri in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).

>[!NOTE]
>
>In Reports &amp; Analytics, le metriche di conversione utilizzano l’attribuzione lineare per questa dimensione. Ad esempio, i ricavi vengono suddivisi tra tutte le pagine visualizzate in una visita prima di un `purchase` evento. Per impostazione predefinita, Analysis Workspace utilizza l’ultima attribuzione, con la possibilità di utilizzare qualsiasi modello di attribuzione.
