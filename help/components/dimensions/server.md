---
title: Server
description: Nome del server.
feature: Dimensions
exl-id: c2454c0d-497e-46f8-8569-7d0517097cab
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 2%

---

# Server

Il &#39;Server&#39; [dimensione](overview.md) in genere elenca il nome host del sito. Per le suite di rapporti che combinano più domini o sottodomini, questa dimensione è utile per vedere quali domini o sottodomini offrono le prestazioni migliori.

Questa dimensione è correlata al [Pagina](page.md) e [Sezione del sito](site-section.md) dimensioni. La pagina è più granulare, il server meno granulare e la sezione Sito è compresa tra le due.

## Popola questa dimensione con i dati

Questa dimensione recupera i dati da [`server` stringa di query](/help/implement/validate/query-parameters.md) nelle richieste di immagini. L’AppMeasurement raccoglie questi dati utilizzando [`server`](/help/implement/vars/page-vars/server.md) variabile.

## Elementi dimensionali

Gli elementi del Dimension includono i server del sito. L’organizzazione determina gli elementi dimensionali specifici che desideri utilizzare. Alcune organizzazioni utilizzano `window.location.hostname`mentre altri formulano valori personalizzati. Indipendentemente dal metodo utilizzato, assicurarsi che sia coerente e che venga registrato in un [documento di progettazione della soluzione](/help/implement/prepare/solution-design.md).
