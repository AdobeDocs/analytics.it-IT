---
title: Sezione Sito
description: Nome della sezione del sito.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---


# Sezione Sito

La dimensione &quot;Sezione del sito&quot; elenca i nomi delle sezioni del sito presenti sul sito. Per i siti di grandi dimensioni, è utile raggruppare le pagine in sezioni. Questa dimensione è utile per visualizzare le sezioni del sito più visualizzate o più performanti.

Questa dimensione è correlata alle dimensioni [Pagina](page.md) e [Server](server.md) . La pagina è più granulare, il server è meno granulare e la sezione Sito è tra le due.

## Compilare questa dimensione con i dati

Questa dimensione recupera i dati dalla stringa [`ch` di](/help/implement/validate/query-parameters.md) query nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la [`channel`](/help/implement/vars/page-vars/channel.md) variabile.

## Elementi dimensione

Gli elementi dimensione includono i nomi delle sezioni del sito sul sito. L&#39;organizzazione determina quali elementi dimensionali specifici si desidera utilizzare. Qualunque sia il metodo utilizzato, accertati che sia coerente e che lo registri in un documento [di progettazione della](/help/implement/prepare/solution-design.md)soluzione.
