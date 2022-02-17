---
title: Sezione del sito
description: Nome della sezione del sito.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 2%

---

# Sezione del sito

La dimensione &quot;Sezione sito&quot; elenca i nomi delle sezioni del sito presenti sul sito. Per i siti di grandi dimensioni, è utile raggruppare le pagine in sezioni. Questa dimensione è utile per visualizzare le sezioni del sito più visualizzate o più performanti.

Questa dimensione è correlata al [Pagina](page.md) e [Server](server.md) dimensioni. La pagina è più granulare, il server è meno granulare e la sezione Sito è tra le due.

## Popolare questa dimensione con i dati

Questa dimensione recupera i dati dal [`ch` stringa di interrogazione](/help/implement/validate/query-parameters.md) nelle richieste di immagini. AppMeasurement raccoglie questi dati utilizzando la variabile [`channel`](/help/implement/vars/page-vars/channel.md) variabile.

## Elementi Dimension

Gli elementi di Dimension includono i nomi delle sezioni del sito. L’organizzazione determina gli elementi dimensionali specifici da utilizzare. Qualunque sia il metodo utilizzato, assicurati che sia coerente e che lo registri in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
