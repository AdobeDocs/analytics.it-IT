---
title: Profondità di hit
description: Numero di hit nella visita.
feature: Dimensions
exl-id: 84c27e3f-4228-4455-95bf-0239928337b5
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 10%

---

# Profondità di hit

La dimensione &#39;Profondità hit&#39; indica la distanza in una visita di un determinato hit. Questa dimensione è utile per comprendere fino a che punto in una visita i visitatori eseguono azioni sul sito. La profondità di hit conta tutti i tipi di hit, comprese le visualizzazioni di pagina ([`t()`](/help/implement/vars/functions/t-method.md)e hit di tracciamento dei collegamenti ([`tl()`](/help/implement/vars/functions/tl-method.md)).

## Popolare questa dimensione con i dati

Questa dimensione funziona come standard per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi Dimension

Gli elementi di Dimension includono la stringa `"Hit Depth"` seguito da un numero che rappresenta il numero di hit nella visita. Elemento dimensionale di `"Hit Depth 1"` rappresenta il primo hit della visita, mentre l’elemento dimensione `"Hit Depth 8"` rappresenta l’ottavo hit della visita.

## Confronto con la profondità della visita

La profondità di hit conta tutti i tipi di hit, inclusi gli hit di visualizzazione della pagina e di tracciamento dei collegamenti. incrementi della profondità solo per gli hit di visualizzazione della pagina, _e_ la [Pagina](page.md) l’elemento dimensionale non è lo stesso valore della pagina precedente. La profondità della visita è anche una dimensione basata su visite, il che significa che è lo stesso valore per tutti gli hit della visita. La tabella seguente illustra un esempio di visita e come considera la profondità di hit + la profondità di visita:

| Sequenza di pagina | Profondità di hit | Conteggia la profondità della visita? | Profondità della visita |
| --- | --- | --- | --- |
| Home page | 1 | Sì | 4 |
| Pagina di prodotto | 2 | Sì | 4 |
| Home page | 3 | Sì | 4 |
| Clic sul collegamento personalizzato | 4 | No (collegamento personalizzato) | 4 |
| Clic sul collegamento personalizzato | 5 | No (collegamento personalizzato) | 4 |
| Pagina di prodotto | 6 | Sì | 4 |
| Clic sul collegamento personalizzato | 7 | No (collegamento personalizzato) | 4 |
| Pagina di prodotto | 8 | No (come nella pagina precedente) | 4 |
