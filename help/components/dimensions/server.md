---
title: Server
description: Nome del server.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 1%

---


# Server

La dimensione &#39;Server&#39; elenca in genere il nome host del sito. Per le suite di rapporti che combinano più domini o sottodomini, questa dimensione è utile per vedere quali domini o sottodomini eseguono al meglio le prestazioni.

Questa dimensione è correlata alle dimensioni della sezione [](page.md) Pagina [e](site-section.md) Sito. La pagina è più granulare, il server è meno granulare e la sezione Sito è tra le due.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`server` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la [`server`](/help/implement/vars/page-vars/server.md) variabile.

## Elementi dimensione

Gli elementi dimensione includono i server sul sito. L&#39;organizzazione determina quali elementi dimensionali specifici si desidera utilizzare. Alcune organizzazioni utilizzano `window.location.hostname`, mentre altre formulano valori personalizzati. Qualunque sia il metodo utilizzato, accertati che sia coerente e che lo registri in un documento [di progettazione della](/help/implement/prepare/solution-design.md)soluzione.
