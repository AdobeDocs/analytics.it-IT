---
title: Profondità dell'hit
description: Numero di hit nella visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 7%

---


# Profondità dell&#39;hit

La dimensione &#39;Profondità hit&#39; indica la distanza tra una visita e un dato hit. Questa dimensione è importante per comprendere fino a che punto una visita i visitatori eseguono azioni sul sito. La profondità di hit conta tutti i tipi di hit, comprese le visualizzazioni di pagina ([`t()`](/help/implement/vars/functions/t-method.md)) e gli hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Compilare questa dimensione con i dati

Questa dimensione funziona automaticamente per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensione

Gli elementi dimensione includono la stringa `"Hit Depth"` seguita da un numero che rappresenta il numero di hit nella visita. L’elemento dimensione di `"Hit Depth 1"` rappresenta il primo hit della visita, mentre l’elemento dimensione `"Hit Depth 8"` rappresenta l’ottavo hit della visita.

## Confronto con la profondità della visita

La profondità di hit conta tutti i tipi di hit, inclusi la visualizzazione della pagina e gli hit di tracciamento dei collegamenti. La profondità della visita incrementa solo gli incrementi per gli hit della visualizzazione della pagina, _mentre_ l’elemento dimensione [Pagina](page.md) non equivale al valore della pagina precedente. La profondità delle visite è anche una dimensione basata sulle visite, il che significa che è lo stesso valore per tutti gli hit della visita. Nella tabella seguente è riportato un esempio di visita e di come considera la profondità di hit + la profondità di visita:

| Sequenza di pagine | Profondità dell&#39;hit | Conteggia per la profondità della visita? | Informazioni sulla visita |
| --- | --- | --- | --- |
| Home page | 1 | Sì | 4 |
| Pagina prodotto | 2 | Sì | 4 |
| Home page | 3 | Sì | 4 |
| Clic sul collegamento personalizzato | 4 | No (collegamento personalizzato) | 4 |
| Clic sul collegamento personalizzato | 5 | No (collegamento personalizzato) | 4 |
| Pagina prodotto | 6 | Sì | 4 |
| Clic sul collegamento personalizzato | 7 | No (collegamento personalizzato) | 4 |
| Pagina prodotto | 8 | No (come nella pagina precedente) | 4 |
