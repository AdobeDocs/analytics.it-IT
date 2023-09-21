---
title: Profondità della visita
description: Dimensione basata sulla visita che riporta la profondità della visita.
feature: Dimensions
exl-id: 3e9aca08-2255-46ca-9949-77334ee7120e
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 3%

---

# Profondità della visita

Profondità della visita [dimensione](overview.md) riporta il numero di visualizzazioni di pagina viste dal visitatore nell’intera visita. La profondità della visita aumenta solo se l’hit è una visualizzazione di pagina e il [Pagina](page.md) la dimensione non è uguale all’elemento dimensione dell’ultima visualizzazione pagina. Si tratta di una dimensione basata sulle visite, il che significa che contiene lo stesso valore per l’intera visita. Questa variabile è impostata per tutti gli hit in una visita dopo la conclusione di tale visita.

## Popola questa dimensione con i dati

Questa dimensione funziona in modo predefinito per tutte le implementazioni. Se una suite di rapporti contiene dati, questa dimensione funziona.

## Elementi dimensionali

Gli elementi Dimension includono la stringa `"Pages per visit"` seguito da un numero che rappresenta il numero di pagine della visita. L’elemento dimensionale di `"Pages per visit: 1"` rappresenta una visita a pagina singola, mentre l’elemento dimensione `"Pages per visit: 8"` rappresenta una visita con 8 visualizzazioni di pagina (e un numero qualsiasi di chiamate di tracciamento dei collegamenti).

## Confronto con la profondità di hit

Consulta [Profondità di hit](hit-depth.md) per un confronto tra dimensioni.
