---
title: Profondità di hit
description: Il numero di hit nella visita.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 22%

---

# Profondità di hit

La &#39;Profondità di hit&#39; [dimensione](overview.md) indica quanto è distante una visita da un determinato hit. Questa dimensione è utile per comprendere fino a che punto in una visita i visitatori eseguono azioni sul sito. La profondità degli hit conta tutti i tipi di hit, incluse le visualizzazioni di pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e gli hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Popolare questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi di Dimension includono la stringa `"Hit Depth"` seguita da un numero che rappresenta il numero di hit nella visita. L&#39;elemento dimensione di `"Hit Depth 1"` rappresenta il primo hit della visita, mentre l&#39;elemento dimensione `"Hit Depth 8"` rappresenta l&#39;ottavo hit della visita.

## Confronto con profondità di visita

La profondità degli hit conta tutti i tipi di hit, inclusi gli hit di visualizzazione pagina e di tracciamento dei collegamenti. Incrementi solo di profondità di visita per gli hit di visualizzazione pagina, _e_ l&#39;elemento dimensione [Pagina](page.md) non corrisponde al valore della pagina precedente. La profondità della visita è anche una dimensione basata sulla visita, il che significa che è lo stesso valore per tutti gli hit nella visita. La tabella seguente illustra un esempio di visita e come considera la profondità di hit + la profondità di visita:

| Sequenza di pagine | Profondità di hit | Conta per la profondità di visita? | Profondità della visita |
| --- | --- | --- | --- |
| Pagina Home | 1 | Sì | 4 |
| Pagina prodotto | 2 | Sì | 4 |
| Pagina Home | 3 | Sì | 4 |
| Clic collegamento personalizzato | 4 | No (collegamento personalizzato) | 4 |
| Clic collegamento personalizzato | 5 | No (collegamento personalizzato) | 4 |
| Pagina prodotto | 6 | Sì | 4 |
| Clic collegamento personalizzato | 7 | No (collegamento personalizzato) | 4 |
| Pagina prodotto | 8 | No (come nella pagina precedente) | 4 |
