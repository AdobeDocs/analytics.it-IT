---
title: Sezione del sito
description: Nome della sezione del sito.
feature: Dimensions
exl-id: 349bace0-4596-4b4c-bf29-6cd8866c246b
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 4%

---

# Sezione del sito

La &quot;sezione Sito&quot; [dimensione](overview.md) elenca i nomi delle sezioni del sito. Per i siti di grandi dimensioni, è utile raggruppare le pagine in sezioni. Questa dimensione è utile per visualizzare le sezioni del sito con le prestazioni migliori o più elevate.

Questa dimensione è correlata al [Pagina](page.md) e [Server](server.md) dimensioni. La pagina è più granulare, il server meno granulare e la sezione Sito è compresa tra le due.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`ch` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. L’AppMeasurement raccoglie questi dati utilizzando [`channel`](/help/implement/vars/page-vars/channel.md) variabile.

## Elementi dimensionali

Gli elementi di Dimension includono i nomi delle sezioni del sito. L’organizzazione determina gli elementi dimensionali specifici che desideri utilizzare. Indipendentemente dal metodo utilizzato, assicurarsi che sia coerente e che venga registrato in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
